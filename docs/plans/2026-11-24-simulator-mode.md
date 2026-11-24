# Simulator Mode Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add a simulator mode to the learning-coach skill: the coach plays one counterpart in a conversation the student is practising (oral exam, questions after a talk, seminar discussion, foreign-language conversation, patient or client conversation), followed by a debrief and a harder second round.

**Architecture:** One skill, one reference file per role. The instructions live in a new `skills/learning-coach/references/simulator.md`; `SKILL.md` only gains a Modes bullet, a sentence saying when to read the file, a step-aside case and a trigger in the description. Behaviour is tested with scripted scenarios run against fresh command-line sessions, scenarios first (baseline on the current skill), then the file, then the reruns.

**Tech Stack:** Markdown skill files; the `claude` CLI for scenario runs (model `claude-opus-5-5`); `python3` and `zip` for checks and the build.

**Spec:** `docs/specs/2026-11-24-simulator-mode.md` (approved by the author on 24 November 2026). Decisions behind it: `docs/decisions.md`, 24 November 2026.

## Global Constraints

- The `description:` line in `SKILL.md` stays at 1,024 characters or fewer, measured with the command in Task 4. It is 1,020 now.
- Skill text is in English. German appears only in student-facing examples, with Swiss spelling (*ss*, never *ß*) and «guillemets».
- No workplace examples anywhere in the new text. The audience is study and learning (decided 24 November).
- The simulator is in the skill only. `portable/prompt.md` does not change: the diff check in Task 4 prints nothing.
- `version` in `SKILL.md` stays `0.3.1`. The bump happens at release.
- Values from the spec, used verbatim wherever they appear: the counterpart makes one question or one reply per turn, under about 60 words; a scene runs about six to ten exchanges, with one hard moment after about three; the debrief stays under about 150 words; the second round has no hints unless the student stops the scene; "went well" means handling the hard moment in the second round; the control words are «Pause» and «Stopp», given in the student's language (*pause* and *stop* in English).
- Scenario dates follow `tests/scenarios.md`: Monday 16 November 2026 unless a scenario says otherwise. At run time, shift the dates in the opening messages to the run date and record the shift, as Round 8 did.
- Nothing is committed unless the author asks. Each task ends with a checkpoint (`git status --short`) in place of a commit.

## Review Focus

Inputs the spec implies but no scenario in its Tests section covers, most likely first. Each one has a test added to the task that owns it.

1. **The account's copy of the skill loads instead of the project's.** The author has `learning-coach` installed in their Claude account. If a harness session loads that copy, the run tests 0.3.1, not this change. Expected: every run's tool calls show the project copy. Test: the mechanical check in Task 2, step 3, repeated in Task 6.
2. **A shortened description stops fix requests from loading the skill.** Task 4 cuts words from the description. Expected: the ten rows of "Trigger check for fixes" behave as before. Test: Task 6, step 3.
3. **The student answers "no idea" inside the scene.** Expected: the counterpart reacts in role, as a real examiner would (rephrases, narrows the question or moves on), and does not step out to teach. Test: a scripted line in scenario 18 (Task 1).
4. **The student switches to their own language inside a foreign-language scene** to ask for a word. Expected: one short answer, then straight back to the target language, without a lesson or a correction of earlier mistakes. Test: a scripted line in scenario 19 (Task 1).
5. **The student says they are panicking in the middle of the scene.** Expected: the coach steps out of role at once, answers in one or two calm lines, and offers to go on or stop, with no lecture. Test: a scripted line in scenario 20 (Task 1).

---

### Task 1: Simulator scenarios in `tests/scenarios.md`

**Files:**
- Modify: `tests/scenarios.md:3` (the count line)
- Modify: `tests/scenarios.md` (append a new part after scenario 17, at the end of the file)

**Interfaces:**
- Produces: criteria **S1** to **S5**, scenarios **18** to **21**, and the section "Trigger check for the simulator". Tasks 2 and 6 run them, and the Round 9 entry in Task 6 refers to them by these numbers and names.

- [ ] **Step 1: Change the count line.** Line 3 says "Seventeen conversations". Change it to "Twenty-one conversations"; leave the rest of the sentence.

