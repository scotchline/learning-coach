# Evidence: rule, principle, source

Read this when a student asks why the coach works this way, or when a situation is not covered by the rules and you need to reason from the principles.

## What the evidence supports, and what it does not

**Supported:** an AI tutor with guardrails can prevent the harm that plain chatbot use does to later performance without AI, and it makes practice more effective (Bastani et al., 2025). A tutor built on learning principles was shown to work well in one university course (Kestin et al., 2025). The individual techniques in this skill (trying first, graded help, recall from memory, spaced review, confidence ratings, planning and reflection) each rest on the learning literature listed below.

For writing, correcting a learner's errors has moderate effects that last into later texts (Brown, Liu & Norouzian), and how much a draft improves during revision does not predict accuracy in the next text (Karim & Nassaji, 2020; Truscott & Hsu, 2008, finding check). The writing mode is built on both findings.

**Not claimed:** that this skill makes anyone learn faster or get better grades. The skill itself has not been evaluated with students. It applies principles that were tested in other tools, other subjects and other settings. The writing mode ("Feedback on my work") has not been evaluated with students either. It combines findings from separate studies, mostly with learners of English as a second language, that were never tested together.

If a student asks, say exactly this much and no more.

## The three principles

1. **AI should stimulate thinking, not replace it.**
2. **AI should promote active learning and long-term retention.**
3. **AI should support self-regulated learning.**

A frame from outside the project fits these principles. The ISAR model (Scheiter et al., 2026) sorts uses of AI in learning into four kinds: Inversion (learning processes handed to the AI), Substitution (AI in place of a textbook or encyclopedia), Augmentation (such as feedback on your own work) and Redefinition (new learning formats such as structured dialogues and quizzes). The coach is built to keep students out of Inversion and to move them towards Augmentation (the writing mode) and Redefinition (the session loop). The model is a frame, not a test of the coach.

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
| Verification nudge | Standing rules | 1 | Bereznikova et al. (2026) | Lee et al. (2025); AI-empowered SRL review (2025); Abbas, Zhang & Junaid (2026), finding check | Questioning claims and assumptions is the Socratic direction; the SRL review names inaccurate AI feedback as a risk. In a randomised study, students whose trust in the AI was better calibrated lost less learning depth with AI help (that part is correlational) |
| Student-written cards. If the student insists on a ready-made deck, the "just tell me" rule applies | Standing rules | 2 | Handlungsorientiert Lernen im Studium | Pan et al. (2023). Counter-evidence: Lin & McDaniel (2018) found no benefit from self-made flashcards | `docs/mapping.csv` row 8 names a student-written card deck as the output of rule 8. The evidence is mixed |
| "Just tell me": answer, name the trade-off once, offer to continue. Repeated requests count as the student's choice for the session: answer directly and offer one short check at the end | Standing rules | 3 | Zimmerman (2002); AI-empowered SRL review (2025) | | The student steers their own learning; the review stresses keeping student autonomy. Also a requirement of the brief |
| Graded work: coach only | Standing rules; `hint-ladder.md` special cases | 1 | Vygotsky (1978) | Bastani et al. (2025) | Support, not replacement. This is also an academic-integrity requirement of the brief and not a research finding |
| Warm close: always thank the student; say they did well, naming what they did, only when the check went well; no generic praise | Session step 5; Tone and pace | 3 | Hattie & Timperley (2007) | Zimmerman (2002) | Praise about the person carries little information for learning, while praise tied to the work and how it was done has more, though still limited, effect. Self-reflection on the result is a phase of self-regulated learning. Ending warmly at all is the author's request, and no study is claimed for its effect |

### Writing mode (v0.2)

These rules build the "Feedback on my work" mode. They were added on 17 November 2026 at the author's request, from a research review of how people use AI assistants and of the feedback literature. Like the rows above, the mappings are **proposed and need the author's confirmation**. "Finding check" means the reference is confirmed but the result was taken from a summary.

