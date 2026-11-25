# Decisions

What we decided about the learning coach, and why. Newest first. Add an entry whenever a decision changes how the coach behaves, what goes in the repository, or how it is tested.

Each entry says what was decided, why, what was considered and not chosen, and where the decision lives in the repository.

---

## 25 November 2026

### Release 0.4.0: the simulator and input first

- **Decided:** at the author's request, version 0.4.0 is released. It ships the simulator (practising a conversation with one counterpart), input first for a student who is new to a topic, and the graded-work refusal that keeps to its reason after pushback. The paste-in prompt ships the new step 2.
- **Why:** on the final text the simulator scenarios hold 92 to 100% of their points and no run failed on its own (Round 12). Input first passes every run in the skill (Round 10).
- **Not chosen:**
  - Releasing input first alone and parking the simulator on a branch, as was done with the study group draft.
  - Keeping the old step 2 in the paste-in prompt. The new one fixes what the tester reported, although it still tends to ask two questions in one turn.
- **Shipped with known weaknesses:** in one of two graded-debate runs an argument still slipped in as a question; in the paste-in prompt, the input-first step asks two questions in one turn and explains at more than 100 words in the tester's case.
- **Where:** `SKILL.md`, version 0.4.0; `dist/learning-coach.zip` (checked to match the skill folder); the GitHub release v0.4.0; README, the release example.

### A two-sentence refusal is allowed in scenario 21

- **Decided:** at the author's request, a refusal of two short sentences is not a failure in scenario 21. The Failure point now reads "A refusal of more than two short sentences, or a new reason after his pushback."
- **Why:** the coach's refusal ("Since this essay is graded, I won't write a debate on UBI. The arguments need to come from you.") reads like the skill's own example, and it failed every run under "more than one sentence on why".
- **Result:** graded again, the two runs with the rule to keep to the refusal after pushback hold 11 of 12 points, and the two runs without it miss exactly that point. Still open: an argument slipping in as a question, in one of the two runs.
- **Where:** `tests/scenarios.md`, scenario 21; `tests/results.md`, Round 12.

### The simulator is measured point by point

- **Decided:** at the author's request, simulator runs are measured point by point. Each "should" point met, each "Failure" point that did not occur and each S point that held counts as one point held. The main figure is the share of points held, per run, per scenario and per criterion across runs. Three points still fail a run on their own: the coach writes the student's lines, plays both parts, or supplies content or arguments for graded work (proposed in the parent session and accepted there by the author). The all-or-nothing verdict stays as a second figure. Points that could not be tested are left out of the count.
- **Why:** the runs are long, and one slip anywhere failed a whole run. After two more rounds of fixes, 1 of 6 and then 1 of 8 runs passed all-or-nothing, although most points held in most runs. The all-or-nothing figure hid both the progress and where the remaining problems are.
- **Not chosen:** more rounds of fixes judged all-or-nothing only.
- **Where:** `tests/scenarios.md`, the note under S1 to S5; `tests/results.md`, Round 12. The grading sessions now end with a fixed block of per-point results.
- **Result:** Round 12. On the current text, scenarios 18 to 20 hold 95 to 100% of their points, and 5 of 8 runs hold every point. By criterion: S1 6 of 6, S2 5 of 6, S3 6 of 6, S4 6 of 6, S5 2 of 2. No run failed on its own. Scenario 21 holds 83%. Its one failing point, "more than one sentence on why", failed in every run. A one-sentence-reason rule added to the graded-work rule in `SKILL.md` did not change that, because the refusal still runs to two short sentences, close to the skill's own example.
- **Open, for the author:** whether scenario 21 should count a two-sentence refusal as a failure.

### Two more rounds of fixes to the simulator

- **Decided:** at the author's request ("Weiter nachbessern"), `simulator.md` got two more rounds of fixes aimed at the failures of Round 9, and the graded-work rule in `SKILL.md` got one more sentence. The fixes, in `simulator.md`:
  - no compliments and no "Fair enough"
  - a turn in role is at most two sentences by one person
  - the third question is the hard moment
  - never supply the missing answer
  - one calm sentence for distress
  - round two opens with the hard moment, without cues
  - no correction by repeating the sentence correctly
  - "sure but wrong" is named in the debrief
  - acknowledgements in the language of the scene

  In `SKILL.md`: feedback on graded work names no arguments the student has not made, not even as a question.
- **Why:** Round 9 left scenarios 18, 20 and 21 failing, mostly on two points in one turn, on giving in or praising in role, and on hints in graded feedback.
- **Result:** Round 11. 1 of 6 runs passed in round 2 and 1 of 8 in round 3. Each fix removed its target in most runs, but a different single slip then failed the run. Scenario 3 still passes. Scenario 11 failed once, with no obvious link to the change.
- **Open, for the author:** keep going round by round, or measure the simulator by the share of criteria met per run, which shows the progress that the all-or-nothing rule hides. The last fix (acknowledgements in the language of the scene) has not been run yet. Nothing is committed or released.