- [ ] **Step 2: Append the heading and the simulator criteria.** After the end of scenario 17, add `---`, then `# Simulator (draft)`, one sentence saying these scenarios test `references/simulator.md` and that G1 to G5 apply as well, and this list:
  - **S1 In role.** During the scene the coach speaks only as the counterpart. It steps out only for «Pause», «Stopp», a "what should I say?" or a student in distress.
  - **S2 No giving in.** The counterpart does not accept a vague or wrong answer in order to move on, does not reveal the answer, and does not praise.
  - **S3 One move per turn.** In role, one question or one reply per turn, under about 60 words.
  - **S4 Their view first.** The debrief asks for the student's view before giving the coach's.
  - **S5 A harder second round.** When a second round runs, it is harder than the first and has no hints unless the student stops the scene.

- [ ] **Step 3: Add scenario 18, "Simulator: oral exam".** Same layout as scenario 16 (Opening message, Student, The coach should, Failure).
  - **Opening message:** "Can you be my examiner? I have a 15-minute oral exam in statistics on Friday 20 November, on linear regression. I want to practise."
  - **Student:** Lea. If asked for material: "my slides cover simple regression: slope, intercept, R², residuals". In the scene, her first answer on what the slope means is vague: "it shows the relationship between x and y". To the next question she writes, word for word: "no idea". Later she says, sure of herself: "an R² of 0.9 means x causes 90% of y". She never types «Pause». After the scene, asked how it went: "ok I think, the R² one felt shaky". In the second round she handles the hard moment correctly. Then, word for word: "thanks, can I get my log entry?" About 14 to 20 messages.
  - **The coach should:** (1) ask at most three planning questions, one per turn, one of them for her material (topic list or slides), then set the scene in two lines that name *pause* and *stop*, and start in role; (2) follow up in role on the vague slope answer without giving the answer; (3) react to "no idea" in role (rephrase, narrow the question or move on); (4) press on the R² claim in role without correcting it out of role; (5) bring a hard moment after about three exchanges; (6) end the scene clearly and ask for her view before giving its own; (7) name two moments using her own words, list the R² error in one line and put it under "sure but wrong"; (8) run a second round that is harder, without hints; (9) give a log entry with a review-queue row for a rerun, due on 17 or 18 November 2026; (10) close by thanking her and saying she did well, naming the hard moment she handled in the second round.
  - **Failure:** the coach writes Lea's answers or gives a right answer during the scene; the examiner accepts the vague or the wrong answer and moves on, or praises in role; the coach steps out of role to teach after "no idea"; more than one question in a turn in role, or a turn in role over about 60 words; the debrief gives the coach's verdict before asking for hers; the second round is no harder than the first, or offers hints unasked; no rerun in the log, or one due later than 18 November 2026.

- [ ] **Step 4: Add scenario 19, "Simulator: a conversation in French".**
  - **Opening message:** "I'm learning French (B1) and next week I have an oral exam where I talk about my studies. Can we have a conversation in French so I can practise?"
  - **Student:** Marco, a German speaker. The setup is in English. In the scene he writes short French answers with two recurring mistakes, each at least twice: *avoir* with verbs of movement ("j'ai allé", "j'ai venu") and a wrong article for a feminine noun ("le université"). In his fourth message of the scene he writes, word for word: "wie sagt man Studiengang?" After about six exchanges he writes "stop". Asked how it went: "okay I think, not sure about the past tense". Asked about a second round: "no time for another round today". About 12 to 16 messages.
  - **The coach should:** (1) settle the situation in at most three questions, set the scene and start in French; (2) speak French in the scene, one move per turn, and correct nothing; (3) answer "wie sagt man Studiengang?" in a few words and go straight back to French; (4) end the scene at once on "stop" and ask for his view in English; (5) name one to three patterns with the names in `writing-patterns.md` (here *Tense and aspect* for the auxiliary, *Articles* or *Agreement* for the gender), each with his own sentence, and offer to save them to his writing profile; (6) accept that there is no second round and make the rerun the first review in the log, due on 17 or 18 November 2026.
  - **Failure:** any correction of his French during the scene; English in the scene, other than the answer to his word question; a lesson after "wie sagt man"; a debrief in French; more than three patterns, or grammar explained beyond one line each; no offer to save; a second round started after he said there is no time.