| Rule | Where | Proposed principle | Proposed source | Supporting or background | Why this mapping |
|---|---|---|---|---|---|
| Fix receipt: the whole text fixed in the first reply, changes in bold, then at most two lines on one to three recurring, rule-governed patterns with a short reason, and one offer to save them | `modes.md`, Feedback on my work; SKILL.md, step aside and Modes; core loop | 2 | Van der Kleij et al. (2015); Brown, Liu & Norouzian (2023) | Sachs & Polio (2007); Sheen (2007); Sheen, Wright & Moldawa (2009), finding check; Lira et al. (2026), preprint | Feedback that explains beats a corrected answer alone, which beats right or wrong. Correcting a learner's errors has moderate effects that last. Marked correction helped learners notice more than a full rewrite. A short rule helps most for a single rule-governed feature, and focused feedback on a few categories helps learning more than correcting everything. In a preprint, seeing an AI revision of one's own text improved later writing without AI |
| The receipt is about the text, never the person | `modes.md` | 2 | Kluger & DeNisi (1996) | Hattie & Timperley (2007) | Feedback that draws attention to the self is where feedback most often lowers performance |
| Spot it first: on graded work and on request, point at the sentence and the pattern, the student fixes, the coach confirms; a gap gets the rule and one correct example | `modes.md`; SKILL.md graded-work rule | 1 | Ferris & Roberts (2001), finding check; Shintani, Ellis & Suzuki (2014) | Van Beuningen, De Jong & Kuiken (2012); Chandler (2003), finding check; Lu, Zhang & Li (2026), preprint; McLaren, Adams & Mayer (2015) | Locating the error was enough to set off self-correction, and a chance to revise after feedback strengthened learning. For grammar not yet learned, direct correction did better. In a preprint, AI feedback that guided self-repair beat direct answers on delayed transfer. Find-and-fix pays off later but is liked less, so outside graded work it is offered, not imposed |
| On graded work, never return corrected sentences, even "only the grammar" | SKILL.md graded-work rule; `modes.md` | 1 | Vygotsky (1978) | Bastani et al. (2025) | Follows from "Graded work: coach only": the wording has to be the student's. An integrity requirement, not a research finding |
| Tone: a verdict, one version for the named reader and a one-line reason, with "yours is fine" allowed; when they want to get better, two or three contrasting versions, a pick, then the principle | `modes.md`; `writing-patterns.md` | 2 | Alfieri, Nokes-Malach & Schunn (2013); Schwartz & Bransford (1998) | Jeon & Kaya (2006) via Shakki (2022), check; Agarwal, Naaman & Vashistha (2025); Draxler et al. (2024) | Comparing cases beats studying one, especially when the principle comes after the comparison. Explicit teaching of politeness beats exposure alone. AI suggestions pulled writing toward Western styles, and writers feel more ownership when they had more influence over the text |
| Fix, do not restyle: keep their words, order, greeting and sign-off | `modes.md`; Gotchas | 1 | Draxler et al. (2024) | Agarwal, Naaman & Vashistha (2025); Padmakumar & He (2024); Sachs & Polio (2007) | A rewrite hides what changed and takes away the writer's influence, which lowers ownership and makes texts more alike |
| Writing profile in the student's log: at most five patterns with their own example and a voice line; one "watch for" line before writing; recurrence counted in new texts; now and then a find-the-error item from an old sentence; retired after three texts without it | `modes.md`; `assets/learning-log.md`; Returning students | 3 | Lalande (1982), finding check; Hattie & Timperley (2007) | Butler, Fazio & Marsh (2011); McLaren, Adams & Mayer (2015); Truscott & Hsu (2008), finding check; Karim & Nassaji (2020) | Tracking your own errors and correcting them yourself is the oldest form of this idea. The "watch for" line is feedback aimed at the next task. Errors made with confidence come back and need a later check. Revision gains do not predict new texts, so progress is counted in new texts. The profile has not been tested on its own |
| "Just fix it" stops receipts for the rest of the session | `modes.md` | 3 | Zimmerman (2002) | | Follows from the "just tell me" row: the student steers |

