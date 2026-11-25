# Input First Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** A student who is new to a topic gets a short explanation with an example first, then one question that makes them use it. A student with a basis keeps attempt-first.

**Architecture:** The order is decided in step 2 of `SKILL.md` and in the core loop, which `portable/prompt.md` copies word for word. The tester used ChatGPT with the paste-in prompt, so the core loop carries the change, and the paste-in prompt is tested as well as the skill. Scenario first, baseline on today's text, then the edit, then the reruns.

**Tech Stack:** Markdown skill files; the scenario harness from the simulator plan (`$H` = the `harness` folder in this session's scratchpad: `run.sh`, `trigger.sh`, `check.py`, `grade.sh`); model `claude-opus-5-5`.

**Spec:** `docs/specs/2026-11-24-input-first-design.md` (approved by the author on 25 November 2026).

## Global Constraints

- The core loop block in `SKILL.md` and `portable/prompt.md` stay identical, and the block is at most 1,500 characters with each line break counted twice. It is 1,498 now, so every character added must be cut elsewhere in the block.
- The `description:` line in `SKILL.md` does not change (1,018 characters).
- The explanation for a student new to the topic is under about 100 words, with one concrete example. Over about 150 words is a failure.
- "New to the topic" is read from the answer to the prior-knowledge question. No extra question is added to find out.
- After the explanation, exactly one question that makes the student use it.
- Students with a basis keep attempt-first, the hint ladder and the "three questions without progress" rule.
- English skill text; study examples only, no workplace examples. `version` stays `0.3.1`.
- Nothing is committed unless the author asks.
- Runs are on Wednesday 25 November 2026; the scenarios assume Monday 16 November. Shift dates in openings and in the grading note, as in Round 9.

## Review Focus

1. **A student with a basis says "I don't know" about one detail.** Expected: a guiding question, not an explanation. Test: the basis run of scenario 22 (Task 1).
2. **A student with a basis asks for the explanation first.** Expected: the explanation at once, then one question. Test: the explain-first run of scenario 22 (Task 1).
3. **Exam prep starts explaining.** Expected: "quiz me" still starts with the student's guess and a pre-test. Test: scenario 16, one run (Task 4).
4. **The examiner in the simulator starts explaining after "no idea".** Expected: it reacts in role, as before. Test: scenario 18, one run (Task 4).
5. **The paste-in prompt drifts from the skill.** Expected: both pass scenario 22 and the regression runs. Test: the paste-in runs in Task 4.

---

### Task 1: Scenario 22 in `tests/scenarios.md`

**Files:**
- Modify: `tests/scenarios.md:3` (count line), and append after the "Trigger check for the simulator" section

**Interfaces:**
- Produces: scenario **22** "New to the topic: regression", with a normal run, an explain-first run and a basis run. Tasks 2 and 4 run all three; Round 10 names them so.

- [ ] **Step 1: Change the count line** from "Twenty-one conversations" to "Twenty-two conversations".

- [ ] **Step 2: Append `---`, the heading `# Input first (draft)`, and scenario 22** in the layout of scenario 16:
  - **Opening:** "Can you help me learn linear regression? I study interaction design and we have a statistics module now."
  - **Student:** Mia. Asked what she knows: "nothing really, I've never had statistics". She answers the first application question half right. Asked to explain it back, she does it in two sentences. Then, word for word: "thanks, that's enough for today". About 6 to 8 messages.
  - **The coach should:** (1) give an explanation within its first two replies, under about 100 words, with one concrete example; (2) follow it straight away with one question that makes her use it; (3) not ask her to guess before the explanation; (4) go on with the usual loop (explain back or a question on a new case) before the close.
  - **Failure:** a request to guess; more than one question before the explanation (the prior-knowledge question counts as that one); an explanation over about 150 words; an explanation with no question after it; explanations spread over several turns without a question from her side to answer.
  - **Explain-first run:** opening "I know a bit of statistics, means and correlation. Explain linear regression to me first, then I'll try." Should: the explanation at once, then one question that uses it. Failure: a request to try or guess before the explanation.
  - **Basis run:** opening "We had linear regression last week. I get the line, but I don't know what the slope tells me." Should: a question or a guiding question first, no explanation in the first reply. Failure: the explanation of the slope in the first reply.

- [ ] **Step 3: Check.** `grep -n -E "^## 22\.|Explain-first run|Basis run|^# Input first" tests/scenarios.md` prints four lines, after `## Trigger check for the simulator`.

- [ ] **Step 4: Checkpoint.** `git status --short` shows `tests/scenarios.md`. No commit.

### Task 2: Baseline (red)

**Interfaces:**
- Consumes: scenario 22 (Task 1); `$H/run.sh`, `$H/grade.sh`.
- Produces: `$H/run.sh <scenario> <label> portable:<prompt-file>`, a portable mode in which the coach has the prompt file plus "Today is <weekday, date>." as its only system prompt, `--tools ""` and `--disable-slash-commands`. Task 4 uses it. Also `$H/out/baseline-22.md`.

- [ ] **Step 1: Add the portable mode to `run.sh`.** When the third argument starts with `portable:`, the coach call uses `--system-prompt "$(cat <file>)\n\nToday is Wednesday, 25 November 2026."`, `--tools ""` and `--disable-slash-commands`, and no skill folder. Smoke run: one coach turn of scenario 22 with `portable:portable/prompt.md`; expected: a reply and no tool calls in `check.py`.

- [ ] **Step 2: Baseline runs.** On a snapshot of today's working-tree skill and on `portable:` with today's `portable/prompt.md`, one run each of the three runs of scenario 22: six runs.

- [ ] **Step 3: Grade and confirm red.** One grading session per run kind, with a note naming the run paragraph that applies. Write `$H/out/baseline-22.md`: per run, pass or fail with a quote. Expected: the normal run fails on the skill and on the paste-in prompt (a request to guess, or more than one question before the explanation). If a normal run passes, record it; it then does not test the change.

### Task 3: `SKILL.md`, the core loop and the hint ladder

**Files:**
- Modify: `skills/learning-coach/SKILL.md`. The core loop line 2 is at line 29. Step 1 is at lines 65 to 71, step 2 at lines 73 to 88. The "I don't know" sentence is at line 84.
- Modify: `portable/prompt.md`, to match the block
- Modify: `skills/learning-coach/references/hint-ladder.md` (the sentence under the title)
- Rebuild: `dist/learning-coach.zip`

**Interfaces:**
- Produces: the text Tasks 4 and 5 test.

- [ ] **Step 1: Step 2 in `SKILL.md`.** Rename the heading to "### 2. Attempt first, or input first". Before the first paragraph, add the order rule from the spec. The prior-knowledge answer decides. New to the topic means they say so ("no idea", "never heard of it", "we haven't covered it yet") or their answer lacks the basics. Then: an explanation under about 100 words with one example, from their field when it is known, then one question that makes them use it; no request to guess. "Explain it to me first" is treated the same way, and it is not "just tell me". A student with a basis: the existing text, unchanged. Add a "Why:" sentence with the expertise-reversal finding.

- [ ] **Step 2: The "I don't know" sentence** at line 84. Limit it to students with a basis: "From a student with a basis, 'I don't know' is not yet stuck ...". A student new to the topic gets the explanation.

- [ ] **Step 3: Step 1.** After the sentence at line 71, add: the answer also decides the order in step 2.

- [ ] **Step 4: The core loop line 2.** Say that attempt-first applies when they know the basics, and that someone new to it gets a short explanation with an example, then applies it. Cut the same number of characters elsewhere in the block. Then copy the block to `portable/prompt.md`.

- [ ] **Step 5: Hint ladder.** In `hint-ladder.md`, add one sentence: the ladder is for students with a basis; a student new to the topic gets the explanation first (`SKILL.md`, step 2).

- [ ] **Step 6: Check.**
  - `diff <(sed -n '/^<!-- portable:start -->$/,/^<!-- portable:end -->$/p' skills/learning-coach/SKILL.md | sed '1d;$d') portable/prompt.md` prints nothing.
  - `python3 -E -c "p=open('portable/prompt.md').read();print(len(p)+p.count(chr(10)))"` prints 1,500 or less.
  - The description check from the simulator plan prints `1018`.

- [ ] **Step 7: Rebuild the ZIP** with the README command. Checkpoint: `git status --short`. No commit.

### Task 4: Runs (green), regressions and Round 10

**Files:**
- Modify: `tests/results.md` (a new `## Round 10: input first (scenario 22)` section before `## Limits of these tests`)
- Modify: `skills/learning-coach/references/evidence.md` and `docs/references.md` (one proposed row and one reference)

**Interfaces:**
- Consumes: Task 2's portable mode and baseline; Task 3's text.

- [ ] **Step 1: Scenario 22.** On a snapshot of the new skill and on `portable:` with the new `portable/prompt.md`: two runs each of the normal run, one each of the explain-first run and the basis run. Eight runs. Expected: all pass.

- [ ] **Step 2: Regressions.** On the skill: scenarios 1, 2, 16 and 18, one run each. On the paste-in prompt: scenarios 1 and 2, one run each. Expected: they pass as in their last recorded rounds. Scenario 18 is judged under the rules of Round 9, so compare it with Round 9 and do not count it as a new failure if it fails for a reason Round 9 already recorded.

- [ ] **Step 3: One round of fixes,** if a run of scenario 22 fails. Change the step 2 text, rerun only the failing runs, and grade again. Anything still failing goes to the author.

- [ ] **Step 4: The source.** Confirm Kalyuga, Ayres, Chandler & Sweller (2003), "The expertise reversal effect", *Educational Psychologist, 38*(1), 23-31, against the publisher or Crossref. Add a proposed row to `evidence.md` under "Added 25 November 2026", in the style of the 24 November block, and the reference to `docs/references.md`. If it cannot be confirmed, leave both out and say so in Round 10.

- [ ] **Step 5: Write Round 10** in the format of Round 9. Include:
  - how it was run, including the portable mode
  - a note that the tester used ChatGPT and these runs use Claude with the same prompt
  - the baseline table
  - the results table
  - the regressions
  - the character counts before and after
  - "What this shows"
  - "Weaknesses that did not fail a criterion"

  Checkpoint: `git status --short`. No commit.

### Task 5: Decision log

- [ ] **Step 1:** In `docs/decisions.md`, under the newest date, add an entry for the build in the format of the others. It covers what changed in `SKILL.md`, the core loop and `hint-ladder.md`; which characters were cut from the block; Round 10 in two lines; and what is open. Check it with `sed -n 1,30p docs/decisions.md`.
- [ ] **Step 2: Final checkpoint.** `git status --short`. Show the author the list and commit only if asked.