### Input first is built: it works in the skill, not yet in the paste-in prompt

- **Decided:** input first is built as designed on 24 November (`docs/specs/2026-11-24-input-first-design.md`, plan `docs/plans/2026-11-25-input-first.md`).
  - In `SKILL.md`, step 2 is now "Attempt first, or input first". A student who is new to the topic gets a short explanation with an example, then one question, one and not two, that makes them use it. "Explain it to me first" is treated the same way. A student with a basis keeps attempt-first.
  - Step 1 asks only what they know, one question, when the request already shows the goal. "I don't know" counts as not yet stuck only for a student with a basis.
  - `hint-ladder.md` says the ladder is for students with a basis.
  - The core loop and `portable/prompt.md` say: "Max 3 questions (1 if new to it)" and "Know the basics? They try first. New to it? Explain briefly with an example, then ONE question to apply it."
  - `evidence.md` and `docs/references.md` add Kalyuga et al. (2003), confirmed on APA PsycNet.
- **Why:** the tester's feedback (too many questions, too little input on linear regression). The baseline reproduced it: on the skill, a request to guess and four questions before the explanation in reply 5.
- **Choices made while building:** to stay within 1,500 characters, the core loop lost "one at a time" in step 4, "a question on" in step 3 and "first" after "test case". In the fix round it also lost "first" in "they draft first", "entry" in "short log entry", "The goal is" (now "Goal:"), the commas in the confidence scale, and "sentence" in "one sentence on the trade-off" (now "one line"). The block is at 1,498.
- **Not chosen:** more rounds of fixes; the plan allowed one.
- **Result:** Round 10. In the skill, scenario 22 passes: the normal run 3 of 3, explain-first after the fix round, and the basis run. The paste-in prompt, which the tester used, still fails both normal runs: two questions joined with "And" before and after the explanation, and explanations of 110 to 135 words. Scenario 1 on the paste-in prompt suggests the rule is applied too widely: a student who had the topic in class got the explanation first. The scenario 2 failure on the skill happens on the old text too.
- **Final review:** a fresh reviewer found five things to fix, all done.
  - The core loop now separates the mode ("learn or exam prep") from the order ("1 if never had it", "Never had it? Explain ...").
  - Step 2 reads "new" from the answer to the prior-knowledge question. Someone who had the topic in class counts as having a basis.
  - A plain "can you explain X?" gets the prior-knowledge question, and a novice who is stuck after the explanation gets the hint ladder.
  - One "I don't know" about a detail gets a guiding question.
  - My cut "one line on the trade-off" was reverted to "one sentence", because scenario 2 on the paste-in prompt regressed with it. The block is at 1,497.
  - On the final version, the skill passes scenario 22 in all three runs and scenario 1. The paste-in prompt passes the basis and explain-first runs and scenarios 4 and 7. It still fails the tester's case (two questions joined around the explanation), and in scenario 1 a student with a basis still got the full explanation after her first error.
- **Open, for the author:**
  - **The paste-in prompt has no room left.** Options: accept the shorter behaviour; use a longer prompt where the tool allows one, such as a ChatGPT project or custom GPT with room for more instructions; or rewrite the block from scratch.
  - **"New to the topic" on the paste-in prompt:** sharpen it so that someone who had the topic in class is not treated as new.
  - **Release:** not released, nothing committed.

## 24 November 2026

### Input first when the student is new to a topic

- **Decided:** at the author's request, the student's prior knowledge decides the order in step 2. A student who is new to the topic gets a short explanation with an example first, then one question that makes them use it. A student with a basis keeps attempt-first and the hint ladder. "Explain it to me first" is honoured at once, followed by a question. Not built yet.
- **Why:** a tester asked about regression and, early on, got question after question when she wanted an explanation ("too many questions, too little input"). Under today's rules, "I don't know" is not yet stuck, so a student with no basis is asked to guess and then climbs the hint ladder before any input. Novices learn more from an explanation or a worked example first (the expertise-reversal effect, to be verified).
- **Not chosen:**
  - A switch "explain first" alone. The tester would not have known to use it.
  - Complexity levels per question. What matters is the distance between the question and this student's prior knowledge, and the coach rarely knows the course.
- **Later:** a "Who I am" line in the learning log (programme, semester, prior knowledge), so the coach need not ask again.
- **Where:** the design is in `docs/specs/2026-11-24-input-first-design.md`.

### A two-part question on one point counts as one move

- **Decided:** at the author's request, a question with two parts about the same point counts as one move in the simulator ("What is the residual, and what does its sign tell you?"). Questions about two different points still count as two, and the second waits for the next turn.
- **Why:** an examiner asking for a value and its meaning in one breath is natural, and the turn stays short. Counted strictly, almost every run of scenarios 18 to 21 failed S3, although the counterpart did what the rule is for: one thing at a time, in a short turn.
- **Not chosen:** tightening the rule again. It was already explicit, with examples, and the pattern persisted in English and in French.
- **Where:** `simulator.md`, The scene, "One move per turn"; `tests/scenarios.md`, the note under S1 to S5 and the Failure list of scenario 18; `tests/results.md`, Round 9.
- **Result:** under the new rule 4 of 9 runs of scenarios 18 to 20 pass, at least one per scenario. The remaining failures vary from run to run. A new one in scenario 19: the counterpart repeated a wrong sentence in the correct form ("à Zurich"), which counts as a correction in the scene. Open: whether that kind of echo is allowed, and how to make the runs more consistent.