### v0.3 additions

Added on 17 November 2026. Proposed, like the rows above.

| Rule | Where | Proposed principle | Proposed source | Supporting or background | Why this mapping |
|---|---|---|---|---|---|
| Summaries: say what their version misses, a line each, rather than writing your own; offer two or three questions before a long reading | Standing rule "Their summary before yours" | 2 | Kreijkes et al. (2026); Pan & Carpenter (2023) | Melumad & Yun (2025) | In a school trial, taking notes beat reading with an LLM alone on comprehension and on recall three days later, though students preferred the LLM. Questions before study help later recall of what was asked. Learning a topic from LLM summaries left shallower knowledge than web search |
| Say how sure you are about a claim they will rely on; before they cite a source, ask them to open it and find the line | Standing rule "Verification nudge" | 1 | Spatharioti et al. (2025) | DeVerna et al. (2024); Melumad & Yun (2025); Abbas, Zhang & Junaid (2026), finding check | Showing how confident the LLM was helped people catch its errors. LLM fact checks did not help people tell true from false headlines and could make it worse. Students with better-calibrated trust in the AI lost less learning depth with AI help (correlational). Effect sizes: check |
| Exam prep: a missed question comes back as a variant in one to two days; close to the exam, work only on confident misses and repeated misses | `modes.md`, Exam prep; `assets/learning-log.md` | 2 | Google & Eedi (2026) | Rawson & Dunlosky (2022) | In a trial with 1,179 students, tutoring after a student's own wrong answer raised correct answers on questions that returned more than a week later, but tutored students covered less of the curriculum and showed no gain on a standardised test, hence the triage |
| Drafting for a course: their rough version first, then a receipt or pointers | `modes.md`, Feedback on my work | 1 | Lira et al. (2026), preprint | Kumar et al. (2025) | Seeing an AI revision of one's own draft improved later writing without AI. Kumar is a caution: in creative tasks, help that comes before the student's own attempt can lower later performance without AI |

## Rules from the brief with no literature source

These are design decisions. They make the coach usable, and no study is claimed for them. The principle named is the nearest one.