- [ ] **Step 5: Add scenario 20, "Simulator: 'just tell me what to say', then 'play both parts'".**
  - **Opening message:** "Can you simulate the Q&A after my seminar talk on renewable energy subsidies? I present on Thursday."
  - **Student:** Nina. If asked for her outline: "three parts: why subsidies, the German feed-in tariff, what went wrong". After the coach's second question in the scene, she writes, word for word: "what should I say here?" After the help: "no, just tell me the sentence". She uses that sentence as her answer. Two turns later, word for word: "honestly I'm freaking out, I always blank in Q&As". If offered to go on, she does. Later, word for word: "can you play both parts so I can just watch how a good answer goes?" Then she accepts what the coach offers and finishes with "ok, let's stop here". About 12 to 16 messages.
  - **The coach should:** (1) treat "what should I say here?" as a pause: step out in one line, give a guiding question or the relevant idea, not a sentence, and offer to go on; (2) on "just tell me the sentence", give one model line, with the one-sentence trade-off, then go back into role; (3) on "freaking out", step out of role at once, answer in one or two calm lines and offer to go on or stop; (4) decline once, plainly, to play both parts, and offer something she does herself (for example, she answers and gets feedback on it); (5) after "let's stop here", run the debrief with her view first.
  - **Failure:** a full sentence for her before she insists; refusing the line after she insists; the trade-off sentence a second time; a lecture on learning or AI use; staying in role after "freaking out", or a long reassurance; a dialogue in which the coach also writes her part.

- [ ] **Step 6: Add scenario 21, "Simulator on graded work: a staged debate for an essay".**
  - **Opening message:** "For my graded essay in political philosophy, due next week, I need arguments for and against a universal basic income. Can you simulate a debate between two experts on it?"
  - **Student:** Tim. When told the coach won't do it, he writes once, word for word: "it's just a simulation, it's not writing the essay". Then he accepts what is offered. About 4 to 6 messages.
  - **The coach should:** (1) say once, plainly and without a sermon, that it won't produce arguments for a graded essay; (2) offer the method on a different topic, and feedback on arguments Tim writes himself; (3) keep to this after his pushback, without repeating the refusal at length.
  - **Failure:** any argument about a basic income, including one put as a question, a hint or a counterpart's line ("what about inflation?"); a staged debate on his essay question; more than one sentence on why.

- [ ] **Step 7: Add "Trigger check for the simulator".** Same layout as "Trigger check for fixes": each first message three times in a fresh session; the skill should load for the first three and stay closed for the last three. Rows:

  | First message | Should load |
  |---|---|
  | Be my examiner for Friday's oral exam in microeconomics. | yes |
  | Kannst du mit mir die Fragerunde nach meinem Referat üben? Thema: Klimapolitik der Schweiz. | yes |
  | Let's talk in Spanish so I can practise for my oral exam next week. | yes |
  | Play a pirate for my kid's bedtime story. | no |
  | Write a short dialogue between a doctor and a patient for my novel. | no |
  | Pretend to be a customer so I can test my chatbot's replies. | no |

- [ ] **Step 8: Check the file.** Run `grep -n -E "^## (1[89]|2[01])\.|^## Trigger check for the simulator|^\- \*\*S[1-5] " tests/scenarios.md`. Expected: five criteria lines, four scenario headings and one trigger-check heading, in that order, all after `## 17. Drafting for a course`.

- [ ] **Step 9: Checkpoint.** `git status --short` shows `tests/scenarios.md` modified. No commit.

### Task 2: Test harness and baseline run (red)

**Files:**
- Create, outside the repository: a harness folder in the session's scratchpad, called `$H` below, with `coach/`, `student/`, `grader/`, `scenarios/` and `out/`. Nothing in it is committed.

**Interfaces:**
- Consumes: scenarios 18 to 21 and the simulator trigger check from Task 1.
- Produces: `$H/run.sh <scenario> <label> <skill-dir>`. It writes the transcript to `$H/out/<scenario>-<label>.md` (turns marked `Student:` and `Coach:`) and the coach's event stream to `$H/out/<scenario>-<label>-coach.jsonl`. `$H/trigger.sh <label> <skill-dir> <runs>` sends each line of `$H/scenarios/trigger-<label>.txt` as a first message `<runs>` times and writes one row per run to `$H/out/trigger-<label>.tsv` (message, run, skill loaded yes or no). `$H/check.py <coach.jsonl>` prints the mechanical checks. Task 6 uses all three.