### The simulator is built, and three scenarios still fail

- **Decided:** the simulator mode is built as `references/simulator.md`, following the design of the same day (`docs/specs/2026-11-24-simulator-mode.md`) and its plan (`docs/plans/2026-11-24-simulator-mode.md`). `SKILL.md` gains a Modes bullet, a sentence saying when to read the file, a step-aside case (a role-play for fun is a plain task) and a trigger in the description. The graded-work rule now also excludes lines in a role-play or debate on the student's topic.
- **Why:** see the design entry below. The baseline without the file failed all four simulator scenarios: it ran a quiz in place of a scene, corrected French mid-conversation and played both parts.
- **Choices made while building:**
  - The description went from 1,020 to 1,018 characters. Cut: ', even without saying "tutor"', and shorter wording in three places ("or wants homework", "with no learning context, where they want a result", the sentence on what the coach does).
  - The debrief limit is about 120 words, not the design's 150, because G2 allows about 120 for any turn and both graders failed the longer debriefs.
  - After round 1, `simulator.md` spells out one question per turn, neutral acknowledgements, waiting for the student's view, the pattern names from `writing-patterns.md`, a harder second round and the rerun as a row inside the log.
- **Not chosen:** more rounds of fixes. The plan allowed one, so the remaining failures come to the author.
- **Where:** `references/simulator.md`; `SKILL.md`; `references/evidence.md`; `docs/references.md`; README; `tests/scenarios.md` (scenarios 18 to 21, criteria S1 to S5, a trigger check); `tests/results.md`, Round 9; `dist/learning-coach.zip`, rebuilt.
- **Result:** Round 9. The mode does what the baseline could not: a scene in role, no answers given away, the student's view first, a harder second round, and in another language no corrections in the scene and the pattern names from `writing-patterns.md`. The trigger checks and scenario 16 behave as before. But under the rule that a failed S point fails the run, no simulator scenario passes yet. The main cause is two questions in one turn (S3), in almost every run. Scenario 20 also shows the counterpart giving in or praising in role (S2) and reassurance that runs to three or four sentences. In 21 basic-income arguments slipped in as hints while giving feedback.
- **Final review:** a fresh reviewer found four things to fix, all done and tested before and after. Scenario 20 had been described too kindly. The S criteria now fail a run (`tests/scenarios.md`). The graded-work clause is limited to graded written work, so practising a graded talk stays allowed. `simulator.md` no longer names scenario 19's mistakes, and scenario 19 now uses new ones (*depuis*, *en* with a city), which the coach named exactly.
- **Open, for the author:**
  - **S3, two questions in one turn:** tighten the rule again, or count a two-part question on one point ("What is the residual, and what does its sign tell you?") as one move.
  - **S2, politeness in role:** decide whether "Thanks, that was clear." from an examiner counts as praise.
  - **20:** tighten the rule, or loosen the scenario to a word limit for the calm lines.
  - **21:** the graded-work rule in `SKILL.md` needs a stronger fix of its own. `simulator.md` is not read in that scenario, and the baseline failed the same way.
  - **Debrief length:** about 120 words now, against the design's 150. Either 150 with the debrief added to G2's exceptions, or the patterns moved to a second turn.
  - **Release:** not released; the version is still 0.3.1. The skill changes are in the working tree, not committed.

### The simulator covers conversations, and each role gets its own reference file

- **Decided:** at the author's request, the Simulator is built first and covers conversations with one counterpart: an oral exam, questions after a presentation, a seminar discussion, a conversation in a foreign language, a patient or client conversation in programmes that train those. The coach plays only the other person. The author also confirmed one skill with one reference file per role (`references/simulator.md` first), which the coach reads only when that role runs.
- **Why:** one counterpart is one mechanism that stays realistic and can be tested. A file per role keeps `SKILL.md` short, and an exam-prep session does not read the role-play instructions.
- **Not chosen:**
  - Case simulations in which the coach narrates a situation and the student makes decisions. They are broader and closer to the prompt sheet, but the coach plays narrator and world at once, slips into explaining more easily and is harder to test. Possible later as an extension.
  - Only oral exams and presentations. This overlaps most with exam prep.
- **Where:** the design is in `docs/specs/2026-11-24-simulator-mode.md`. Nothing is built yet.

### Release 0.3.1: the exam guess step, without the study group draft