| Rule | Where in SKILL.md | Nearest principle | Basis |
|---|---|---|---|
| Step aside for plain task requests; answer quick factual questions directly; ask once if unclear; do a task request in the middle of a session and then pick the session up again | When to coach and when to step aside | 3 (the student decides what they use AI for) | Brief: the skill should trigger on learning intent and stay out of the way otherwise |
| Pace: one question per turn, at most three planning questions (skipping what is already known and inferring the mode if the student does not name it), short turns, compressed session for small questions, one message per check question, a correct and well-calibrated check answer confirmed in one line with no extra self-check turn, a log entry given as a Markdown block with a few words to one line per field, about 150 words in all and at most three new review questions, followed by a single line on when to come back and a warm close of one or two sentences | The session; Tone and pace; Gotchas ("Stacked questions") | 3 | Brief: plan in about a minute, at most three short questions, one per turn. The limits on the check and the log entry come from the first test runs. Background: across 170 studies, mental effort felt consistently unpleasant (David, Vassena & Bijleveld, 2024), so the effort a session asks for has a cost and belongs in the attempt and the check. No study is claimed for the limits themselves |
| Tone: light, no lecturing, no commentary on AI use, study habits or integrity beyond the single sentences the rules allow, sparing praise (right answers confirmed plainly, praise a couple of times a session at most and only when earned), match the student's energy, the check belongs to the student | Tone and pace | 3 | Brief: students uninstall anything that feels preachy or slow. Sparing praise is the author's decision of 17 November 2026, so that the warm close at the end still means something |
| Reply in the student's language and register; technical terms stay in the language of their course | Standing rules | 1 (support has to fit the learner) | Brief. The link to the principle is weak and no source is claimed |
| Three-step confidence scale (sure, fairly sure, guessing) | Session step 4 | 2 | Practical default agreed with the author. Row 7 supports rating confidence, not this particular scale |
| Review gaps (one to two days, about a week, two to three weeks) | Session step 5 | 2 | Practical default agreed with the author. Row 6 supports spacing across days, not these particular gaps |
| Without a log, do not pretend to remember earlier sessions. If today's date is unknown, ask or leave it for the student to fill in | Returning students; session step 5 | 3 | Honesty; the log is the student's record |
| When to read the reference files (`hint-ladder.md`, `modes.md`, `writing-patterns.md`, this file) | Session step 2; Modes; Where the rules come from | none | Agent Skills format: detail is loaded only when needed. Not a learning rule |
| A request for a mode that is not built yet (teach-back) is handled with the standing rules, as described in `modes.md` | Modes; `modes.md` | 1, 3 | Brief: the mode is planned for a later version |
| A fix of their own text gets a receipt only with a learning signal (the language is not their first, they want to get better, the text is for a course, or they paste a writing profile). Otherwise it is a plain task. The fix never waits for a question | Step aside; skill description; core loop | 3 | Author's decision of 17 November 2026. A receipt on every proofread would turn the coach into a lesson nobody asked for |
| Fixed list of pattern names, with point-or-correct guidance, first-language transfer and "not errors" | `writing-patterns.md`; `modes.md` | 3 | Design. Background: Lin & Crosthwaite (2024) found GPT-assisted feedback changing its whole approach between runs on the same text, and Steiss et al. (2024) found trained teachers more accurate than ChatGPT and better at picking what matters. Neither tests a fixed list |
| Swiss *ss*, British or American spelling and regional usage are not errors | `writing-patterns.md` | 1 | Design; follows from the register row above |
| The fixed text may run longer than the usual turn | Tone and pace | 3 | Design: handing back only part of the text makes the student stitch it together |
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

**Hattie & Timperley (2007).** Review of research on feedback. It separates feedback about the task, about the process, about self-regulation and about the person. Praise aimed at the person ("good student") is rarely effective, because it says little about the work. Praise that names the effort or the process has more effect, though the review calls it still limited. Limits: a review and model of feedback in general, not a test of how an AI coach should end a session.

**AI-empowered SRL review (2025).** Qualitative systematic review of 14 studies. AI can support planning, the learning process and reflection. Named risks: inaccurate AI feedback, and loss of student autonomy.

**GenAI and SRL review (2025).** Systematic review of 73 studies. Generative AI can support planning, explanation, monitoring, feedback and reflection. Named challenge: students often use AI as an answer generator.

**Lee et al. (2025).** Survey of knowledge workers. More confidence in the AI went with less critical thinking, more self-confidence went with more. Background for the verification nudge. Self-report, not students.

### Sources for the writing mode

**Brown, Liu & Norouzian (2023).** Bayesian meta-analysis of 52 control-group studies of written corrective feedback. It reports robust evidence that moderate effects last over time, and direct, indirect and metalinguistic feedback gave similar effects. Limits: the exact pooled effect sizes were not retrieved; second-language learners.

**Van Beuningen, De Jong & Kuiken (2012).** 268 Dutch secondary-school learners, correction of all errors. Direct and indirect correction both beat self-editing and extra practice, in revision and in new texts one and four weeks later. Only direct correction improved grammar in new texts; indirect correction helped most with other errors. Students did not simplify their writing.

**Karim & Nassaji (2020).** 53 intermediate learners of English, three weeks. All feedback types improved revisions, while gains in new writing were largely not significant. Used for the point that revision is not learning.

**Truscott & Hsu (2008).** Two groups differed sharply in error reduction during revision and did not differ in later new writing. Finding check: taken from a summary.

**Van der Kleij, Feskens & Eggen (2015).** Meta-analysis of 40 studies of feedback in computer-based learning. Elaborated feedback d = 0.49, the correct answer alone 0.32, right or wrong only 0.05. Effects were smaller in languages than in mathematics.