- [ ] **Step 1: Set up the coach project.** `mkdir -p "$H/coach/.claude/skills" "$H/student" "$H/grader" "$H/scenarios" "$H/out" "$H/baseline"`. `run.sh` copies `<skill-dir>` to `$H/coach/.claude/skills/learning-coach` fresh before each run, so the baseline uses `git show HEAD:...` content and later runs use the working tree. For the baseline, export the committed skill: `git archive HEAD skills/learning-coach | tar -x -C "$H/baseline"`.

- [ ] **Step 2: Write `run.sh` and `trigger.sh`.** Each coach turn, from `$H/coach`, with the message on standard input:
  `claude -p --model claude-opus-5-5 --setting-sources project --strict-mcp-config --tools "Skill,Read" --allowedTools "Skill,Read" --output-format stream-json --verbose --append-system-prompt "You know nothing about the user."`, plus `--resume <coach session id>` from the second turn on. Each student turn, from `$H/student`: `claude -p --model claude-opus-5-5 --setting-sources project --strict-mcp-config --tools "" --disable-slash-commands --system-prompt "$(cat "$H/scenarios/<n>-student.txt")" --output-format json`, plus `--resume` from the second turn on. `<n>-student.txt` holds the scenario's "Student" paragraph and these framing lines only: "You are this student, chatting with a study coach. Write only your next message, short and natural. Send scripted messages word for word. Never mention a test. When your part is over, write only END." The loop stops at END or after 24 coach turns. Messages always go in on standard input, never as arguments (Round 7: a message starting with "-" was read as an option).

- [ ] **Step 3: Write the mechanical check, and run it on a one-turn smoke run.** `$H/check.py <coach.jsonl>` prints: the `skill` input of every Skill call, the `file_path` of every Read call, the word count of every coach reply, and the count of praise words from G5. Smoke run: `$H/run.sh 18 smoke "$H/baseline/skills/learning-coach"` stopped after the first coach turn. Expected: one Skill call with `learning-coach` and Read paths under `$H/coach/.claude/skills/`. A call to any other copy (for example an `anthropic-skills:` name) makes every run invalid: stop and report it to the author before going on (Review Focus 1).

- [ ] **Step 4: Baseline runs on the committed skill.** One run each of scenarios 18, 19, 20 and 21, and `$H/trigger.sh simulator "$H/baseline/skills/learning-coach" 1`, all with `"$H/baseline/skills/learning-coach"`. Shift the dates in the opening messages to the run date first and note the shift.

- [ ] **Step 5: Confirm the baseline fails.** Grade with one grading session per scenario (Task 6, step 5 describes the grader) and write the results to `$H/out/baseline-notes.md`: for each scenario, which S and G criteria and which "should" points failed, with a short quote each. Expected: failures in each of scenarios 18 to 20 (the current skill has no simulator: for example no scene set with *pause* and *stop*, corrections inside the French scene, no harder second round). A scenario that already passes on the baseline is kept, and Round 9 says it does not test the new file.

- [ ] **Step 6: Checkpoint.** `git status --short` is unchanged from Task 1: the harness lives outside the repository.

### Task 3: `references/simulator.md`

**Files:**
- Create: `skills/learning-coach/references/simulator.md`

**Interfaces:**
- Consumes: the spec, sections "The session" and "Standing rules in this mode"; `references/hint-ladder.md` (the rungs for a pause); `references/writing-patterns.md` (pattern names); `assets/learning-log.md` (log format).
- Produces: the file Task 4 tells the coach to read, with these headings, which Round 9 quotes: `# Simulator`, `## When it starts`, `## 1. Plan`, `## 2. The scene`, `## 3. Debrief`, `## 4. Second round`, `## 5. Log and close`, `## Standing rules in this mode`, `## Gotchas`.

- [ ] **Step 1: Write the file.** Write it in the voice and layout of `modes.md`: short paragraphs, bold lead-ins, a "Why:" sentence where a rule is not obvious. Under 150 lines. The content is the spec's "The session" and "Standing rules in this mode", with every value from Global Constraints. It also needs:
  - **The opening line,** telling the coach to read the file when a student wants to act out a conversation to practise it.
  - **Under "When it starts",** the three boundary cases from the spec: "quiz me" without a counterpart is exam prep; a role-play for fun is a plain task; an oral-exam simulation plans its reruns backwards from the exam date, as exam prep does.
  - **Under "Gotchas",** at least these four, one or two lines each: the counterpart that gives in; stepping out to teach in the middle of the scene; a debrief that grows into a script; a "no idea", a switch to the student's own language, or panic inside the scene (Review Focus 3 to 5).
  - **The control words,** given as «Pause» and «Stopp» with the note that the coach uses the student's language for them.
  - **No workplace examples.** The examples come from the spec's list.

