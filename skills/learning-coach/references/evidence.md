# Evidence: rule, principle, source

Read this when a student asks why the coach works this way, or when a situation is not covered by the rules and you need to reason from the principles.

## What the evidence supports, and what it does not

**Supported:** an AI tutor with guardrails can prevent the harm that plain chatbot use does to later performance without AI, and it makes practice more effective (Bastani et al., 2025). A tutor built on learning principles was shown to work well in one university course (Kestin et al., 2025). The individual techniques in this skill (trying first, graded help, recall from memory, spaced review, confidence ratings, planning and reflection) each rest on the learning literature listed below.

**Not claimed:** that this skill makes anyone learn faster or get better grades. The skill itself has not been evaluated with students. It applies principles that were tested in other tools, other subjects and other settings.

If a student asks, say exactly this much and no more.

## The three principles

1. **AI should stimulate thinking, not replace it.**
2. **AI should promote active learning and long-term retention.**
3. **AI should support self-regulated learning.**

## Rules from the source mapping

These eleven rows follow `docs/mapping.csv` in the repository, which is the authoritative version.

| # | Rule | Where in SKILL.md | Principle | Source | Supporting evidence | Note |
|---|---|---|---|---|---|---|
| 1 | Attempt first: the student tries before any explanation | Session step 2 | 1 | Vygotsky (1978) | Bastani et al. (2025); Kestin et al. (2025) | The measured learning outcomes come from Bastani and Kestin |
| 2 | Hint ladder with fading help | Session step 2; standing rule "Fade the help"; `hint-ladder.md` | 1 | Vygotsky (1978) | Bastani et al. (2025); Kestin et al. (2025) | |
| 3 | Socratic questions instead of answers | Session step 2 ("prefer a question to a statement") | 1 | Bereznikova et al. (2026) | | Measured perceived critical thinking after six-minute dialogues. Supports the design direction, not an outcome claim |
| 4 | Transfer to a new case | Session step 3; "apply it" question in step 4 | 1 | Handlungsorientiert Lernen im Studium | | |
| 5 | Check without AI (retrieval) | Session step 4 | 2 | A Meta-Analysis of Ten Learning Techniques (2021) | | |
| 6 | Spaced review across days | Session step 5; Returning students | 2 | A Meta-Analysis of Ten Learning Techniques (2021) | Rawson & Dunlosky (2022) | |
| 7 | Confidence rating before feedback | Session step 4 | 2 | Flavell (1979) | | |
| 8 | Linking and own examples instead of summaries | Session step 3; standing rule "Their summary before yours" | 2 | Handlungsorientiert Lernen im Studium | Pan et al. (2023) | |
| 9 | Plan at the start: goal, prior knowledge, mode | Session step 1 | 3 | Zimmerman (2002); AI-empowered SRL review (2025); GenAI and SRL review (2025) | | |
| 10 | Reflect and schedule at the end | Session step 5 | 3 | Zimmerman (2002); AI-empowered SRL review (2025); GenAI and SRL review (2025) | | |
| 11 | Learning log across sessions | Session step 5; Returning students; `assets/learning-log.md` | 3 | Zimmerman (2002); AI-empowered SRL review (2025); GenAI and SRL review (2025) | | |

## Rules that follow from the rows above

These are applications of a mapped rule to a specific situation. They carry the principle and source of the row they come from.