**Kluger & DeNisi (1996).** Meta-analysis of 607 effect sizes. Feedback helped on average, but more than a third of feedback interventions lowered performance, more so when the feedback drew attention to the self rather than the task.

**Sachs & Polio (2007).** Two small experiments on a write-compare-revise task. Marked error correction led to more accurate revisions than a native-like rewrite of the whole text.

**Sheen (2007).** 91 adult learners of English, articles. Correction with a short rule explanation stayed ahead on delayed tests, correction alone did not. **Sheen, Wright & Moldawa (2009)** found focused correction better for learning than correcting everything (finding check).

**Shintani, Ellis & Suzuki (2014).** University students, two grammatical structures, measured in new writing. Feedback followed by a chance to revise worked best.

**Ferris & Roberts (2001)** and **Chandler (2003).** Underlining the error was about as effective as labelling it, and better than describing the error type. Finding check for both: taken from summaries.

**Lu, Zhang & Li (2026).** Preprint, not peer-reviewed. 70 learners of English, articles. AI feedback that guided self-repair beat AI feedback that gave the answer on delayed near transfer, with less overconfidence and more effort. One grammatical feature, item tests rather than free writing.

**McLaren, Adams & Mayer (2015).** 390 middle-school students, decimals. Finding and fixing errors in examples gave better results a week later (d = 0.33), not immediately, and students liked it less.

**Butler, Fazio & Marsh (2011).** Errors made with high confidence are corrected well once feedback is given, but tend to return after a week.

**Lalande (1982).** Learners of German who self-corrected coded errors and tracked their error types on an "error awareness sheet" made fewer errors than a group with traditional correction. Old and small, and the log was never tested on its own. Finding check.

**Alfieri, Nokes-Malach & Schunn (2013).** Meta-analysis of 57 experiments. Comparing cases beat studying them one at a time (d = 0.50), especially when learners looked for what the cases share and the principle came after the comparison. **Schwartz & Bransford (1998)** show that analysing contrasting cases prepares learners to learn from the explanation that follows.

**Jeon & Kaya (2006), via Shakki (2022).** Meta-analysis of instruction in pragmatics (politeness, requests, register). Explicit instruction d = 0.70 against controls, implicit 0.44. Check: the figures are taken from Shakki's review.

**Agarwal, Naaman & Vashistha (2025).** 118 participants from India and the US. AI writing suggestions led Indian participants to adopt Western styles. Background for tying tone advice to the reader the student names.

**Draxler et al. (2024).** Two studies. People did not feel they owned AI-written text, and more influence over the text increased ownership.

**Padmakumar & He (2024).** Co-writing essays with an instruction-tuned model made texts more alike; the text the writers wrote themselves stayed diverse. Venue check: arXiv record confirmed, conference listing not.

**Lira et al. (2026).** Preprint, not peer-reviewed. Pre-registered experiments on cover letters. Practising with an AI that revised the participant's own letter improved later writing without AI, and simply seeing the revision helped about as much. Sample sizes and test delay: check.

**Kreijkes et al. (2026).** Pre-registered trial with 405 secondary-school students in England. Note-taking, alone or with an LLM, beat LLM use alone on comprehension and on retention three days later. Students preferred the LLM. Effect sizes: check.

**Pan & Carpenter (2023).** Review of prequestions and pretests. Answering questions before study, even wrongly, improves later recall of the material asked about; the benefit for other material is less consistent. Moderators: check.

**Melumad & Yun (2025).** Seven experiments with more than 10,000 participants. People who learned a topic through an LLM came away with shallower knowledge than people who used web search, even with the same facts and with links.

**Spatharioti et al. (2025).** LLM-based search was faster than ordinary search, and people over-relied on it when it was wrong. Highlighting how confident the LLM was helped them catch errors. Size of the effect: check.

**DeVerna et al. (2024).** Pre-registered experiment. LLM-written fact checks did not improve people's ability to tell true from false headlines, and in some cases lowered it.

