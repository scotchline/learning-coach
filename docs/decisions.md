# Decisions

What we decided about the learning coach, and why. Newest first. Add an entry whenever a decision changes how the coach behaves, what goes in the repository, or how it is tested.

Each entry says what was decided, why, what was considered and not chosen, and where the decision lives in the repository.

---

## 17 November 2026

### First release, and the install link points to it

- **Decided:** version 0.3.0 is the first GitHub release, with `learning-coach.zip` attached. The README's download links (English and German) now point to the ZIP in the latest release (`releases/latest/download/learning-coach.zip`), no longer to `dist/` on `main`.
- **Why:** several sessions commit to `main` during a day, and the ZIP in `dist/` can be rebuilt in the middle of a change. Students should get a version that was tested and released, not whatever is on `main` at the time.
- **Not chosen:** a link to a fixed version (`releases/download/v0.3.0/...`), because it would need a README edit for every release.
- **Consequence:** a change reaches students only with a new release. The README's maintainer section says how to publish one.
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