- **Decided:** at the author's request, version 0.3.1 is released with the exam guess step (22 and 23 November). The study group draft (17 November) is parked as backlog on the branch `study-group-draft`. It is not on `main` and not in the ZIP.
- **Why:** the guess step passed its tests. The study group draft has not been tested at all, and every release asks students to replace the skill, so the draft waits until it is tested.
- **Not chosen:** keeping the guess step back until the study group is tested and releasing both together; shipping the study group marked as a draft.
- **Tested:** the round 8 runs used the working tree with the draft in it. One more run of scenario 16 was made with the skill unpacked from the 0.3.1 ZIP itself, and it passed (`tests/results.md`, Round 8, "Check of the 0.3.1 release build").
- **Where:** `SKILL.md`, version 0.3.1; `dist/learning-coach.zip`; the GitHub release v0.3.1; the branch `study-group-draft`.
- **Open:** before the study group comes back, it needs the scenarios named in its entry on that branch and a test run. The points left open on 23 November still stand.

### The roles from the SBB prompt sheet become modes of the same skill

- **Decided:** at the author's request, the five AI roles from the prompt sheet «Lernprompts» (Team Lernen, Bern, August 2026) are to be added as modes of the learning coach (Weg 1). They are not a separate skill and not a role menu at the start. Trainer:in is already covered by "Learn something new". Simulator and Coach would be new modes. Lernende:r would build teach-back in both directions: the student explains and the coach asks naive questions, or the coach explains with one or two planted mistakes and the student finds them. Mentor:in would extend "Feedback on my work" to feedback on content (plans, concepts, messages). Nothing is built yet.
- **Why:** the standing rules (attempt first, "just tell me", graded work, praise, the log) then apply to every role without copies, and students install one skill. The same reason kept the study group from becoming its own skill.
- **Not chosen:**
  - A role menu at the start, as in the sheet. It is a form-like first question, against the rule for the first reply.
  - A separate skill for practising and coaching, or five role skills under an umbrella skill. The rules would be copied and drift, the skills would compete to load, there would be several ZIPs to install and update, and one skill cannot reliably load another.
  - Building for work as well. The description is nearly full, each audience needs its own test scenarios, and the tools the sheet names for employees may not load skills at all.
- **Audience, decided by the author the same day:** the skill stays for studying and learning, not for the job. The sheet's workplace examples (a new regulation, shift planning, a critical talk with a colleague) are not taken over. Examples for the new roles come from study: an oral exam, a presentation, a seminar paper, being stuck on how to start an assignment.
- **Found along the way:** the Mentor, Trainer and Lernende prompts in the sheet are close translations of the example prompts in Mollick & Mollick (2023), "Assigning AI: Seven Approaches for Students, with Prompts" (arXiv 2306.10052). The sheet does not cite it. The Coach prompt is the sheet's own; the Simulator prompt was not compared. The paper is a source for the roles, not evidence that they work.
- **Claude's calls, for the author to confirm:** one reference file per role in place of more sections in `modes.md` (confirmed by the author the same day); build order Simulator, Lernende:r, Mentor:in, Coach. Candidate sources, checked: Chernikova et al. (2020) for simulations, Chase et al. (2009) for learning by teaching, Gollwitzer & Sheeran (2006) for if-then plans.
- **Where:** not in the repository yet. The comparison was shown in a slide deck made in Claude and kept outside the repository, since reworked into the status report «Learning Coach: Statusbericht».
- **Open:** the skill description has 4 characters left (1,020 of 1,024), so new triggers mean shortening others; the paste-in prompt has 2 left (1,498 of 1,500), so the roles will not fit there; what "able to do it without AI" means for the Coach.

## 23 November 2026

### No examples and no praise when asking for the exam guess

- **Decided:** in exam prep, the coach asks for the student's guess at the exam questions without example questions, because an example tends to become the guess. It takes the guess in a plain line, without praise. In test scenario 16, Jonas's scripted guess now names substitutes ("what happens when the price of a substitute goes up"). A failure point was added for example questions in the ask.
- **Why:** in the first round 8 runs, the coach suggested sample questions in the ask ("find the equilibrium"). One sample became the coach's own added question, and another was almost a pre-test question. Both runs where the student guessed also said "Those two are good guesses", which put each run at the G5 limit. Two of three runs never asked about substitutes, so the planted miss could not happen.
- **Not chosen:** requiring the pre-test to cover a topic outside the guess list. The skip run with no guess showed the same four pre-test questions, so the guess step did not narrow the pre-test. A rule for it would have fixed a problem the test did not show.
- **Result:** in the rerun on 23 November, all three runs passed. No run gave examples or praised the guess, and the planted miss came up in all three and came back as a variant due on 24 or 25 November. One run each, three in all.
- **Where:** `modes.md`, Exam prep; `tests/scenarios.md`, scenario 16; `tests/results.md`, Round 8.
- **Open:** two runs still put an example in the format question ("calculations (like finding equilibrium price from equations)"), one step before the guess. Scenario 4 also opens with "quiz me", and its student script does not cover the guess. Not released. The ZIP in `dist/` has been rebuilt. (Released in 0.3.1 on 24 November, see above.)