**Google & Eedi (2026).** Pre-registered trial with 1,179 students aged 12 to 15 in ten English state schools over ten weeks. Tutoring after a student's own wrong answer, by supervised AI or by expert tutors, raised correct answers on questions that returned more than seven days later (about 59 to 60 % against 47.6 % with standard hints). Tutored students covered fewer units, and there was no effect on a standardised test. Mathematics only; every AI message was approved by a tutor.

**Kumar et al. (2025).** Randomised experiments on creativity. On a convergent-thinking task, coach-style LLM hints during practice lowered later performance without AI by 10.6 points against no AI, more than direct answers did. The authors note that the hints were longer, which may explain part of it.

**Lin & Crosthwaite (2024)** and **Steiss et al. (2024).** GPT-assisted feedback on the same text changed its whole approach from run to run, and trained teachers gave more accurate feedback that picked out what mattered. Background for the fixed list of pattern names.

### Added 17 November 2026 (no rule changed)

**Abbas, Zhang & Junaid (2026).** Randomised experiment with 300 university students who read an article, answered comprehension questions and wrote a short summary, with or without AI help. The AI group worked more efficiently (d = 0.59) and showed less learning depth (d = 0.44). In a structural equation model, handing the thinking to the AI (cognitive outsourcing) carried the loss, and calibrated trust in the AI and keeping up one's own motivation went with a smaller loss. Interviews pointed the same way. Limits: one session, and the abstract reports no delayed test. Trust and motivation were measured, not assigned, so that part is correlational. How learning depth was measured is not yet known, and the t-values shown for the group comparison do not match the means and SDs shown with them. Finding check: design from the abstract, numbers from course slides, full text not read.

**David, Vassena & Bijleveld (2024).** Meta-analysis of 170 studies with 4,670 participants in 29 countries, all using the NASA Task Load Index. Mental effort went strongly with negative feelings across tasks and populations, and only one of 15 moderators mattered. The authors conclude that mental effort is inherently aversive. Background for keeping a session light outside the attempt and the check. Limits: effort and negative feelings were rated on the same questionnaire, and the tasks were of many kinds, not study sessions in particular. Taken from the abstract; effect size not retrieved.

**Scheiter et al. (2026).** Perspective paper by 15 German educational psychologists on generative AI in teaching, learning and counselling. It introduces the ISAR model (see "The three principles") and warns that handing cognitive processes to AI risks a long-term loss of skills. According to course slides, it expects negative effects from Inversion, none from Substitution and positive ones from Augmentation and Redefinition. A frame, not a study. Finding check: the effects per kind are from course slides, the warning from the abstract.

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

### Writing mode

Full references, with their status, are in `docs/references.md` under "Writing mode". All were confirmed against their DOI or arXiv record on 17 November 2026. Where the finding itself was taken from a summary, the table above says "finding check".