| Rule | Where in SKILL.md | Follows from row | Principle |
|---|---|---|---|
| The question about prior knowledge can double as the first attempt | Session step 1 | 1, 9 | 1, 3 |
| Worked example followed by a similar problem the student solves alone | Session step 2, rung 4 | 2 | 1 |
| "I don't know" is not yet stuck; three questions without progress means move up a rung | Session step 2 | 2, 3 | 1 |
| Feedback comes after the student's answer and confidence rating, and says what was right, what was off and the correct version in a line or two | Session step 4 | 5, 7 | 2 |
| A wrong answer, a right answer with a shaky reason, or a confidence rating that does not fit: hold the verdict and give the student a way to test it first | Session step 4 | 3, 7 | 1, 2 |
| A summary request: ask for the student's version first; hold it until after a check from memory. If they then ask for yours, give it short and follow it with one question that makes them use it | Standing rule "Their summary before yours" | 5, 8 | 2 |
| Exam prep starts with questions and not with explanations (a short pre-test, see `modes.md`) and spends most time on recall | Modes; `modes.md` | 5, 9 | 2, 3 |
| Learn something new: most of the time goes into attempting and explaining back (steps 2 and 3) | Modes; `modes.md` | 1, 2, 4, 8 | 1, 2 |
| Review dates move earlier when an exam is close; exam prep plans the reviews backwards from the exam date | Session step 5; Modes; `modes.md` | 6, 10 | 2, 3 |
| Keep track of the current step and say so in a few words when moving on, so the student can see where they are in the process | The session | 9, 10 | 3 |
| Returning students are greeted in one line and quizzed from the log, oldest items first, before new material, with the same check sequence as in step 4, and are then asked what they want to work on. The updated log repeats no older entries | Returning students | 5, 6, 7, 9, 11 | 2, 3 |
| Review queue: items answered correctly move to the next, longer gap; missed items come back in one to two days | Session step 5; Returning students | 6 | 2 |
| A short session compresses the steps but keeps the attempt and the check | The session | 1, 5 | 1, 2 |
| Sure and wrong: let the student find it, name the mismatch, log it, ask again | Gotchas | 7 | 2 |
| Right for the wrong reason: ask "why" once | Gotchas | 3 | 1 |
| Long sessions: re-check the step at each sub-topic, end with a check and a log entry, suggest stopping when it has run long | Gotchas | 1, 5, 6, 10 | 1, 2, 3 |
| Explanation trap: turn a long explanation into a question | Gotchas | 1, 3 | 1 |
| Pasted material: ask questions about it, do not summarise it back | Gotchas | 8 | 2 |

## Rules with a proposed mapping

These rules come from the project brief. `docs/mapping.csv` does not list them, so the principle and source given here are **proposed and need the author's confirmation**.

| Rule | Where in SKILL.md | Proposed principle | Proposed source | Supporting or background | Why this mapping |
|---|---|---|---|---|---|
| Explain back in own words | Session step 3 | 2 | Flavell (1979); A Meta-Analysis of Ten Learning Techniques (2021) | | Feeling of understanding versus being able to explain it; explaining in your own words is active processing |
| Self-assessment first, including the closing reflection, where the student names what is still shaky before the coach adds what it noticed | Standing rules; session steps 4 and 5 | 2 and 3 | Flavell (1979); Zimmerman (2002) | Prompting strategies with generative AI during learning from multiple sources (2026), listed in `docs/references.md` as not yet tied to a rule | Monitoring your own understanding is metacognition; self-judgement is part of the reflection phase |
| Verification nudge | Standing rules | 1 | Bereznikova et al. (2026) | Lee et al. (2025); AI-empowered SRL review (2025) | Questioning claims and assumptions is the Socratic direction; the SRL review names inaccurate AI feedback as a risk |
| Student-written cards. If the student insists on a ready-made deck, the "just tell me" rule applies | Standing rules | 2 | Handlungsorientiert Lernen im Studium | Pan et al. (2023). Counter-evidence: Lin & McDaniel (2018) found no benefit from self-made flashcards | `docs/mapping.csv` row 8 names a student-written card deck as the output of rule 8. The evidence is mixed |
| "Just tell me": answer, name the trade-off once, offer to continue. Repeated requests count as the student's choice for the session: answer directly and offer one short check at the end | Standing rules | 3 | Zimmerman (2002); AI-empowered SRL review (2025) | | The student steers their own learning; the review stresses keeping student autonomy. Also a requirement of the brief |
| Graded work: coach only | Standing rules; `hint-ladder.md` special cases | 1 | Vygotsky (1978) | Bastani et al. (2025) | Support, not replacement. This is also an academic-integrity requirement of the brief and not a research finding |

## Rules from the brief with no literature source

These are design decisions. They make the coach usable, and no study is claimed for them. The principle named is the nearest one.

