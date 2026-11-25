# Input first when the student is new to a topic: design

24 November 2026. Status: draft for the author's approval. Nothing is built.

## Intent

A tester asked the coach about regression and, relatively early in the session, got question after question when she wanted an explanation. Her verdict: too many questions, too little input.

The cause is in `SKILL.md`, step 2. Before any explanation the student must try. "I don't know" is "not yet stuck", so the coach first asks for a guess. Then help climbs the hint ladder one rung at a time, and the worked example comes last. Someone who knows nothing about regression cannot make a useful guess, so they get four or five questions before any input. For them, attempt-first is guessing, not thinking.

The change: how much the student already knows decides the order. Someone new to the topic gets a short explanation first, then has to use it at once. Someone with a basis tries first, as today.

Why this fits the skill: the measure is still what they can do afterwards without AI. The learning work moves from guessing before the input to applying right after it. The expertise-reversal effect is the reason: novices learn more from an explanation or a worked example first, and learners with some knowledge learn more from trying first (Kalyuga et al., 2003; to be verified before it goes into `evidence.md`).

## Goals

- A student who is new to a topic gets a short explanation within the first two replies, then one question that makes them apply it.
- A student with a basis keeps attempt-first and the hint ladder unchanged.
- "Explain it to me first" is honoured at once, followed by a question that uses the explanation.

## Non-goals

- Complexity levels per question (approach C, not chosen).
- Remembering who the student is across chats (a later step: a "Who I am" line in the learning log).
- Changes to exam prep, the feedback mode or the simulator.

## Anti-goals

- The coach turns into a lecturer: long explanations, or explanations with no question after them.
- Students who could try get the explanation handed over, so the first piece of thinking leaves them again.
- More planning questions to find out the level.

## Approaches

1. **The student's prior knowledge decides the order (chosen by the author).** Small changes to step 2, the "I don't know" line and the core loop.
2. A switch "explain first" that the student has to know about. Not chosen alone, because the tester would not have known to use it. Folded into approach 1 as a request the coach honours.
3. Complexity levels per question, as the author first sketched it. Not chosen, because what matters is the distance between the question and this student's prior knowledge, not how hard the question is in general, and the coach rarely knows the course.

## How it works

**Telling new from not new.** No extra question. The plan step already asks what they know, and that answer decides. A student is new to the topic when they say so ("no idea", "never heard of it", "we haven't covered it yet"), or when their answer shows they lack the basics the question needs. One "I don't know" about a detail is not the same; that still gets a guiding question.

**New to the topic.**
- No request for a guess.
- A short explanation: under about 100 words, one concrete example, from their field when it is known (a design student gets a design example).
- Then straight away one question that makes them use it: the idea applied to a small new case, or the idea in their own words.
- From there, the loop as usual: explain back, a check from memory, the log.

**With a basis.** Unchanged: attempt first, the hint ladder, at most three questions without progress before moving up.

**"Explain it to me first."** Honour it at once, the same way as for a student who is new to the topic. This is not "just tell me": they still want to learn, so the question that uses the explanation follows.

**Core loop and paste-in prompt.** The core loop's step 2 says that attempt-first applies when they have a basis and that otherwise a short explanation comes first, then they apply it. The paste-in prompt is full (1,498 of 1,500 characters), so the same number of characters must be cut elsewhere in the block.

## Changes to the repository

- `SKILL.md`: step 2 (when attempt-first applies, the new-to-the-topic path, "explain first"), the "I don't know" line, the core-loop line, and the copy of the core loop in `portable/prompt.md`. The description is not touched.
- `references/hint-ladder.md`: one line saying the ladder is for students with a basis.
- `references/evidence.md` and `docs/references.md`: a proposed row for input first with the expertise-reversal source, once it is verified.
- `tests/scenarios.md`: a new scenario, and the reruns listed below.
- `docs/decisions.md`: an entry when it is built.

## Tests

1. **New scenario: new to regression.** A student in a design programme asks what a regression is and says she has never had it. Pass: an explanation of under about 100 words with an example, within the first two replies; then one question that uses it; no request for a guess. Fail: a guess asked for, more than one question before the explanation, an explanation over about 150 words, or an explanation with no question after it.
2. **New scenario, second run: "explain it to me first".** A student who knows some statistics says this. Pass: an explanation, then one question that uses it.
3. **Regression check: scenario 1** (a normal session with some prior knowledge). It should still start with an attempt.
4. **Regression check: scenario 2** ("just tell me" three times) and the paste-in prompt runs of scenarios 1 and 2, because the core loop changes.

## Left to the builder

The exact wording; which characters to cut in the core loop; the details of the new scenario.

## Calls Claude made, for the author to check

- "New to the topic" is read from the answer to the prior-knowledge question, without an extra question.
- The explanation is under about 100 words.
- "Explain it to me first" is honoured at once, followed by a question.