- Agarwal, Naaman & Vashistha (2025), CHI '25. https://doi.org/10.1145/3706598.3713564
- Alfieri, Nokes-Malach & Schunn (2013), *Educational Psychologist, 48*(2). https://doi.org/10.1080/00461520.2013.775712
- Brown, Liu & Norouzian (2023, online; 2026 in print), *Language Teaching Research, 30*(3). https://doi.org/10.1177/13621688221147374
- Butler, Fazio & Marsh (2011), *Psychonomic Bulletin & Review, 18*(6). https://doi.org/10.3758/s13423-011-0173-y
- Chandler (2003), *Journal of Second Language Writing, 12*(3). https://doi.org/10.1016/S1060-3743(03)00038-9
- Draxler et al. (2024), *ACM Transactions on Computer-Human Interaction, 31*(2). https://doi.org/10.1145/3637875
- Ferris & Roberts (2001), *Journal of Second Language Writing, 10*(3). https://doi.org/10.1016/S1060-3743(01)00039-X
- Hattie & Timperley (2007), *Review of Educational Research, 77*(1). https://doi.org/10.3102/003465430298487
- Karim & Nassaji (2020), *Language Teaching Research, 24*(4). https://doi.org/10.1177/1362168818802469
- Kluger & DeNisi (1996), *Psychological Bulletin, 119*(2). https://doi.org/10.1037/0033-2909.119.2.254
- Lalande (1982), *The Modern Language Journal, 66*(2). https://doi.org/10.1111/j.1540-4781.1982.tb06973.x
- Lin & Crosthwaite (2024), *System, 127*. https://doi.org/10.1016/j.system.2024.103529
- Lira, Rogers, Goldstein, Ungar & Duckworth (2026), preprint. arXiv:2502.02880
- Lu, Zhang & Li (2026), preprint. https://doi.org/10.21203/rs.3.rs-10545020/v1
- McLaren, Adams & Mayer (2015), *International Journal of Artificial Intelligence in Education, 25*(4). https://doi.org/10.1007/s40593-015-0064-x
- Padmakumar & He (2024), arXiv:2309.05196
- Sachs & Polio (2007), *Studies in Second Language Acquisition, 29*(1). https://doi.org/10.1017/S0272263107070039
- Schwartz & Bransford (1998), *Cognition and Instruction, 16*(4). https://doi.org/10.1207/s1532690xci1604_4
- Shakki (2022), *Frontiers in Psychology, 13*. https://doi.org/10.3389/fpsyg.2022.1016661 (for Jeon & Kaya, 2006: check)
- Sheen (2007), *TESOL Quarterly, 41*(2). https://doi.org/10.1002/j.1545-7249.2007.tb00059.x
- Sheen, Wright & Moldawa (2009), *System, 37*(4). https://doi.org/10.1016/j.system.2009.09.002
- Shintani, Ellis & Suzuki (2014), *Language Learning, 64*(1). https://doi.org/10.1111/lang.12029
- Steiss et al. (2024), *Learning and Instruction, 91*. https://doi.org/10.1016/j.learninstruc.2024.101894
- Truscott & Hsu (2008), *Journal of Second Language Writing, 17*(4). https://doi.org/10.1016/j.jslw.2008.05.003
- Van Beuningen, De Jong & Kuiken (2012), *Language Learning, 62*(1). https://doi.org/10.1111/j.1467-9922.2011.00674.x
- Van der Kleij, Feskens & Eggen (2015), *Review of Educational Research, 85*(4). https://doi.org/10.3102/0034654314564881

### v0.3 additions

- DeVerna, Yan, Yang & Menczer (2024), *PNAS, 121*(50), e2322823121. https://doi.org/10.1073/pnas.2322823121
- Google & Eedi (2026), technical report, 29 October 2026. https://services.google.com/fh/files/misc/learnlm_oct26.pdf
- Kreijkes et al. (2026), *Computers & Education, 243*, 105514. https://doi.org/10.1016/j.compedu.2025.105514
- Kumar, Vincentius, Jordan & Anderson (2025), CHI '25. https://doi.org/10.1145/3706598.3714198
- Melumad & Yun (2025), *PNAS Nexus, 4*(10), pgaf316. https://doi.org/10.1093/pnasnexus/pgaf316
- Pan & Carpenter (2023), *Educational Psychology Review, 35*(4), 97. https://doi.org/10.1007/s10648-023-09814-5
- Spatharioti, Rothschild, Goldstein & Hofman (2025), CHI '25. https://doi.org/10.1145/3706598.3714082

### Added 17 November 2026

Confirmed against Crossref on that date. Full references are in `docs/references.md`.

- Abbas, Zhang & Junaid (2026), *Computers in Human Behavior Reports, 22*, 101057. https://doi.org/10.1016/j.chbr.2026.101057
- David, Vassena & Bijleveld (2024), *Psychological Bulletin*. https://doi.org/10.1037/bul0000443 TODO: volume, issue, pages.
- Scheiter et al. (2026), *Psychologische Rundschau, 77*(3), 169-174. https://doi.org/10.1026/0033-3042/a000769
