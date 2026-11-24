# Simulator mode: design

24 November 2026. Status: draft for the author's approval. Nothing is built.

## Intent

A student practises a conversation they will later have to hold without AI. The coach plays the other person, the student plays themselves, and then comes a debrief and a second, harder round.

It is the first of the roles taken from the prompt sheet «Lernprompts» (see `docs/decisions.md`, 24 November 2026), and it fills the biggest gap the comparison found. The skill trains knowing and recalling, but not performing: answering, explaining and holding a position live, in front of someone. That is what an oral exam, a talk or a conversation in another language asks for, and the measure of the skill is still what the student can do afterwards without AI.

## Goals

- Practise conversations with one counterpart: an oral exam, questions after a presentation, a seminar discussion, a conversation in a foreign language, a patient or client conversation in programmes that train them.
- Keep the five steps and the standing rules. The student acts first, judges their own performance before the coach does, is checked once more without hints, and leaves with a log entry and a date.

## Non-goals

- Case simulations in which the coach narrates a situation and the student makes decisions (decided 24 November: not now).
- Conversations at work (decided 24 November: the skill is for study and learning).
- Voice. The coach works in text. The README can suggest dictation.
- The paste-in prompt. It is full (1,498 of 1,500 characters), so the simulator exists in the skill only.

## Anti-goals: failure even if it runs

- The coach writes the student's lines, or plays both parts.
- The counterpart gives in: it accepts a weak or wrong answer to move on, agrees too soon, or praises. Practice without resistance trains nothing.
- The coach leaves the role in the middle of the scene to teach or correct.
- The debrief becomes a long list or a model script.
- A "simulation" that produces content for graded written work, for example a debate staged to collect arguments for a graded essay.

## Constraints

- The skill description has 4 characters left (1,020 of 1,024). A trigger for practising a conversation means shortening other wording.
- Turns stay short. In role, the counterpart asks one question or gives one reply per turn, as a real person would.
- Reply language follows the rule in `SKILL.md`. In a foreign-language conversation the counterpart speaks the target language; the setup and the debrief are in the language the student set the session up in.

## Approaches: where the instructions live

1. **A file of its own, `references/simulator.md` (chosen).** `SKILL.md` gets one bullet under Modes and one sentence saying when to read the file. The coach reads it only when a simulation runs. The author confirmed one file per role on 24 November.
2. A section in `modes.md`, like the other modes. Consistent with today, but every exam-prep or writing session would also read the role-play instructions.
3. A separate skill. Ruled out on 24 November: copied rules, skills competing to load, more to install.

The existing modes stay in `modes.md` for now. Moving them into one file each is a separate change.

## The session

### When the mode starts

A request to act out a conversation in order to practise it: "be my examiner", "simulate my oral exam on Friday", "ask me what the audience might ask after my talk", "let's talk in French so I can practise", "play a patient, I'm practising history-taking".

- "Quiz me" without a counterpart stays exam prep.
- A role-play with no practice purpose (a story, a game, a character for fun) is a plain task. Step aside, as for any other task.
- An oral-exam simulation also uses the date logic of exam prep: the reruns are planned backwards from the exam date.

### 1. Plan (one to three questions, one per turn)

Find out what they are practising and for when, who the counterpart is, and what the situation is. Skip what they already said. For an oral exam or a talk, ask for the topic list, the slides or the outline, and work from it. The default difficulty is realistic, with one hard moment.

Then set the scene in two lines, in the student's language: who the coach plays and what the situation is, and the two words that work throughout, «Pause» for a hint and «Stopp» to end. Then start, in role.

### 2. The role-play: the attempt

- Play only the counterpart. Never write the student's lines.
- React to what they actually said. A vague answer gets the follow-up a real examiner would ask, and a gap gets pressed. Do not accept a wrong or vague answer to move on, do not reveal the answer, and do not praise.
- One question or one reply per turn, under about 60 words.
- After about three exchanges, bring one hard moment that fits the situation: a why or what-if question, an objection, a misunderstanding, a question outside what they prepared.
- Run about six to ten exchanges, or to the natural end of the situation.
- **«Pause»:** step out in one line and give the smallest help from the hint ladder (a guiding question or the relevant idea, never the line to say). Ask whether to go on, then go back into role. A student who asks in the scene "what should I say?" gets the same. If they insist on a line, the "just tell me" rule applies.
- **Language practice:** do not correct mistakes in the scene. Note them for the debrief. Check meaning only where a real conversation partner would not understand.
- Step out of role at once if the student seems upset or the scene turns harmful.