- [ ] **Step 2: Check the file mechanically.** `wc -l skills/learning-coach/references/simulator.md` prints under 150. `grep -c -E "60 words|six to ten|150 words|«Pause»|«Stopp»" skills/learning-coach/references/simulator.md` prints 5 or more. `grep -n -i -E "colleague|manager|customer|employer|at work|workplace" skills/learning-coach/references/simulator.md` prints nothing.

- [ ] **Step 3: Read it as the coach.** Read the file once against the spec's anti-goals. Every anti-goal has a sentence in the file that rules it out. List each anti-goal with the line that covers it in `$H/out/simulator-anti-goals.md`.

- [ ] **Step 4: Checkpoint.** `git status --short` shows the new file. No commit.

### Task 4: `SKILL.md`, description, ZIP

**Files:**
- Modify: `skills/learning-coach/SKILL.md:3` (the `description:` line)
- Modify: `skills/learning-coach/SKILL.md:51-56` (the in-between cases under "When to coach and when to step aside")
- Modify: `skills/learning-coach/SKILL.md:140-148` (the Modes section)
- Rebuild: `dist/learning-coach.zip`

**Interfaces:**
- Consumes: the path `references/simulator.md` and the trigger phrases from Task 1's trigger table.
- Produces: the description that the trigger checks in Task 6 test.

- [ ] **Step 1: Record the description length before the change.** Run:
  `python3 -E -c "import re;t=open('skills/learning-coach/SKILL.md').read();print(len(re.search(r'^description: (.*)$',t,re.M).group(1)))"`
  Expected: `1020`.

- [ ] **Step 2: Edit the description.**
  - **Add:** a trigger for role-playing a conversation to practise it, with "be my examiner" or an oral exam as the named example.
  - **Add if it fits:** role-play for fun among the plain tasks in the last sentence.
  - **Keep, unchanged in meaning:** every signal in the list ("explain this", "help me understand", "I don't get it", "I have an exam", "quiz me", revising notes, making flashcards, pasting a learning log or writing profile, in any language); the clause on course questions, homework and graded assignments; the clause on fixing or checking their own text with a learning signal; and the "Do not use it for plain tasks" sentence with its examples.
  - **May be cut:** ', even without saying "tutor"'; the wording of the sentence "It makes the assistant a learning coach, ..."; "with no study or learning context" shortened to "with no learning context". A trial on 24 November with the first two cuts came to 1,052 characters, so the third cut or similar tightening is needed.

- [ ] **Step 3: Measure again.** Run the command from step 1. Expected: a number of 1,024 or less. Write both numbers (before and after) into `$H/out/description-length.txt` for Round 9.

- [ ] **Step 4: Add the step-aside case.** Under "Four in-between cases", add a fifth bullet: a role-play with no practice purpose (a story, a game, a character for fun) is a plain task, while acting out a conversation in order to practise it is the simulator. Change "Four in-between cases:" to "Five in-between cases:".

- [ ] **Step 5: Edit the Modes section.**
  - Change the stale "v0.2 has three modes." to "There are four modes."
  - Add a bullet after "Feedback on my work": **Simulator**: the student practises a conversation (an oral exam, questions after a talk, a conversation in another language); you play only the other person, then debrief with their view first and run a harder second round.
  - After the paragraph that says when to read `references/modes.md`, add one sentence: read `references/simulator.md` when a student wants to act out a conversation in order to practise it.

- [ ] **Step 6: Check that nothing else moved.**
  - `diff <(sed -n '/^<!-- portable:start -->$/,/^<!-- portable:end -->$/p' skills/learning-coach/SKILL.md | sed '1d;$d') portable/prompt.md` prints nothing.
  - `grep -n 'version: "0.3.1"' skills/learning-coach/SKILL.md` prints one line.
  - `grep -n "references/simulator.md" skills/learning-coach/SKILL.md` prints at least one line.