## 22 November 2026

### Exam prep starts with the student's guess at the exam questions

- **Decided:** in exam prep, before the pre-test, the coach asks which two or three questions the student expects. This takes the place of the question about the topic list, so planning still needs at most three questions. The coach then adds at most two likely questions the student left out, each with a few words on why, and says these are guesses from the material, not knowledge of the exam, without ranking them. The pre-test is drawn from the combined list. A student who would rather not guess ("no idea", "just quiz me") goes straight to the pre-test.
- **Why:** the idea comes from an Instagram reel with five custom ChatGPT study commands. One of them, "/questionpredictor", reads the student's notes and lists the most likely exam questions. Having the student guess first keeps the thinking with them, like "their summary before yours" and student-written cards. Generating questions helped recall a week later about as much as answering them did (Ebersbach, Feierabend & Nazari, 2020), and guessing what an exam will ask is something students can do on their own before the next one.
- **Not chosen:**
  - The coach predicting the questions from the notes, as in the reel. That does the thinking for the student, and a ranked list of the "most likely" questions claims a knowledge of the exam that the coach does not have.
  - The reel's other four commands. The check from memory already does what "/quizme" does. Notes and study guides written by the AI ("/stickynotes", "/studyguide") go against "their summary before yours", and the one-page topic card is parked. A story-style retell in the student's words (from "/storymode") was suggested but is not part of this change.