### 3. Debrief: their view first

- Mark the end clearly ("End of the simulation.").
- Ask first how it went and which moment they would redo. This takes the place of the confidence rating: their view comes before yours.
- Then two moments, each quoting their own words: one that worked and why, and one to change and what to try. Say what to try as a principle or a question, not as a script.
- **Oral exam:** content that was wrong or missing, one line each. A wrong answer they gave with confidence goes into the log under "sure but wrong".
- **Foreign language:** one to three recurring patterns, named as in `writing-patterns.md`, each with the student's own sentence, and the offer to save them to their writing profile, as in the receipt of "Feedback on my work".
- The whole debrief stays under about 150 words.

### 4. Check without AI: a second round

The same situation, harder: more resistance, a twist, or the moment they said they would redo. No hints this time unless they stop the scene. Afterwards, one or two lines on what changed. If there is no time left, the second round becomes the first review.

### 5. Reflect and log

A log entry in the format of `assets/learning-log.md`: the goal, what they can now do, what is still shaky, "next time I'll do differently" (the one thing to try), and the next review, a rerun with a variant in one to two days or planned back from the exam date. The review queue gets a row such as "Rerun: oral exam on regression, examiner asks for a counter-example".

The warm close follows step 5 of `SKILL.md`. Here, the check went well when they handled the hard moment in the second round; that decides whether the close says they did well.

### Standing rules in this mode

- **Graded work:** practising for a graded oral exam or talk is fine, because the practice is not the submission. Staging a conversation to produce content for a graded written piece is not: hand it back as the graded-work rule says.
- **"Just tell me":** a model line for one moment, in the debrief or after «Pause». The first time, with the one sentence on the trade-off.
- **Praise:** never from the counterpart. In the debrief, the usual limit.

## Changes to the repository

- `references/simulator.md`: new, with the instructions above.
- `SKILL.md`: one bullet under Modes; the sentence saying when to read `references/simulator.md`; under "When to coach and when to step aside", the case of a role-play for fun; the description with a trigger for practising a conversation, at 1,024 characters or fewer. Version bump at release.
- `references/evidence.md` and `docs/references.md`: rows for the simulator. Chernikova et al. (2020) for simulation-based learning: a large effect on complex skills (g = 0.85 across 145 studies), mostly in medical education and not with AI. Mollick & Mollick (2023) as the source of the role, not as evidence of an effect. "Their view first" reuses the existing self-assessment row.
- `tests/scenarios.md`: the scenarios and criteria below.
- README: a row in "Using it", and the repository layout.
- `docs/decisions.md`: an entry when it is built.

## Tests

Scenarios, run with simulated students:

1. **Oral exam, statistics.** The student gives a vague answer and later a confident wrong one. Pass: the examiner follows up without revealing the answer, brings a hard moment after about three exchanges; the debrief opens with the student's view; the wrong answer goes under "sure but wrong"; the second round is harder; the log has a rerun date.
2. **Conversation in French**, with a student learning French. They make mistakes in the scene. Pass: no correction in the scene; the debrief names one to three patterns with their own sentences and offers to save them.
3. **"Just tell me what to say"** in the middle of the scene, then "play both parts so I can watch". Pass: a hint first; a line only when they insist, with the trade-off sentence once; never both parts.
4. **Graded:** "simulate a debate between two experts on my essay question", for a graded essay. Pass: the graded-work rule, and no arguments produced.
5. **Trigger check:** "play a pirate for my kid's bedtime story" is a task; "be my examiner for Friday's oral exam" loads the skill and starts the simulator.

New criteria for simulator scenarios: stays in role; does not give in to a wrong or vague answer; one question or reply per turn; the debrief opens with the student's view; the second round is harder than the first.

## Left to the builder

The exact wording of the file and of the description; which words in the description to shorten; the details of each scenario; «Pause» and «Stopp» in the student's language.

## Calls Claude made, for the author to check

- The second round has no hints by default.
- The setup and the debrief are in the language the session was set up in; the scene is in the target language.
- "Went well" means handling the hard moment in the second round.
- About six to ten exchanges, with one hard moment after about three.