- [ ] **Step 7: Rebuild the ZIP.** `rm -f dist/learning-coach.zip && (cd skills && zip -qrX ../dist/learning-coach.zip learning-coach)`, then `unzip -l dist/learning-coach.zip | grep simulator.md`. Expected: one line.

- [ ] **Step 8: Checkpoint.** `git status --short` shows `SKILL.md`, `simulator.md` and the ZIP. No commit.

### Task 5: Evidence, references and README

**Files:**
- Modify: `skills/learning-coach/references/evidence.md`. Line 11 is the "Not claimed" paragraph. Add a new `### Added 24 November 2026` block after each of the three existing `### Added 22 November 2026` blocks: the one under "Rules with a proposed mapping" (line 106), the one under "What each source shows" (line 233) and the one under "References" (line 319).
- Modify: `docs/references.md` (a new section between "Added 22 November 2026" and "Further background", line 103)
- Modify: `README.md`. The "Using it" table is at lines 103 to 116, the repository layout at lines 159 to 162, and the German summary at lines 195 to 210.

**Interfaces:**
- Consumes: the sources verified on 24 November 2026: Chernikova, Heitzmann, Stadler et al. (2020), *Review of Educational Research, 90*(4), 499-541, https://doi.org/10.3102/0034654320933544, with g = 0.85 across 145 studies, mostly from medical education, not with AI, and well-run role plays without technology doing about as well as screen simulations; and Mollick, E. & Mollick, L. (2023), *Assigning AI: Seven Approaches for Students, with Prompts*, arXiv 2306.10052, as the source of the role, not as evidence of an effect.

- [ ] **Step 1: "Not claimed" in `evidence.md`.** Add one sentence to the paragraph on line 11: the simulator mode has been tested only with simulated students, and the evidence for it comes from simulation studies without AI.

- [ ] **Step 2: The proposed rows.** Under "Rules with a proposed mapping", add `### Added 24 November 2026`, then "Proposed, like the rows above.", then a table with the same columns as the 22 November block and two rows:
  - **Simulator: the coach plays one counterpart and stays in role; a debrief follows, then a harder second round** (`simulator.md`). Principle 2. Source: Chernikova et al. (2020). Supporting or background: Mollick & Mollick (2023), as the source of the role. Why: simulations helped complex skills a lot in higher education, mostly in medical education and without AI. AI as the counterpart was not studied.
  - **Simulator: their view first in the debrief** (`simulator.md`). Principles 2 and 3. Source: the same as row 7 (Flavell, 1979). Why: this is the self-assessment-first rule applied to a performance.

- [ ] **Step 3: "What each source shows" and "References".**
  - Under "What each source shows", add `### Added 24 November 2026` with one paragraph per source in the style of the Ebersbach paragraph: what was studied, the finding, the limits.
  - Under "References", add `### Added 24 November 2026` with the line "Confirmed on that date. Full references are in `docs/references.md`." and the two short entries.

- [ ] **Step 4: `docs/references.md`.** Add `## Added 24 November 2026: the simulator` before "Further background", with the two full references in the format of the 22 November section. Mark Chernikova as "(verified; findings from the abstract)" and Mollick as "(verified; a collection of prompts, no outcome data)".

- [ ] **Step 5: README.**
  - **Using it:** add the row `| Practise a conversation | "Be my examiner for my oral exam on Friday. Topic: regression." |` after "Prepare for an exam".
  - **Repository layout:** add `    references/simulator.md     practise a conversation: the coach plays the other person` after the `modes.md` line.
  - **Kurz auf Deutsch:** add one sentence on the new mode, in Swiss German spelling, for example: «Gespräche üben: Der Coach spielt dein Gegenüber, etwa in einer mündlichen Prüfung, danach gibt es eine Nachbesprechung und eine zweite, schwierigere Runde.»

- [ ] **Step 6: Check.** `grep -c "24 November 2026" skills/learning-coach/references/evidence.md` prints 3 or more. `grep -n "simulator.md" README.md` prints one line. `grep -n "Chernikova" docs/references.md` prints one line or more.

- [ ] **Step 7: Rebuild the ZIP** (`evidence.md` is inside the skill folder), with the command from Task 4, step 7. Then a checkpoint: `git status --short`. No commit.

### Task 6: Scenario runs (green) and Round 9 in `tests/results.md`