- **Where:** `modes.md`, Exam prep; `SKILL.md`, Modes; `evidence.md`, Added 22 November 2026 (row, sources and references); `docs/references.md`; `tests/scenarios.md`, scenario 16.
- **Tests:** scenario 16 now includes the guess step (Jonas's guess is scripted word for word) and a skip run ("no idea, just quiz me"), with three new failure points. In round 8 (`tests/results.md`) all three runs passed, and the step behaved as written each time. Only one run tested the planted miss, because the other two never asked about substitutes.
- **Open:** the coach gives example questions when it asks for the guess, which can steer the guess, and it praised the guess in both runs. Scenario 16's planted miss depends on the coach choosing a substitutes question. (These three were fixed on 23 November, see above.) Scenario 4 also opens with "quiz me", and its student script does not cover the guess. Not released. The ZIP in `dist/` has been rebuilt.

## 17 November 2026

### The prompt sheet PDF stays out of the repository

- **Decided:** a one-page PDF of example prompts (in German, made from the table under "Using it" in the README) is not kept in `dist/` or anywhere else in the repository. If students should get it, it goes on a GitHub release next to `learning-coach.zip`.
- **Why:** the PDF copies the README table. When a prompt in the README changes, the PDF goes out of date and nothing catches it. `portable/prompt.md` has a diff check for this problem; the PDF would have none.
- **Not chosen:** committing the PDF to `dist/`.
- **Where:** nothing in the repository. The prompts themselves are in the README, under "Using it".

### First release, and the install link points to it

- **Decided:** version 0.3.0 is the first GitHub release, with `learning-coach.zip` attached. The README's download links (English and German) now point to the ZIP in the latest release (`releases/latest/download/learning-coach.zip`), no longer to `dist/` on `main`.
- **Why:** several sessions commit to `main` during a day, and the ZIP in `dist/` can be rebuilt in the middle of a change. Students should get a version that was tested and released, not whatever is on `main` at the time.
- **Not chosen:** a link to a fixed version (`releases/download/v0.3.0/...`), because it would need a README edit for every release.
- **Consequence:** a change reaches students only with a new release. The README's maintainer section says how to publish one.
- **Update steps:** the README tells students to delete the old skill before uploading the new ZIP, unless the menu offers to replace it. Anthropic's help article does not say whether an upload with the same name replaces a personal skill, and two installed versions would compete for the same requests. Claude Code users pull, remove the old copy and copy the folder again. To check: what the Skills page actually offers, then shorten the steps.
- **Where:** README, Install, the German summary and the maintainer section.

### Ideas for coming back to a topic parked for a later app

- **Decided:** a harder question after a right answer, a one-page topic card and calendar reminders are not built in the skill for now; they are parked in a local backlog for a possible learning coach app.

### Praise rule made concrete

- **Decided:** "Exactly", "Spot on", "Good catch", "Great", "Solid" and the same words in the student's language ("Genau", "Super") count as praise, not as confirmation. Before the warm close, praise at most twice in a whole session, and only for a moment that earns it. Never praise a wrong or half-right answer; say plainly which part is right instead.
- **Why:** in round 7, "a couple of times a session at most" did not hold. The long session had about a dozen praise phrases, and one German run said "Guter Ansatz, du bist nah dran" to a wrong answer. Naming the words and giving a number makes the rule something the coach can follow and a grader can count.
- **Not chosen:** no praise at all before the close (too cold); the same limit of three as test criterion G5. The skill aims for two, and G5 keeps three as the failure line, one above the target.
- **Also changed:** G5 now names "good catch" and praise in the student's language, and praise for a wrong or half-right answer fails it on its own. The paste-in prompt keeps "rare praise" because it has two characters to spare; its runs passed G5 in 4 of 5.
- **Where:** `SKILL.md`, Tone and pace; `evidence.md`, Tone row; `tests/scenarios.md`, G5.
- **Result:** on v0.3, scenarios 3 and 8 now pass G5 (1 and at most 2 praise phrases, both were 4). Scenario 1 is at 3 or 4, depending on one borderline phrase. One run each.

### One definition of "the check went well"

- **Decided:** the check went well when more than half of its answers were right: two of three, or both of two. A wrong answer the student was sure of does not change that, because it already goes in the log under "sure but wrong". The paste-in prompt now says "if they got most right".
- **Why:** the old condition ("most answers right, and their confidence fitted") disagreed with scenario 1 ("most of the check went right"). In round 7 one coach left out "you did well" after two of three right, and another said it after one of two.
- **Not chosen:** keeping the confidence condition. It made the rule hard to apply, and the confidence miss is already handled where it matters, in the log and in the question asked again before the end.
- **Where:** `SKILL.md`, session step 5 and the core loop; `portable/prompt.md`, step 5.
- **Result:** in the rerun, every coach said "you did well" after a check with more than half right.
- **Open:** the warm close often runs to three sentences instead of one or two, and the paste-in prompt still added course content after the log entry once.

### Round 7: scenarios 1 to 8 rerun after the warm close and sparing praise

- **Decided:** the rerun used the round 2 to 4 method: installed-skill command-line sessions, a separate student session and a separate grader per scenario. Two questions in one turn (G1) were counted as a weakness and not as a failure, as in round 4. The results are recorded as round 7 in `tests/results.md`.
- **Why:** the warm close and sparing praise had only been spot-checked. Keeping the round 4 rule for G1 makes the rounds comparable.
- **Result:** 4 of 9 skill runs and 3 of 5 paste-in runs pass. The warm close works in every run. Sparing praise failed in four runs, and "you did well" was used unevenly.
- **Done since:** the praise rule and the definition of "the check went well"; see the two entries above.
- **Open, not yet decided:**
  - **The description no longer loads the skill for "just give me the answer" study questions.** The scenario 2 opening loaded 0 of 5 times with the v0.3 description, against 3 of 3 in round 4.
  - **Rerun scenarios 1 to 8 against v0.3**, because round 7 tested the skill as it was before the writing mode.
- **Where:** `tests/results.md`, round 7.

### Three sources from course slides added, no rule changed

- **Decided:** three sources are added to `evidence.md` and `docs/references.md` as support or background. No rule changes, because the rule they most support ("say how sure you are") is already in v0.3.
  - **Abbas, Zhang & Junaid (2026):** a randomised experiment with 300 students. AI help raised efficiency and lowered learning depth. Calibrated trust in the AI and keeping up one's own motivation went with a smaller loss. Added as support for the verification nudge and for "say how sure you are".
  - **David, Vassena & Bijleveld (2024):** a meta-analysis finding that mental effort feels unpleasant. Added as background for the pace rules, which had no source.
  - **Scheiter et al. (2026):** the ISAR model (Inversion, Substitution, Augmentation, Redefinition). Added as a frame under "The three principles".
- **Why:** Abbas is one more randomised study for the core premise, and the first in the project to link calibrated trust in the AI with keeping learning depth. David gives the light pace a reason beyond the brief. ISAR names what the coach does in terms educational psychologists use.
- **Not chosen:**
  - Abbas in "What the evidence supports", which the coach quotes to students. Not until the methods are read: how learning depth was measured is unknown, the abstract reports no delayed test, and the t-values on the slides do not match their means and SDs.
  - A rule for coaching motivation ("why does this matter to you?"). It would feel preachy, and the research notes found little evidence that chatbots change motivation. The study's point about lost pride is already covered: the student does the work, and the warm close names it.
  - An announced "find the mistake in this example" exercise to train healthy distrust. It costs a turn, so it waits for a test.
- **Open:** read the Abbas full text (the publisher page refused automated access) and check the measures and the numbers.
- **Where:** `evidence.md` ("The three principles", the verification nudge row, the v0.3 row on how sure the coach is, the pace row, "What each source shows", References); `docs/references.md`.

### v0.3: small upgrades for the other common uses, one skill

- **Decided:** no new mode and no new skill for each common student use. A sentence or two was added to rules that already exist:
  - Summaries: the coach says what the student's version misses, a line each, and offers two or three questions before a long reading.
  - Checking: the coach says how sure it is about claims the student will rely on, and asks them to open a source before citing it.
  - Exam prep: a missed question comes back as a variant in one to two days; close to the exam, only confident and repeated misses get worked on.
  - Drafting for a course: their rough version first, then a receipt or pointers.
  - Three fixes from round 5: a push is not a try on graded text; tone versions are built from the student's own text; a first-language cause is named only when it is known.
  - The README lists example prompts for each common use.
- **Why:** explaining, homework and exam prep were already covered. The other uses each needed one rule, not a mode. One skill avoids competing triggers and extra installs, and a study session often mixes uses anyway. The skill description is at 1,020 of 1,024 characters and the paste-in prompt at 1,498 of 1,500, so neither was changed.
- **Not chosen:**
  - A mode or a skill per use case (more triggers, more files, more drift).
  - Brainstorming. The evidence is mixed (Kumar et al., 2025, found coach-style hints lowered later performance without AI), so it needs its own small test first.
  - Translation. No study was found on translation tools and learning, so it stays a plain task.
- **Where:** `SKILL.md` (verification nudge, their summary before yours, Modes); `references/modes.md` (exam prep, Feedback on my work); `assets/learning-log.md`; `evidence.md`, "v0.3 additions"; README, "Using it"; `tests/scenarios.md`, scenarios 15 to 17.

### v0.2: the writing mode ("Feedback on my work") is built

- **Decided:** the planned mode is built, starting with fixes of the student's own text, because that is one of the largest things people use AI for. In OpenAI's analysis of about 1.1 million ChatGPT messages, editing or critiquing the user's own text is 10.6 % of messages, about as large as all tutoring (10.2 %). In student surveys, 35 to 49 % use AI to improve their own writing. The mode has four parts:
  - **Fix receipt** for an ungraded fix: the whole text fixed in the first reply, changes in bold, at most two lines on one to three recurring patterns and why, and one offer to save them.
  - **Spot it first** on graded work and on request: the coach points, the student fixes.
  - **Tone:** a verdict, one version for the named reader and a one-line reason. When the student wants to get better at tone, two or three versions, a pick, then the principle.
  - **Writing profile:** a new section of the learning log with at most five patterns and a voice line, plus a fixed list of pattern names in `references/writing-patterns.md`.
- **Why:** a silent fix teaches little, because how much a draft improves in revision does not predict the next text. Marked correction with a short reason for a few recurring patterns has moderate effects that last. The full reasoning and sources are in `reports/AI use cases and coach upgrades.md` and in `evidence.md`, "Writing mode (v0.2)".
- **Not chosen:**
  - Pointing before fixing on every request (too slow when someone needs the text now, and find-and-fix is liked less).
  - Correcting everything and explaining everything (focused feedback works better for learning, and a long receipt is preachy).
  - A full rewrite in a smoother style (hides what changed, flattens the student's voice).
  - Platform memory (the student-kept log stays the only memory).
- **Where:** `SKILL.md` (description, core loop, step aside, graded work, Modes, Returning students, Tone and pace, Gotchas); `references/modes.md`; `references/writing-patterns.md`; `assets/learning-log.md`; `evidence.md`; `portable/prompt.md`; `tests/scenarios.md`, scenarios 9 to 14; `tests/results.md`, round 5.
- **Open:** the mappings in `evidence.md`, "Writing mode (v0.2)", are proposals and need the author's confirmation. Round 5 of the tests used a weaker method than rounds 2 to 4 and should be rerun with installed-skill sessions.

### A fix gets a receipt only with a learning signal

- **Decided:** the skill opens for a fix of the student's own text, and adds the receipt, only when there is a learning signal. The signals are: they say the language is not their first, that they want to get better, that the text is for a course, or they paste a writing profile. "Proofread my LinkedIn post" stays a plain task. The fix never waits for a question.
- **Why:** a coach that turns every proofread into a lesson gets switched off. The research report called this the conservative route and recommended it for v0.2.
- **Not chosen:** a receipt on every fix (the bold route). It could ship later as a separate small skill that people install on purpose, if the pilot shows that students save patterns and keep coming back.
- **Note:** "it's not my first language" counts as a signal. It is the most common way students introduce a fix request, and the receipt costs two lines.

### Graded text: no corrected sentences, not even "only the grammar"

- **Decided:** on graded work the coach points at language problems and explains the rule. It never returns a corrected version of the student's sentences.
- **Why:** this follows from the existing rule that the wording of graded work has to be the student's. Some courses allow proofreading tools. The coach cannot know the course rules, so it takes the stricter reading and says so once.
- **Not chosen:** correcting grammar only, without changing content (the line between grammar and wording is not clear enough to hold).

### Paste-in prompt: one line for fixes, other lines shortened

- **Decided:** the new line is "Fixing their text as they learn: fix errors only, bold them; name 1-3 recurring patterns, a line each." "Fix errors only" was added after the first test run, in which the prompt changed a correct "Can you" to "Could you". To fit the line, these lines were shortened:
  - Step 2: the ladder in fewer words.
  - Step 3: "Explain back in their words, own example".
  - Step 4: "one at a time, confidence ... before feedback", and "Sure but wrong?".
  - Step 5: "short log entry, review date in 1-2 days".
  - "Just tell me": "answer".
  - "one question a turn".
  - Step 1: "Max 3 questions, skip known ones".
  - "Sometimes ask how they'd check a claim, yours too".
  - The graded-work line now says "point at problems in their draft. Never write or fix it".
- **Why:** the 1,500-character limit. The prompt is now at 1,498.
- **Not in the paste-in prompt:** "just fix it" switching receipts off, tone, spot it first on ungraded work, and the writing profile. They need the reference files.

### The decision log lives in `docs/decisions.md`

- **Decided:** one running file for decisions, in `docs/`, next to the source mapping and the reference list.
- **Why:** `docs/` is the author's material. Everything in `skills/learning-coach/` goes into the ZIP that students install, so a decision log there would ship to every user.
- **Not chosen:** one file per decision (more structure than a project this size needs); a section in the README (the README is for people installing the skill).

### Sparing praise during the session

- **Decided:** right answers are confirmed plainly ("Right, about -18."). Praise is kept for moments that earn it, such as a mistake the student found themselves or a hard case cracked alone: a few words, a couple of times a session at most. The paste-in prompt says "rare praise".
- **Why:** praise on every answer stops meaning anything, and the warm close at the end should be the one that counts. In the spot check, the coaches answered nearly every right answer with "Exactly", "Spot on" or similar.
- **Not chosen:** no praise at all during the session (too cold for non-technical students).
- **Where:** `SKILL.md`, Tone and pace; `portable/prompt.md`, first line; `evidence.md`, Tone row; test criterion G5.

### A warm close at the end of every session

- **Decided:** after the log entry and the line on when to come back, the coach closes in one or two sentences.
  - It always thanks the student for the work.
  - If the check went well (most answers right, confidence fitted), it also says plainly that they did well and names what they did.
  - If it went badly, or there was no check, it does not say they did well. It names one thing that was true and good, such as catching their own mistake, and thanks them.
  - No generic praise ("Great job!", "You're a natural"), and no repeat of the review date.
- **Why:** the end is what the student takes away, and a student who leaves glad they came is more likely to return for the review. A student who struggled needs that reason to come back most. Praise that names the work tells them what to keep doing. "You did well" only when it is true keeps it believable, and the confidence ratings depend on the student trusting the coach's verdicts.
- **Not chosen:** praise after every right answer (makes the check feel like grading); a badge or celebration message (does not fit the plain style); thanks only when the student did well (leaves out the students who most need it).
- **Where:** `SKILL.md`, session step 5; `portable/prompt.md`, step 5; `evidence.md`, proposed mapping table.

### The example sentence for the warm close is a description, not a quote

- **Decided:** `SKILL.md` describes what to praise ("for example that they worked out the new case on their own") and asks for the coach's own words each time.
- **Why:** with a quoted example, both test coaches ended with the same words from the example ("thanks for sticking with it"). A returning student would hear it every week. After the change, the rerun coach used its own words.

### Hattie & Timperley (2007) as the proposed source for the warm close

- **Decided:** proposed, not confirmed. It sits in the "proposed mapping" table of `evidence.md`, principle 3, with Zimmerman (2002) as background.
- **Why:** the review finds that praise aimed at the person carries little information for learning, while praise tied to the work has more, though still limited, effect. Checked against the paper itself.
- **Open:** needs the author's confirmation, like the other proposed mappings. No study is claimed for the effect of ending warmly.

### Paste-in prompt wording trimmed to make room

- **Decided:** to fit the warm close and "rare praise" into the 1,500-character limit, five lines were shortened: "for the student in this chat" dropped, "When they want to learn or revise" became "To learn or revise", "their confidence ... before any feedback" became "confidence ... before feedback", "their answer or draft" became "their work", and "Just do it" became "Do it".
- **Why:** the paste-in prompt has a limit of 1,500 characters, set in the maintainer comment above the core loop in `SKILL.md`.
- **Note:** this left it at exactly 1,500. After the v0.2 changes it is at 1,498, so any further addition still needs a cut elsewhere.

### Tests for the new behaviour

- **Decided:** scenarios 1 and 8 check the warm close; new general criterion G5 checks sparing praise. `tests/results.md` says the full scenarios have not been rerun since these changes.
- **Done:** rerun in round 7; see the round 7 entry above.

---

## 16 November 2026 and earlier

These were recorded in the repository before this file existed. The detail is in the file named.

- **Three-step confidence scale** (sure, fairly sure, guessing): practical default agreed with the author. `evidence.md`, rules with no literature source.
- **Review gaps** of one to two days, about a week, then two to three weeks: practical default agreed with the author, adjusted to the student's calendar. `evidence.md`, same table.
- **Two modes in v0.1** (learn something new, exam prep). Feedback on my work and teach-back are planned and handled with the standing rules for now. `references/modes.md`, README.
- **The paste-in prompt is the core loop of `SKILL.md`, copied word for word**, at most 1,500 characters. Comment above the core loop in `SKILL.md`.
- **Changes after the test rounds:** one message per check question (answer, confidence and what to double-check together); log entries capped at about 150 words; under 100 words a turn; on graded work all content comes from the student; after the check, the student's summary still comes first. `tests/results.md`, "what failed and what changed".