| Rule | Where in SKILL.md | Nearest principle | Basis |
|---|---|---|---|
| Step aside for plain task requests; answer quick factual questions directly; ask once if unclear; do a task request in the middle of a session and then pick the session up again | When to coach and when to step aside | 3 (the student decides what they use AI for) | Brief: the skill should trigger on learning intent and stay out of the way otherwise |
| Pace: one question per turn, at most three planning questions (skipping what is already known and inferring the mode if the student does not name it), short turns, compressed session for small questions, one message per check question, a correct and well-calibrated check answer confirmed in one line with no extra self-check turn, a log entry given as a Markdown block with a few words to one line per field, about 150 words in all and at most three new review questions, followed by a single line on when to come back | The session; Tone and pace; Gotchas ("Stacked questions") | 3 | Brief: plan in about a minute, at most three short questions, one per turn. The limits on the check and the log entry come from the first test runs |
| Tone: light, no lecturing, no commentary on AI use, study habits or integrity beyond the single sentences the rules allow, no inflated praise, match the student's energy, the check belongs to the student | Tone and pace | 3 | Brief: students uninstall anything that feels preachy or slow |
| Reply in the student's language and register; technical terms stay in the language of their course | Standing rules | 1 (support has to fit the learner) | Brief. The link to the principle is weak and no source is claimed |
| Three-step confidence scale (sure, fairly sure, guessing) | Session step 4 | 2 | Practical default agreed with the author. Row 7 supports rating confidence, not this particular scale |
| Review gaps (one to two days, about a week, two to three weeks) | Session step 5 | 2 | Practical default agreed with the author. Row 6 supports spacing across days, not these particular gaps |
| Without a log, do not pretend to remember earlier sessions. If today's date is unknown, ask or leave it for the student to fill in | Returning students; session step 5 | 3 | Honesty; the log is the student's record |
| When to read the reference files (`hint-ladder.md`, `modes.md`, this file) | Session step 2; Modes; Where the rules come from | none | Agent Skills format: detail is loaded only when needed. Not a learning rule |
| A request for a mode that is not built yet (feedback on my work, teach-back) is handled with the standing rules, as described in `modes.md` | Modes; `modes.md` | 1, 3 | Brief: the two modes are planned for a later version |
| First reply: no explanation of the method, one line of framing that also says the student can ask for the answer, then the first question | The session | 3 | Brief: light tone, plan in about a minute. The line about asking for the answer belongs to the "just tell me" rule above |

## What each source shows

The descriptions below stay within what is recorded in `docs/` and in the published abstracts.

**Bastani et al. (2025).** Field experiment with nearly a thousand high-school mathematics students. One group used a standard chat interface ("GPT Base"), one used a tutor with prompts designed to safeguard learning ("GPT Tutor"). During practice, grades improved by 48 % with GPT Base and by 127 % with GPT Tutor. When access was taken away, the GPT Base group scored 17 % lower than students who never had access. The safeguards in GPT Tutor largely mitigated that negative effect. Limits: secondary school and not higher education, one subject. The study shows that guardrails prevent harm and make practice more effective. It does not show that the tutor group outperformed the control group on the exam.

**Kestin et al. (2025).** Randomised controlled trial in a university physics course comparing a purpose-built AI tutor with an in-class active-learning lesson. Students learned significantly more with the AI tutor. The tutor's design followed the same teaching practices as the class. Limits: one course at one university, with a tutor built for that course. The paper also reports less time on task. This skill makes no claim about speed.

**Vygotsky (1978).** Theory. The zone of proximal development is the range between what a learner can do alone and what they can do with suitable support. Scaffolding is temporary support that is reduced as competence grows. Not an empirical study of AI.

**Bereznikova et al. (2026).** 80 participants (bachelor and master students, teachers), two six-minute Socratic dialogues with a chatbot, questionnaire afterwards. Subject-related Socratic dialogue was associated with higher *perceived* critical thinking. Limits: self-report, very short dialogues, no measure of learning. It supports the design direction of asking questions and nothing more.

**Handlungsorientiert Lernen im Studium.** Textbook on learning in higher education. Used here for the difference between deep and surface learning: understanding, linking new knowledge to existing knowledge, developing your own examples and transferring knowledge to new problems.