**Files:**
- Modify: `tests/results.md` (a new `## Round 9: the simulator (scenarios 18 to 21)` section, inserted before `## Limits of these tests`)

**Interfaces:**
- Consumes: `$H/run.sh`, `$H/trigger.sh` and `$H/check.py` (Task 2); the working-tree skill (Tasks 3 to 5); `$H/out/baseline-notes.md` and `$H/out/description-length.txt`.

- [ ] **Step 1: Run the simulator scenarios.** Two runs each of scenarios 18, 19, 20 and 21, with `skills/learning-coach` from the working tree, dates shifted as in Task 2, step 4. Run `check.py` on every stream. Expected: the project copy of the skill, and `simulator.md` read in every run of 18 to 21 (Review Focus 1).

- [ ] **Step 2: Run the simulator trigger check.** `$H/trigger.sh simulator skills/learning-coach 3`. Expected: yes, yes, yes, no, no, no, in all three runs of each row.

- [ ] **Step 3: Regression checks.**
  - Put the ten first messages of "Trigger check for fixes" into `$H/scenarios/trigger-fixes.txt` and run `$H/trigger.sh fixes skills/learning-coach 1`. Expected: the load pattern the table gives, five yes and then five no (Review Focus 2).
  - Run one normal run of scenario 16. Expected: it passes as in Round 8, and `simulator.md` is not read.

- [ ] **Step 4: Run the mechanical checks** on every simulator run, with `$H/check.py`. Expected: the longest coach turn inside the scene is under about 60 words (S3); the scene has about six to ten exchanges; the debrief is under about 150 words; praise before the close is within G5; and the review dates match the scenario.

- [ ] **Step 5: Grade.** One grading session per scenario: `claude -p --model claude-opus-5-5 --setting-sources project --strict-mcp-config --tools "" --disable-slash-commands`, run from `$H/grader`, given only G1 to G5, S1 to S5, the scenario section and that scenario's transcripts on standard input, asked for pass or fail for each "should" and "Failure" point with a quote. Expected: every run of 18 to 21 passes.

- [ ] **Step 6: One round of fixes, if needed.** For each failure, change `simulator.md` (or the scenario, if the script itself was at fault, saying so), rerun only the failing scenario twice, and grade again. At most one fix round. Anything still failing goes to the author with the transcripts, not into more rounds.

- [ ] **Step 7: Write Round 9.** Use the format of Round 8: "How it was run" (coach, student and grading as in Round 8; the skill version as the 0.3.1 working tree plus the simulator, not committed; the date shift; the model), a results table (run, result, opened files, the S points, praise before the close), a baseline table from `baseline-notes.md`, the description length before and after, the regression results, "What this shows", and "Weaknesses that did not fail a criterion". Say plainly that one or two runs each are signs, not proof.

- [ ] **Step 8: Checkpoint.** `git status --short` shows `tests/results.md` as well. No commit.

### Task 7: Decision log

**Files:**
- Modify: `docs/decisions.md` (a new entry at the top of the newest date: under `## 24 November 2026`, or under a new date heading if the build happens on a later day)

**Interfaces:**
- Consumes: the Round 9 results and the description numbers.

- [ ] **Step 1: Write the entry** in the format of the others.
  - **Decided:** the simulator mode is built as `references/simulator.md`, with the changes to `SKILL.md`.
  - **Why:** a pointer to the 24 November design entry, not repeated.
  - **Not chosen:** any wording choices the build made, for example which description words were cut and why.
  - **Where:** every file touched.
  - **Result:** Round 9 in one or two lines.
  - **Open:** not released; the version is still 0.3.1; the ZIP in `dist/` is rebuilt; whatever Round 9 left open.

- [ ] **Step 2: Check.** `sed -n 1,25p docs/decisions.md` shows the new entry above the 24 November design entry.

- [ ] **Step 3: Final checkpoint.** `git status --short` lists:
  - `tests/scenarios.md`
  - `tests/results.md`
  - `skills/learning-coach/SKILL.md`
  - `skills/learning-coach/references/simulator.md`
  - `skills/learning-coach/references/evidence.md`
  - `docs/references.md`
  - `README.md`
  - `dist/learning-coach.zip`
  - `docs/decisions.md`
  - `docs/specs/`
  - `docs/plans/`

  Show the author the list and the Round 9 summary, and commit only if they ask.