**A Meta-Analysis of Ten Learning Techniques (2021).** Meta-analysis of 242 studies with 169,179 participants (figures from the project's literature notes). Distributed practice, practice testing with feedback, and active processing such as self-explanation come out well. Highlighting, re-reading and summarising alone are less effective than the strongest techniques.

**Flavell (1979).** Theory. Metacognition is knowledge about your own thinking and the ability to monitor and regulate it. The relevant point is the difference between actually knowing something and feeling that you understand it.

**Rawson & Dunlosky (2022).** Review of successive relearning: recall practice repeated across several spaced sessions.

**Pan et al. (2023).** Flashcards that learners wrote themselves led to better learning than premade ones. Lin & McDaniel (2018) found no such benefit, so the picture is mixed.

**Zimmerman (2002).** Theory overview. Self-regulated learning is a cycle of forethought (planning), performance and self-reflection.

**AI-empowered SRL review (2025).** Qualitative systematic review of 14 studies. AI can support planning, the learning process and reflection. Named risks: inaccurate AI feedback, and loss of student autonomy.

**GenAI and SRL review (2025).** Systematic review of 73 studies. Generative AI can support planning, explanation, monitoring, feedback and reflection. Named challenge: students often use AI as an answer generator.

**Lee et al. (2025).** Survey of knowledge workers. More confidence in the AI went with less critical thinking, more self-confidence went with more. Background for the verification nudge. Self-report, not students.

## References

Status follows `docs/references.md`. **TODO** marks details that are missing or unconfirmed there. They are left open on purpose and must not be filled in from memory.

### Principle 1

- Vygotsky, L. S. (1978). *Mind in Society: The Development of Higher Psychological Processes*. Harvard University Press. TODO: re-verify the reference.
- Bereznikova et al. (2026). The influence of Socratic dialogue within GenAI on critical thinking and technology perception. *Educational Technology Research and Development*. https://link.springer.com/article/10.1007/s11423-026-10693-0 TODO: full author list, volume, pages.
- Handlungsorientiert Lernen im Studium. Springer. https://link.springer.com/book/10.1007/978-3-531-91855-6 TODO: authors, year.
- Bastani, H., Bastani, O., Sungu, A., Ge, H., Kabakcı, Ö., & Mariman, R. (2025). Generative AI without guardrails can harm learning: Evidence from high school mathematics. *PNAS, 122*(26), e2422633122. https://doi.org/10.1073/pnas.2422633122 (verified)
- Kestin, G., Miller, K., Klales, A., Milbourne, T., & Ponti, G. (2025). AI tutoring outperforms in-class active learning: an RCT introducing a novel research-based design in an authentic educational setting. *Scientific Reports, 15*, 17458. https://doi.org/10.1038/s41598-025-97652-6 (verified)

### Principle 2

- A Meta-Analysis of Ten Learning Techniques (2021). *Frontiers in Education*. https://doi.org/10.3389/feduc.2021.581216 TODO: authors, volume.
- Flavell, J. H. (1979). Metacognition and cognitive monitoring: A new area of cognitive-developmental inquiry. *American Psychologist, 34*(10), 906-911. https://doi.org/10.1037/0003-066X.34.10.906 TODO: confirm volume and pages.
- Rawson, K. A., & Dunlosky, J. (2022). Successive relearning: An underexplored but potent technique for obtaining and maintaining knowledge. *Current Directions in Psychological Science, 31*(4), 362-368. https://doi.org/10.1177/09637214221100484 (verified)
- Pan, S. C., Zung, I., Imundo, M. N., Zhang, X., & Qiu, Y. (2023). User-generated digital flashcards yield better learning than premade flashcards. *Journal of Applied Research in Memory and Cognition, 12*(4), 574-588. https://doi.org/10.1037/mac0000083 (verified)
- Lin & McDaniel (2018). TODO: full reference.

### Principle 3

- Zimmerman, B. J. (2002). Becoming a self-regulated learner: An overview. *Theory Into Practice, 41*(2), 64-70. https://doi.org/10.1207/s15430421tip4102_2 TODO: confirm title and pages.
- A qualitative systematic review on AI empowered self-regulated learning in higher education (2025). *npj Science of Learning*. https://www.nature.com/articles/s41539-025-00319-0 TODO: authors.
- A systematic literature review on designing self-regulated learning using generative artificial intelligence and its future research directions (2025). *Computers & Education*. https://doi.org/10.1016/j.compedu.2025.105465 TODO: authors.

### Background

- Lee, H.-P., Sarkar, A., Tankelevitch, L., Drosos, I., Rintel, S., Banks, R., & Wilson, N. (2025). The impact of generative AI on critical thinking. *CHI '25*, Article 1121. https://doi.org/10.1145/3706598.3713778 (verified per the project literature file)
- Prompting strategies with generative AI during learning from multiple sources (2026). *Learning and Instruction*. https://doi.org/10.1016/j.learninstruc.2026.102435 TODO: authors.
