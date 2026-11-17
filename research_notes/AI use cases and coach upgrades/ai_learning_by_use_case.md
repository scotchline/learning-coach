# How AI help on specific study tasks affects learning: 2024–2026 evidence, by use case (as of Nov 2026)

Legend: **[verified-DOI]** = title, authors and venue confirmed against Crossref DOI metadata; **[verified-arXiv]** = confirmed on the arXiv abstract or HTML page (or arXiv listing with matching title and authors); **[verified-pub]** = read on the publisher's or author organisation's own page or PDF; **[check]** = details come from secondary coverage, abstracts or memory and need confirming before citation. "With AI" means performance while the tool is available. "Without AI" means a later test with the tool removed, which is the learning measure that matters.

## Cross-cutting anchors: what happens to unassisted performance after AI help?

### Takeaway
Across RCTs and field experiments, AI that hands over answers or does the work raises performance while the tool is there, and leaves later unassisted performance flat or lower. The harm grows with substitutive use and is worst for students with low prior knowledge. AI built as a tutor that holds back answers (and ideally has a human in the loop) usually avoids the harm, and can produce gains on near-transfer and curriculum tests. Broad standardised tests show small or null effects.

### Cited Findings
- **Bastani et al. 2025, PNAS** [verified-DOI 10.1073/pnas.2422633122]. Field RCT in Turkish high-school maths. Students with unrestricted GPT-4 ("GPT Base") solved 48% more practice problems correctly but scored 17% worse on the later unassisted exam. The guarded "GPT Tutor" (hints, no full answers) largely removed the exam harm but did not raise exam scores — [PNAS](https://doi.org/10.1073/pnas.2422633122); [Hechinger Report summary](https://hechingerreport.org/kids-chatgpt-worse-on-tests/). Sample size (about 1,000 students) and the GPT Tutor practice gain (+127%) are from memory [check].
- **Kestin et al. 2025, Scientific Reports** [verified-DOI 10.1038/s41598-025-97652-6]. RCT in a Harvard physics course comparing a research-designed AI tutor with in-class active learning. The paper's title claims AI tutoring "outperforms in-class active learning" — [Sci Rep](https://doi.org/10.1038/s41598-025-97652-6). Figures recalled from memory: N≈194, learning gains more than double, effect sizes about 0.73–1.3 SD, less time on task [check].
- **Lehmann, Cornelius & Sting, "AI Meets the Classroom: When Do Large Language Models Harm Learning?"** (preprint, arXiv 2409.09047 v2, 8 Mar 2025; v1 and SSRN titled "When Does ChatGPT Harm Learning?") [verified-arXiv; SSRN v1 verified-DOI 10.2139/ssrn.4941259] — [arXiv v2](https://arxiv.org/html/2409.09047v2):
  - Design: two pre-registered, incentivised lab experiments on learning Python (Germany, June 2024). Study 2 had n=107; Study 3 had n=69 with copy-paste enabled. The 45-minute learning phase had ChatGPT (gpt-3.5-turbo) available only to the treatment group, and the post-test was taken without the LLM. A field study covered two Dutch graduate Python courses (113 students, 6,594 student-question observations), using ChatGPT outages as an instrument.
  - Overall lab effect on the post-test: null (Study 2: +0.396, SE 0.713, p=0.58; Study 3: +0.959, SE 0.912, p=0.30).
  - Mechanism: requesting **solutions** lowered understanding (−0.312, p<0.01), while requesting **explanations** raised it (+0.249, p<0.05). Enabling copy-paste increased volume covered (+1.733, p<0.05), reduced understanding (−1.407, p<0.01), and tripled solution requests (+3.066).
  - Prior knowledge: the LLM widened the gap. Treated students below the median pre-test understood less than controls (p=0.043); the interaction for those above the median was +2.528 (p=0.028).
  - Students with LLM access *felt* they had learned more (+0.338 on a 5-point scale, p=0.044) despite no gain.
  - Field: cumulative ChatGPT-identical submissions predicted lower later grades (FE2SLS −0.06 on a 0–1 scale, p=0.002).
  - Limits: GPT-3.5, short sessions, no delayed retention in the lab, and the field study proxies use through code similarity.
- **Barcaui 2025/2026, "ChatGPT as a cognitive crutch"** (SSRN preprint verified-DOI 10.2139/ssrn.5353041; journal version in *Social Sciences & Humanities Open*, [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S2590291125010186) [check DOI]). RCT with n=120 undergraduates who studied with ChatGPT or with traditional methods. On a surprise test 45 days later, the ChatGPT group scored 57.5% vs 68.5% (t(83)=−3.19, p=.002, d=0.68), after spending 3.2 h vs 5.8 h on the assignment. Frequent AI users were not protected — [PsyPost](https://www.psypost.org/chatgpt-acts-as-a-cognitive-crutch-that-weakens-memory-new-research-suggests/). Limits: single institution, small sample, and population described inconsistently across outlets [check].
- **Fan et al. 2024, BJET, "Beware of metacognitive laziness"** [verified-DOI 10.1111/bjet.13544]. ChatGPT support improved the immediate essay task score, but not knowledge gain or transfer, compared with human expert, checklist and control conditions. The authors coined "metacognitive laziness" — [BJET](https://doi.org/10.1111/bjet.13544). N≈117 and the exact conditions are from memory [check].
- **Darvishi et al. 2024, Computers & Education 210:104967** [verified-DOI 10.1016/j.compedu.2023.104967]. Randomised experiment with 1,625 students across 10 courses writing peer feedback. Conditions were AI prompts, none, self-monitoring checklists, or both. Students "tended to rely on rather than learn from AI assistance". When AI was removed, checklists partly filled the gap but were less effective than AI, and the AI+checklist hybrid was no better than AI alone — [PsyPost](https://psypost.org/students-tend-to-rely-on-ai-rather-than-learn-from-it-study-finds); [Adelaide repository](https://digital.library.adelaide.edu.au/items/99e9a0ee-4feb-405c-8e66-062c6b67aa11). Effect sizes not retrieved [check].
- **De Simone et al. 2025, World Bank Policy Research Working Paper 11125, "From Chalkboards to Chatbots"** [verified-pub: World Bank OKR / RePEc wbrwps:11125]. RCT of a 6-week, teacher-guided after-school programme in Nigeria using Microsoft Copilot (GPT-4) for English. Reported effects: about 0.31 SD on a composite test (English, AI knowledge, digital skills), about 0.23 SD on English, ITT 0.21 SD on the regular third-term exam (an unassisted test), and dose-response of about 0.031 SD per extra day attended — [World Bank OKR](https://openknowledge.worldbank.org/entities/publication/15e1ff08-15ae-4f7a-b2a8-d146e6c113ee/full); [RePEc](https://econpapers.repec.org/RePEc:wbk:wbrwps:11125). Secondary sources disagree on which number is the headline [check exact table values]. Limits: short duration, structured prompts and teacher facilitation (not free student use), and the full-year projections (1.2–2.2 SD) are extrapolations.
- **Wang et al. 2024/2025, Tutor CoPilot** (preprint, arXiv 2410.03017) [verified-arXiv]. RCT of LLM real-time suggestions to human tutors (900 tutors, 1,800 K-12 students per arXiv; J-PAL reports 783 tutors). Students were 4 pp more likely to master topics (ITT), with +9 pp for students of lower-rated tutors. Cost about $20 per tutor per year — [arXiv](https://arxiv.org/abs/2410.03017); [J-PAL](https://www.povertyactionlab.org/print/pdf/node/8137812?lang=en). Limits: mastery is a within-platform exit-ticket measure, not a standardised test.
- **LearnLM Team, Google & Eedi 2025, exploratory RCT** (preprint, arXiv 2512.23633) [verified-arXiv listing]. N=165 Year 9–10 students in 5 UK schools, May–June 2025. Static hints were compared with 1:1 chat tutoring by humans or by LearnLM supervised by tutors. LearnLM performed "at least as well" as human tutors. Novel-problem success on later topics was 66.2% vs 60.7% (+5.5 pp) — [arXiv](https://arxiv.org/abs/2512.23633v1); [Eedi press release](https://www.eedi.com/news/new-exploratory-research-from-eedi-and-google-deepmind-reveals-human-in-the-loop-ai-tutoring-outperforms-human-only-support). Press framing ("outperforms") is stronger than the paper's.
- **LearnLM Team, Google & Eedi, 29 Oct 2026, "Measuring the impact of AI tutoring, from near transfer to standardised tests: An expanded RCT in UK mathematics classrooms"** [verified-pub: Google PDF read in full] — [Google PDF](https://services.google.com/fh/files/misc/learnlm_oct26.pdf):
  - Design: pre-registered, student-level RCT; N=1,179 in 10 UK state secondary schools over 10 weeks. Four conditions: Eedi standard remediation (diagnostic hints and videos, an active, evidence-based control), expert human tutoring, Gemini tutoring with a pedagogical prompt, and Gemini plus personalised context. The prompt told Gemini to "guide students through their misconceptions step by step with concise, scaffolded questions, without giving away the correct answer." Expert tutors reviewed every draft and approved 94.7% of 94,385 unchanged; maths errors appeared in fewer than 3 per 1,000 messages.
  - Proximate (correcting the immediate mistake): AI 56.9% / 56.5% vs expert 57.7% vs remediation 43.4%.
  - Near transfer (next unit's first question): AI 58.4% / 58.3% vs expert 59.1% vs remediation 50.5%.
  - Mid-trial 8-item quiz: AI 62.1% / 63.5% vs expert 61.8% vs remediation 59.6% (97.1% posterior probability that personalised AI beat remediation).
  - Delayed retrieval (question returning more than 7 days after the miss): AI 59.9% / 59.0% vs expert 58.9% vs remediation 47.6%.
  - **Standardised Star Maths: no overall effect** (AI −0.01 SD [−0.15, +0.14] and +0.02 SD [−0.12, +0.16]; expert −0.09 SD).
  - Explanation offered: a depth-versus-breadth trade-off. Tutored students completed a median of 99 study units (AI) or 77 (expert) vs 132 (remediation), and covered 57 / 48 vs 72 constructs. Each +1 SD of units completed predicted +0.09 SD on Star Maths.
  - Girls benefited more; tutored boys showed less comfort with mistakes. No overall shift in self-efficacy or motivation.
  - Gemini asked end-of-session understanding checks far more often than human tutors did.
  - Limits: company-authored; Bayesian estimates; 10 weeks may be too short for broad gains.
- **Gerlich 2025, Societies 15(1):6** [verified-DOI 10.3390/soc15010006]. Survey and interviews with 666 participants: frequent AI use correlates negatively with critical thinking (Halpern assessment), mediated by cognitive offloading; younger participants were more AI-dependent and scored lower — [DOAJ](https://doaj.org/article/d5c17dd91ce64775a065095d8af730ce). It is **correlational**; r values not retrieved [check].
- **Lee et al. CHI 2025** [verified-DOI 10.1145/3706598.3713778]. Survey of knowledge workers: higher confidence in GenAI was associated with less self-reported critical thinking — [ACM](https://doi.org/10.1145/3706598.3713778). N=319 and 936 examples are from memory [check]. Self-report only.

### Inferences
- The consistent signature is that **performance with AI goes up while learning without AI stays flat or falls**. A coach should judge any feature by a later no-AI check, never by in-session success.
- Three moderators recur: (a) substitution vs complement (Lehmann; Shen & Tamkin, see coding); (b) prior knowledge (Lehmann, Prather) — weaker students are harmed more by free AI; (c) guardrails, structure and human facilitation (Bastani GPT Tutor, Nigeria, Eedi, Tutor CoPilot).
- Students consistently feel they learned more with AI (Lehmann; Kreijkes, see summarising; Prather). Self-ratings are therefore a poor signal for the coach to rely on.
- Eedi's null on a standardised test is a caution: tutoring that makes students work through every mistake buys depth at the cost of coverage. A coach should balance "work through it" against "move on".

### Gaps
- Few studies have delayed (weeks or more) unassisted tests. Barcaui (45 days) and Eedi (7+ days) are rare exceptions.
- Effect sizes for Darvishi and Gerlich, and exact Nigeria table values, were not retrieved.

## Use case 1 — Explaining concepts

### Takeaway
Asking AI to *explain* (rather than to *solve*) is the most learning-friendly common use: it improved understanding in Lehmann's lab study, and conceptual-question patterns preserved learning in Anthropic's RCT. Explanations still produce shallower knowledge than active search or note-making unless the student does something generative with them.

### Cited Findings
- Lehmann et al.: explanation requests raised understanding (+0.249, p<0.05), while solution requests lowered it (−0.312, p<0.01). Neither shifted the total post-test score significantly — [arXiv v2](https://arxiv.org/html/2409.09047v2).
- Shen & Tamkin 2026 (Anthropic; preprint arXiv 2601.20245) [verified-pub + arXiv ID on publisher page]. Participants following the "conceptual inquiry" pattern (asked only conceptual questions, fixed errors themselves; n=7) averaged ~65% on the quiz, versus ~24–39% for delegation patterns. "Generation-then-comprehension" (got code, then asked follow-up why-questions; n=2) averaged ~86% — [Anthropic](https://www.anthropic.com/research/AI-assistance-coding-skills). Pattern groups are tiny and correlational.
- Kreijkes et al. 2026, Computers & Education 105514 [verified-DOI 10.1016/j.compedu.2025.105514]. Pre-registered RCT with 405 English students aged 14–15 in 7 schools. Note-taking alone, or note-taking plus LLM, beat LLM-only on comprehension and on retention 3 days later. Students preferred the LLM and rated it more helpful. The authors suggest LLMs may aid initial understanding and interest, and that notes should be taken separately so students don't copy the LLM — [Microsoft Research](https://www.microsoft.com/en-us/research/?p=1143413); [CMOtech](https://cmotech.uk/story/teenagers-learn-more-from-handwritten-notes-than-ai). Effect sizes not retrieved [check].
- Pardos & Bhandari 2024, PLOS ONE [verified-DOI 10.1371/journal.pone.0304013]. ChatGPT-generated help produced learning gains equivalent to human tutor-authored help on maths skills — [PLOS ONE](https://doi.org/10.1371/journal.pone.0304013). Sample and design details not retrieved [check].
- Kestin et al. 2025: an AI tutor designed around research-based pedagogy (structured, step-wise, not answer-dumping) outperformed active-learning class time — [Sci Rep](https://doi.org/10.1038/s41598-025-97652-6) (numbers [check]).
- Melumad & Yun 2025 (PNAS Nexus) shows that LLM *explanations/summaries* of a topic yield shallower knowledge than web search; see Use case 2 — [PNAS Nexus](https://doi.org/10.1093/pnasnexus/pgaf316).

### Inferences
- Design pattern: **explanation on request, solution withheld**. Pair it with **self-explanation back to the AI** (student restates in own words; AI probes) and **separate note-making**. These convert a passive explanation into generation (see learning-science section).
- "Generation-then-comprehension" suggests a safe fallback when a student insists on an answer: give it, then require them to explain why it works before moving on.

### Gaps
- No RCT isolates "AI explains first" vs "student attempts, then AI explains" for conceptual material. Akgun & Toker (below) are closest.

## Use case 2 — Summarising readings

### Takeaway
Replacing reading with an AI summary reliably produces shallower knowledge. The strongest evidence is a 7-experiment, >10,000-participant study and a 405-student school RCT. Summaries may help as an orientation *before* reading, or as something to *compare against* one's own summary, but not as a substitute.

### Cited Findings
- **Melumad & Yun 2025, PNAS Nexus, pgaf316** [verified-DOI 10.1093/pnasnexus/pgaf316]. Seven experiments, >10,000 participants, randomly assigned to learn a topic via ChatGPT or Google and then write advice. LLM learners spent less time, reported shallower knowledge, and wrote shorter, more generic advice. 1,501 independent evaluators rated that advice less helpful, informative and trustworthy. The effect held with identical facts, with real-time links in the LLM, and for Google AI Overviews vs standard results. Mechanism: summaries stop users from discovering and synthesising sources themselves — [PsyPost](https://www.psypost.org/learning-from-ai-summaries-leads-to-shallower-knowledge-than-web-search/); [Science News](https://www.sciencenews.org/article/ai-chatbots-learning-superficial-llm). Limits: adult online samples; the outcome is advice quality and self-reported depth, not a formal knowledge test.
- **Kreijkes et al. 2026** (above): LLM-only reading support underperformed note-taking on comprehension and on 3-day retention — [MSR](https://www.microsoft.com/en-us/research/?p=1143413).
- A Chinese university study (via search summary) found that leaning on machine summaries displaced connecting, exemplifying and restating ideas, and this displacement accounted for lower comprehension. Highly motivated readers showed no indirect cost [check: source not pinned; surfaced in a search summary alongside [Frontiers in Psychology 2026](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2026.2002898/full)].

### Inferences
- Design patterns: (1) **summarise-first-yourself, then compare with AI's summary** (generation, then feedback); (2) use AI to produce **prequestions** before reading rather than answers after; (3) **AI as checker** of the student's summary (missing points, misreadings), not author.
- A coach should label "read the AI summary instead" as a coverage strategy (useful for triage) that trades away depth.

### Gaps
- A reported pre-registered ACT-passage study finding that summaries hurt higher-performing readers could not be attributed to a confirmed source (possibly [arXiv 2509.18664](https://arxiv.org/html/2509.18664v1)) [check].
- No RCT found testing "AI summary as advance organiser before full reading" vs reading alone.

## Use case 3 — Brainstorming / idea generation (and AI-assisted writing)

### Takeaway
AI ideas raise the quality of the product made with AI but tend to homogenise outputs and do not improve, and can harm, later unassisted creativity. Surprisingly, coach-style hints harmed later unassisted convergent thinking more than direct answers did. Thinking first protects ownership. Seeing an AI-improved version of *one's own* writing can teach.

### Cited Findings
- **Kumar, Vincentius, Jordan & Anderson, CHI 2025** [verified-DOI 10.1145/3706598.3714198; arXiv 2410.03703 verified-arXiv] — [arXiv](https://arxiv.org/html/2410.03703v2):
  - Design: two pre-registered experiments (Prolific; N=460 on the Alternate Uses Task; N=640 on the Remote Associates Test), each with an AI-assisted exposure phase and then an unassisted test.
  - AUT: LLM idea lists did not improve originality. A "List of Strategies" condition made later unassisted originality worse than no LLM (p=0.009) and made ideas less diverse (p=0.017).
  - RAT: direct LLM answers gave the highest exposure scores (~80% vs ~60%). On the unassisted test, **LLM Guidance (coach-style hints, no answer) scored 10.6 points below no-LLM** (95% CI −18.6 to −2.7, p=0.005); LLM Answer was not significantly different from no-LLM.
  - Self-rated creativity fell most after Guidance.
  - Limits: short, lab-based verbal tasks; static (non-conversational) AI; guidance outputs were more verbose (possible load confound).
- **Doshi & Hauser 2024, Science Advances** [verified-DOI 10.1126/sciadv.adn5290]. Access to GPT-4 story ideas raised rated creativity (mostly for less creative writers) but made stories more similar to each other — [Sci Adv](https://doi.org/10.1126/sciadv.adn5290). Sample size and percentages are from memory [check].
- **Kosmyna et al. 2025, "Your Brain on ChatGPT"** (preprint, arXiv 2506.08872) [verified-arXiv]. 54 participants wrote essays with an LLM, with search, or "brain-only" under EEG over 3 sessions. In session 4 (n=18), LLM-to-brain switchers showed weaker connectivity and poor recall of their own essays ("cognitive debt"). Brain-to-LLM switchers showed stronger recall and engagement — [arXiv](https://arxiv.org/abs/2506.08872); [MIT Media Lab](https://www.media.mit.edu/publications/your-brain-on-chatgpt/). Limits: small and not peer-reviewed; session 4 depended on availability.
- **Lira, Rogers, Goldstein, Ungar & Duckworth, "Coach not crutch: Evidence that AI can improve writing skill despite reducing effort"** (preprint, arXiv 2502.02880, v4 18 Feb 2026; earlier title "Learning not cheating") [verified-arXiv]. Pre-registered experiments on cover-letter writing:
  - Practising with an AI tool that rewrote the participant's own letter to apply taught principles improved later **no-AI** writing more than practising alone (Exp 1), than googling examples, or than human-editor feedback (Exp 2), despite less effort.
  - Simply *viewing* the AI-revised version of one's own letter helped as much as practising with the tool (Exp 3).
  - Mechanism claimed: AI "teaches by example" — [arXiv](https://arxiv.org/abs/2502.02880); [HKS](https://www.hks.harvard.edu/publications/learning-not-cheating-ai-assistance-can-enhance-rather-hinder-skill-development).
  - Sample sizes and the test delay (reported elsewhere as one day) are not in the abstract [check].
- Order effects (mixed, mostly non-peer-reviewed):
  - A two-experiment student study (n=170, 176), reported by Psychology Today, found that generating one's own ideas before ChatGPT increased initiative, ownership and effort, but students drifted toward the AI by the third prompt unless every prompt demanded an original idea — [Psychology Today](https://www.psychologytoday.com/us/blog/in-one-lifespan/202607/how-do-you-hold-on-to-your-own-thinking-with-ai) [check: primary paper not identified].
  - Contradicting this, a crossover study of 728 undergraduate design-engineering ideas found AI-first students produced more original and diverse ideas — [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S187118712500207X) [check].
  - In a KICSS 2025 study, GenAI reduced human-generated ideas in groups — [arXiv 2512.20628](https://arxiv.org/pdf/2512.20628) [check].

### Inferences
- Patterns: **think-first (own ideas before AI)**, **require an original contribution at each turn**, and **compare-your-version-with-AI** (Lira: AI rewrite of *your own* draft as a personalised worked example).
- Kumar's result warns that Socratic hinting is not automatically protective. Verbose guidance on short insight tasks may add load or disrupt the student's own search. Keep hints short and let the student finish the problem unaided.

### Gaps
- No student-population RCT with a delayed, unassisted test of brainstorming after weeks of AI use.

## Use case 4 — Coding and debugging for novices (incl. Copilot / Claude Code-style assistants)

### Takeaway
Code-generating AI raises task completion but, when used to delegate, cuts understanding — especially debugging skill — by roughly two letter grades in Anthropic's RCT. Novices with low prior knowledge or weak metacognition are hurt most. Patterns that kept learning were conceptual questions only, asking "why" after generated code, "friction" techniques that make students articulate or trace before seeing code, and assistants that give pseudo-code and explanations rather than solutions.

### Cited Findings
- **Shen & Tamkin 2026, "How AI assistance impacts the formation of coding skills"** (Anthropic; preprint arXiv 2601.20245) [verified-pub; arXiv ID from publisher page] — [Anthropic](https://www.anthropic.com/research/AI-assistance-coding-skills); [arXiv PDF](https://www.arxiv.org/pdf/2601.20245):
  - Design: RCT, N=52 mostly junior engineers learning the unfamiliar Trio async library. A sidebar AI could see their code and write correct code; the control coded by hand. A 25-min quiz without AI followed.
  - Quiz: 50% vs 67% (Cohen's d=0.738, p=0.01). The largest gap was on debugging questions. The speed gain was not significant (~23 vs ~25 min, p=0.391).
  - Low-scoring patterns: full delegation ~39%; progressive reliance ~35%; **"iterative AI debugging" ~24%**.
  - High-scoring patterns: generation-then-comprehension ~86%; hybrid code+explanation ~68%; conceptual inquiry ~65%.
  - Limits: small groups per pattern; immediate test only; sidebar chat, not agentic tools. The authors expect agentic tools such as Claude Code may affect skill formation more strongly.
- **Kazemitabaar et al. CHI 2023** [verified-DOI 10.1145/3544548.3580919; arXiv 2302.07427]. 69 novices aged 10–17 learning Python with or without Codex. Codex gave 1.15× completion and 1.8× scores on code-authoring tasks, with no loss on manual modification. On one-week retention post-tests the Codex group did slightly (non-significantly) better; learners with higher Scratch pre-test scores benefited significantly more — [arXiv](https://arxiv.org/pdf/2302.07427); [UMD PDF](https://terpconnect.umd.edu/~weintrop/papers/Kazemitabaar_et_al_CHI_2023.pdf). A follow-up thematic analysis (n=33) found over-reliance and self-regulation problems — [arXiv 2309.14049](https://arxiv.org/pdf/2309.14049) [check].
- **Kazemitabaar et al. CHI 2024, CodeAid** [verified-DOI 10.1145/3613904.3642773]. Semester-long classroom deployment of an LLM assistant designed *not* to reveal solution code (pseudo-code, annotated explanations, fix suggestions) — [ACM](https://doi.org/10.1145/3613904.3642773). Deployment size (~700 students, 12 weeks) is from memory [check].
- **Kazemitabaar, Huang, Suh, Henley & Grossman, IUI 2025, "Exploring the Design Space of Cognitive Engagement Techniques with AI-Generated Code for Enhanced Learning"** [verified-DOI 10.1145/3708359.3712104; arXiv 2410.08922]. Seven "friction" techniques were tested between-subjects (N=82), then refined in a within-subjects study (N=42) with isomorphic tasks done without AI.
  - **Lead-and-Reveal**: AI walks through steps and reveals code only after the learner articulates reasoning.
  - **Trace-and-Predict**: the learner traces with sample input and predicts variable values.
  - These two were the most balanced. Lead-and-Reveal better aligned perceived and actual ability, without raising cognitive load — [arXiv](https://arxiv.org/html/2410.08922v1); [author PDF](https://austinhenley.com/pubs/Kazemitabaar2025IUI_AIFriction.pdf). Exact statistics not retrieved [check].
- **Prather et al. ICER 2024, "The Widening Gap"** [verified-DOI 10.1145/3632620.3671116; arXiv 2405.17739]. 21 novices observed with eye tracking and interviews. 20/21 finished, but students who were already strong used GenAI to accelerate code they had planned. Strugglers had their metacognitive difficulties compounded (eight identified, three new and GenAI-specific) and left with an illusion of competence — [arXiv](https://arxiv.org/abs/2405.17739). Limits: qualitative, single site.
- Lehmann et al. (Python): solution requests and copy-paste cut understanding; the field study showed cumulative harm to later grades (see the cross-cutting section) — [arXiv](https://arxiv.org/html/2409.09047v2).

### Inferences
- Map to coach upgrades:
  - **Explain-the-bug first**: the student states a hypothesis about why the code fails before the AI responds. This targets the skill Anthropic found most eroded (debugging), and "AI debugs for me" was the worst pattern.
  - **Trace-and-predict** before running the code.
  - **Lead-and-reveal**: code only after the plan is articulated.
  - **Pseudo-code, not code** (CodeAid).
  - **Ask-why-after-generation** as the minimum when code is given.
- For agentic tools (Claude Code / Copilot agents), the risk is plausibly greater (Anthropic's own caveat). Learning or Explanatory output styles exist, but no outcome evaluation of them was found.

### Gaps
- No RCT found on Claude Code's Learning or Explanatory modes, or on Copilot in CS1, with a delayed unassisted test.

## Use case 5 — Research, source finding and fact-checking

### Takeaway
LLM-based search makes research faster and easier but yields shallower reasoning and knowledge than conventional search. It produces over-reliance when the AI is wrong, and LLM "fact checks" can make people *worse* at telling true from false headlines. Fabricated citations remain common. Interface cues showing AI uncertainty partly fix over-reliance.

### Cited Findings
- **Stadler, Bannert & Sailer 2024, Computers in Human Behavior 160:108386** [verified-DOI 10.1016/j.chb.2024.108386]. 91 university students randomly assigned to ChatGPT-3.5 or Google to research nanoparticles in sunscreen (a socio-scientific inquiry task). The ChatGPT group reported significantly lower cognitive load but produced lower-quality reasoning and justifications in their recommendations. Homogeneity of recommendations did not differ. Germane load predicted justification quality — [PsyPost](https://psypost.org/study-finds-chatgpt-eases-students-cognitive-load-but-at-the-expense-of-critical-thinking); [TUM](https://www.edtech.tum.de/?p=2430). Effect sizes not retrieved [check].
- **Melumad & Yun 2025** (above): even with identical facts, or with links included, LLM-mediated learning was shallower than web search — [PNAS Nexus](https://doi.org/10.1093/pnasnexus/pgaf316).
- **Spatharioti, Rothschild, Goldstein & Hofman, CHI 2025, "Effects of LLM-based Search on Decision Making: Speed, Accuracy, and Overreliance"** [verified-DOI 10.1145/3706598.3714082; earlier arXiv 2307.03744]. LLM search was faster with fewer queries and matched traditional search accuracy when the LLM was right, but users over-relied when it erred. Colour-coded confidence highlighting improved error detection and decision accuracy — [Microsoft Research](https://www.microsoft.com/en-us/research/?p=1134789); [arXiv](https://arxiv.org/abs/2307.03744). The "roughly doubled detection" figure is secondary [check].
- **DeVerna, Yan, Yang & Menczer 2024, PNAS** [verified-DOI 10.1073/pnas.2322823121]. Pre-registered RCT: LLM-generated fact checks did not improve headline discernment and could decrease it — [PNAS](https://doi.org/10.1073/pnas.2322823121). Mechanism recalled from memory: less belief in true headlines the AI mislabelled, more belief in false ones when the AI was unsure; N≈2,159 [check].
- Citation fabrication: GPT-4o fabricated 19.9% of citations across six simulated mental-health literature reviews (JMIR, Nov 2025), with reliability depending on topic and prompt — [EurekAlert](https://www.eurekalert.org/news-releases/1106130) [check primary paper].

### Inferences
- Patterns: **AI for query generation and leads, the student reads and evaluates the primary sources**. **Verify-every-citation** (open it, quote the line). **Show uncertainty**: ask the AI for confidence or disagreement and flag weak claims. **Student writes the argument before asking the AI to critique it** (keeps germane load).
- For fact-checking, the coach should never present an AI verdict as the check. It should teach lateral reading and have the AI point to sources the student must open.

### Gaps
- No RCT found on students learning research skills with AI scaffolds (e.g., an AI that only suggests search terms) with a delayed, unassisted research-quality test.

## Use case 6 — Exam prep and practice questions

### Takeaway
Using AI to solve practice problems is the clearest documented harm (−17% on the exam in Bastani). Using AI as a tutor *on practice the student attempts* (hints, misconception diagnosis, follow-up checks) improves near-transfer and delayed retrieval (Eedi). AI-*generated* practice questions look psychometrically comparable to human-written ones, but rigorous RCTs of studying with them are lacking. Retrieval-practice science predicts benefit if the student answers before seeing feedback.

### Cited Findings
- Bastani et al. 2025: practice with answer-giving GPT gave +48% practice performance and −17% exam; the hint-giving tutor avoided most of the harm — [Hechinger](https://hechingerreport.org/kids-chatgpt-worse-on-tests/); [PNAS](https://doi.org/10.1073/pnas.2422633122).
- Eedi/LearnLM Oct 2026: tutoring after a *student's own wrong answer* raised delayed (>7-day) correct answers on returning questions to ~59–60% vs 47.6% with hints-only remediation. The Star Maths null shows the trade-off with coverage — [Google PDF](https://services.google.com/fh/files/misc/learnlm_oct26.pdf).
- Barcaui: studying with ChatGPT gave lower 45-day retention (d=0.68) despite faster study — [PsyPost](https://www.psypost.org/chatgpt-acts-as-a-cognitive-crutch-that-weakens-memory-new-research-suggests/).
- AI-generated MCQs: a 2026 single-centre RCT in medical education found AI-generated and student-generated mock exams performed comparably psychometrically (73.4% ± 12.3% vs 71.0% ± 9.0%). This tests question quality, not learning — [BMC Med Educ](https://link.springer.com/article/10.1186/s12909-026-09671-0) [check].
- A data-science course study found LLM-generated retrieval practice was associated with higher quiz scores vs no-practice weeks (non-randomised), but students scored ~9% lower on LLM-authored than on human-authored items — [arXiv 2507.05629](https://arxiv.org/pdf/2507.05629) [check].
- A retrospective cohort comparison (JITE 2025) reported higher final exams after ChatGPT-assisted retrieval practice; observational only — [Informing Science](https://www.informingscience.org/Publications/5474) [check].
- Henkel et al. 2024 (AIED/CCIS), Rori WhatsApp maths tutor in Ghana: positive effects on maths growth — [Springer](https://doi.org/10.1007/978-3-031-64315-6_34) [verified-DOI]. Effect size (~0.37 SD) is from memory [check].

### Inferences
- Patterns: **attempt-first, then AI feedback on the attempt** (not AI solving). **AI generates questions, the student answers closed-book**. **Interleave topics** in AI-generated sets. **Spaced re-asking of missed items** (Eedi's returning-question mechanic is successive relearning). **End-of-session understanding checks** (a distinctive behaviour of Gemini in Eedi).
- Quality-control AI-generated items (difficulty calibration was weaker in one study).

### Gaps
- No found RCT randomising students to study with AI-generated retrieval practice vs restudy, with a delayed exam.

## Use case 7 — Translation and language learning

### Takeaway
Evidence is thin and mostly quasi-experimental. ChatGPT-supported vocabulary instruction shows immediate gains with weaker or uncertain delayed retention. Feedback that keeps learners revising appears to transfer to later no-AI writing. Letting learners adopt AI phrasing or translations is linked to lower autonomy. No randomised study of machine translation's effect on L2 acquisition was found.

### Cited Findings
- **Abdelhalim & Alsehibany 2025, Language Learning & Technology** [verified-DOI 10.64152/10125/73635]. Saudi EFL classroom study: ChatGPT improved productive vocabulary and overall test scores, but its effect on 4-week delayed retention was not clearly significant. The authors call the delay preliminary — [LLT](https://scholarspace.manoa.hawaii.edu/server/api/core/bitstreams/b1e20acf-9803-480b-83e3-dda1e8470b9f/content).
- An MDPI *Information* study (71 Saudi learners) reported the ChatGPT group outperformed controls at immediate and delayed tests, with a slight but significant decline from immediate to delayed — [MDPI](https://www.mdpi.com/2078-2489/17/9/812) [check: design described inconsistently as randomised or quasi-experimental].
- A longitudinal study of 297 Chinese university EFL learners compared rubric feedback, AI product feedback (after the draft) and AI process feedback (during composing). Process feedback was associated with better monitoring and revision and with stronger later **independent (no-AI) writing** — [PubMed 42984807](https://pubmed.ncbi.nlm.nih.gov/42984807) [check].
- Qadri, Naper & Zaman 2025 (Pakistan ESL): writing proficiency rose with AI assistants, but post-test autonomy fell. Learners deferred to AI phrasing rather than revising independently — [ResearchGate](https://www.researchgate.net/publication/392711021_Examining_the_Effect_of_Artificial_Intelligence_Writing_Assistants_on_English_as_a_Second_Language_Learners'_Proficiency_and_Autonomy) [check; autonomy is self-report].
- Kosmyna et al. (L1 essay writing) and Lira et al. (cover letters) are the best general-writing evidence (see Use case 3).

### Inferences
- Patterns: **write or translate it yourself first, then compare with the AI version and explain each difference** (Lira's personalised-example mechanism plus noticing). **Feedback during composing that asks for a revision, not a rewrite**. **AI as conversation partner that recasts errors** (untested here). For vocabulary, **AI-generated retrieval practice spaced over days**.

### Gaps
- No RCT found on machine-translation use and later L2 proficiency.
- A reported meta-analysis (recursive AI interaction g=0.89 vs editorial use g=0.41) could not be traced to a primary source [check].
- No RCT found on AI speaking partners with delayed outcomes.

## Use case 8 — Study planning, motivation and emotional support

### Takeaway
There is little rigorous evidence. Small pilot RCTs of chatbot procrastination interventions are mixed: in the one with a human comparator, only the human reduced procrastination. Heavy voluntary chatbot use is associated with more loneliness and dependence. AI tutoring in Eedi did not shift motivation or self-efficacy overall. A consistent risk is that AI inflates perceived learning and competence.

### Cited Findings
- **Fang et al. 2025, MIT Media Lab & OpenAI** (preprint, arXiv 2503.17473) [verified-arXiv]. Four-week RCT, n=981, crossing text, neutral-voice and engaging-voice modes with conversation types. In v2, assigned conditions had no significant main effects. Participants who *voluntarily* used the bot more showed worse loneliness, emotional dependence, problematic use and socialisation (correlational). Personal conversations were associated with lower dependence — [arXiv v2](https://arxiv.org/html/2503.17473v2); [MIT](https://www.media.mit.edu/publications/how-ai-and-human-behaviors-shape-psychosocial-effects-of-chatbot-use-a-longitudinal-controlled-study/). Critique: [Frontiers in Medicine 2025](https://www.frontiersin.org/journals/medicine/articles/10.3389/fmed.2025.1612838/pdf).
- **Lee et al. 2025, JMIR mHealth and uHealth** [verified-DOI 10.2196/53133]. Pilot RCT of a semi-generative chatbot in a to-do app for procrastination (30 days of self-observation, strategy-setting and reflection; 85 enrolled, 75 completed per PubMed). It reported a significant time × group effect on procrastination during the use period — [PubMed](https://pubmed.ncbi.nlm.nih.gov/40208664/).
- **Hennemann et al. 2025** (SSRN preprint 5281283). Pilot RCT, n=62: three chat sessions with ChatGPT-4 vs a human agent. Procrastination fell for the human agent but not for ChatGPT-4 — [SSRN](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5281283) [check].
- A 2026 RCT (n=86, 8-day chatbot procrastination intervention) found narrative perspective did not change overall engagement but altered engagement trajectories and motivational experience — [PubMed 42308911](https://pubmed.ncbi.nlm.nih.gov/42308911/) [check].
- Eedi/LearnLM Oct 2026: across the survey sample, neither AI nor expert tutoring shifted attitudes to mistakes, maths self-efficacy or motivation vs remediation. Tutoring narrowed the gender gap in reactions to mistakes by 0.32–0.35 points. Mandatory chat after every error may feel like a "signal of failure" to some students — [Google PDF](https://services.google.com/fh/files/misc/learnlm_oct26.pdf).
- Illusion of learning:
  - LLM access raised perceived learning without raising actual learning (Lehmann) — [arXiv](https://arxiv.org/html/2409.09047v2).
  - Strugglers left with an illusion of competence (Prather) — [arXiv](https://arxiv.org/abs/2405.17739).
  - Students preferred LLM support but learned less (Kreijkes) — [MSR](https://www.microsoft.com/en-us/research/?p=1143413).
  - Lead-and-Reveal improved calibration (Kazemitabaar 2025) — [arXiv](https://arxiv.org/html/2410.08922v1).
- Fan et al. 2024: AI support changed self-regulated learning processes (metacognitive laziness) — [BJET](https://doi.org/10.1111/bjet.13544) [details check]. Darvishi 2024: self-monitoring checklists partly substituted for AI when it was removed — [PsyPost](https://psypost.org/students-tend-to-rely-on-ai-rather-than-learn-from-it-study-finds).

### Inferences
- Patterns: **the student drafts the plan, the AI critiques it** (preserves self-regulation). **Calibration prompts**: predict your score, then test without AI, then compare. **Brief, opt-in emotional support that redirects to people and services**, with the coach monitoring heavy affective use. **Hints offered after an error rather than imposed** (Eedi friction finding).

### Gaps
- No RCT found of AI study-planning assistants on exam outcomes or on self-regulated learning skill measured after AI removal.

## Learning-mode products (ChatGPT Study Mode, Claude learning mode, Gemini Guided Learning / LearnLM): what has been evaluated?

### Takeaway
All three vendors ship "don't just give the answer" modes. Only Google's LearnLM / Gemini line has outcome RCTs: Eedi UK (exploratory and expanded) and Sierra Leone. No outcome RCT of ChatGPT Study Mode or Claude's learning modes was found as of Nov 2026.

### Cited Findings
- Claude learning mode launched 2 Apr 2025 with Claude for Education, inside Projects. It asks how the student would approach a problem, uses Socratic questioning and highlights principles. No outcome evaluation was reported — [Anthropic](https://www.anthropic.com/news/introducing-claude-for-education) [verified-pub]. Learning modes were later extended to all Claude users and to Claude Code (Learning / Explanatory output styles) — [Tom's Guide](https://www.tomsguide.com/ai/claudes-new-learning-modes-take-on-chatgpts-study-mode-heres-what-they-do) [check dates].
- ChatGPT Study Mode launched 29 Jul 2025. It is described as guided questioning with calibrated hints instead of full answers, and is available on all plans. OpenAI's page could not be fetched (403); no outcome RCT found — [TechCrunch](https://techcrunch.com/2025/08/06/google-takes-on-chatgpts-study-mode-with-new-guided-learning-tool-in-gemini/); [Glasp comparison](https://glasp.co/articles/ai-study-modes-compared) [check].
- Gemini Guided Learning launched Aug 2025, adding visuals, videos and quizzes — [TechCrunch](https://techcrunch.com/2025/08/06/google-takes-on-chatgpts-study-mode-with-new-guided-learning-tool-in-gemini/).
- **LearnLM Team, "LearnLM: Improving Gemini for Learning"** (tech report, arXiv 2412.16429, v3 Aug 2025) [verified-arXiv]. Frames pedagogy as "pedagogical instruction following". Expert raters role-playing learners preferred LearnLM over GPT-4o by ~31%, Claude 3.5 Sonnet by ~11% and Gemini 1.5 Pro by ~13% — [arXiv](https://arxiv.org/abs/2412.16429v3). These are rater preferences, not learning outcomes.
- **"Teaching with Gemini: Measuring the impact of Guided Learning on student mathematics progress in Sierra Leone"** (LearnLM Team, Google & Fab AI, May 2026). Pre-registered RCT with 1,763 junior secondary students in 48 classrooms over 8 weeks; teachers were asked to use Gemini in half of weekly lessons (12 h). ITT +0.258 SD (p=0.029); TOT +0.380 SD for the 69% reaching 12 h — [Stanford SCALE repository](https://scale.stanford.edu/ai/repository/teaching-gemini-measuring-impact-guided-learning-student-mathematics-progress-sierra) [check: full report not read; control condition and outcome test not described on that page].
- Eedi UK RCTs: see the cross-cutting section — [Google PDF](https://services.google.com/fh/files/misc/learnlm_oct26.pdf); [arXiv 2512.23633](https://arxiv.org/abs/2512.23633v1).
- Usage context: Anthropic's April 2025 education report analysed 574,740 student conversations. CS was 38.6% of conversations. Direct problem-solving and direct output creation were major interaction types, and "Creating" (39.8%) and "Analyzing" (30.2%) dominated the Bloom's levels — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude) [verified-pub].
- Anthropic's coding RCT authors recommend learning modes (Claude Code Learning / Explanatory, ChatGPT Study Mode) but did not test them — [Anthropic](https://www.anthropic.com/research/AI-assistance-coding-skills).

### Inferences
- Product "study modes" implement the guardrail principle that worked in Bastani's GPT Tutor and Eedi. But students can switch them off, and Kumar shows guidance style matters. Evaluations are vendor-run, so independent replication is needed.

### Gaps
- No independent or vendor RCT found for ChatGPT Study Mode or Claude learning or Explanatory modes.
- The Sierra Leone report's control condition and test instrument were not verified.

## Learning-science background for the design patterns

### Takeaway
The patterns that protected learning in AI studies (attempt first, explain it yourself, compare with an expert version, retrieve before feedback, interleave, space) map onto well-replicated effects. AI changes *who does the generating*, which is exactly what these effects depend on.

### Cited Findings
- **Pretesting / prequestions**: Pan & Carpenter 2023, *Educational Psychology Review*, review of prequestioning and pretesting effects [verified-DOI 10.1007/s10648-023-09814-5]. Attempting questions *before* study, even with errors, improves later retention of the prequestioned material; benefits for non-prequestioned material are less consistent — [EPR](https://doi.org/10.1007/s10648-023-09814-5) [check exact moderator conclusions].
  - AI application: Akgun & Toker 2025 (preprint, arXiv 2504.10249) [verified-arXiv], "Struggle First, Prompt Later", report three experiments in which AI-assisted pretesting enhanced learning, especially for higher-order and complex exploratory tasks; the benefit was smaller for straightforward computational problems — [arXiv](https://arxiv.org/abs/2504.10249). Sample sizes and effect sizes are not in the abstract; one search summary cites 61 students (31/30) [check].
- **Generation effect**: Bertsch et al. 2007, *Memory & Cognition* meta-analysis [verified-DOI 10.3758/BF03193441] — [M&C](https://doi.org/10.3758/BF03193441). Mean effect ~d=0.40 from memory [check].
- **Self-explanation**: Bisra, Liu, Nesbit, Salimi & Winne 2018, *Educational Psychology Review* meta-analysis [verified-DOI 10.1007/s10648-018-9434-x] — [EPR](https://doi.org/10.1007/s10648-018-9434-x). Overall g≈0.55 from memory [check].
- **Worked examples and fading**: worked examples benefit novices and fade as expertise grows (expertise reversal). Key sources — Renkl & Atkinson 2003, *Educational Psychologist* 38(1); Kalyuga et al. 2003 on the expertise reversal effect — were not retrieved this session [check all]. The Lira et al. AI-revised-own-letter result behaves like a personalised worked example — [arXiv](https://arxiv.org/abs/2502.02880).
- **Interleaving**: Brunmair & Richter 2019, *Psychological Bulletin* 145(11) [verified-DOI 10.1037/bul0000209]. The benefit depends on category similarity (greatest for similar, hard-to-discriminate categories) — [Psych Bull](https://doi.org/10.1037/bul0000209). Overall g≈0.42, varying by material (e.g., positive for paintings and maths, not for words), from memory [check].
- **Retrieval practice**: Adesope, Trevisan & Sundararajan 2017, *RER* [verified-DOI 10.3102/0034654316689306] — [RER](https://doi.org/10.3102/0034654316689306); Rowland 2014, *Psychological Bulletin* [verified-DOI 10.1037/a0037559] — [Psych Bull](https://doi.org/10.1037/a0037559). Overall g≈0.61 (Adesope) and g≈0.50 (Rowland), from memory [check].
- **Successive relearning** (retrieve to criterion, then relearn across spaced sessions): Rawson, Dunlosky & Sciartelli 2013, *Educational Psychology Review*, and later classroom work — not retrieved this session [check]. Eedi's returning-question mechanic is an AI-era instance; tutoring improved >7-day returning-question accuracy by ~12 pp vs hints — [Google PDF](https://services.google.com/fh/files/misc/learnlm_oct26.pdf).
- **Desirable difficulties / cognitive offloading**: Barcaui and Stadler frame their results this way — [PsyPost](https://www.psypost.org/chatgpt-acts-as-a-cognitive-crutch-that-weakens-memory-new-research-suggests/); [TUM](https://www.edtech.tum.de/?p=2430).

### Inferences
- Pattern-to-mechanism map:
  - **Attempt first / prequestions** → pretesting and generation.
  - **Explain-it-back / explain-the-bug** → self-explanation.
  - **Compare your version with AI's** → worked example after generation, plus noticing of the gap.
  - **AI quizzes you, you answer closed-book, missed items return later** → retrieval practice and successive relearning.
  - **Mixed AI-generated problem sets** → interleaving.
  - **Fade AI help as competence grows** → worked-example fading and expertise reversal. This matches Lehmann and Prather: the same AI help is safer for high-prior-knowledge learners.

### Gaps
- Numeric effect sizes for the classic meta-analyses come from memory, not re-read; worked-example, fading and successive-relearning sources are unverified.

## Design patterns: which preserved or improved learning in AI studies (cross-walk)

### Takeaway
Patterns with direct AI-study evidence of preserving or improving unassisted learning:
- hint-only or Socratic guardrails (Bastani, Eedi, Kestin)
- explanation-not-solution (Lehmann)
- conceptual-question-only or ask-why-after-code (Anthropic)
- Lead-and-Reveal and Trace-and-Predict friction (Kazemitabaar 2025)
- separate note-making (Kreijkes)
- AI-revised version of one's own work as an example (Lira)
- think-first (Kosmyna Brain→LLM; order studies, mixed)
- AI-assisted pretesting (Akgun & Toker, preprint)
- confidence highlighting for search (Spatharioti)
- human-in-the-loop AI (Tutor CoPilot, Eedi)
- disabling copy-paste (Lehmann, proof of concept)

Counter-evidence: coach-style hints harmed later unassisted RAT performance (Kumar), and conversational tutoring cut curriculum coverage (Eedi Oct 2026).

### Cited Findings
- Hint-only tutor removed the exam harm of answer-giving AI — [Hechinger](https://hechingerreport.org/kids-chatgpt-worse-on-tests/).
- Explanations +0.249 vs solutions −0.312 on understanding — [arXiv](https://arxiv.org/html/2409.09047v2).
- Conceptual inquiry ~65%, generation-then-comprehension ~86% vs delegation 24–39% — [Anthropic](https://www.anthropic.com/research/AI-assistance-coding-skills).
- Lead-and-Reveal improved calibration without extra load — [arXiv](https://arxiv.org/html/2410.08922v1).
- Notes (alone or with LLM) beat LLM-only at 3 days — [MSR](https://www.microsoft.com/en-us/research/?p=1143413).
- Viewing an AI revision of one's own letter improved no-AI writing — [arXiv](https://arxiv.org/abs/2502.02880).
- Coach-style guidance −10.6 points unassisted vs no AI — [arXiv](https://arxiv.org/html/2410.03703v2).
- Tutoring cost coverage: 99 vs 132 units — [Google PDF](https://services.google.com/fh/files/misc/learnlm_oct26.pdf).
- Confidence highlighting improved error detection — [MSR](https://www.microsoft.com/en-us/research/?p=1134789).

### Inferences
- The evidence most strongly supports a coach that: (1) asks for the student's attempt, plan or hypothesis first; (2) gives the smallest useful help (hint, explanation, pseudo-code) and withholds full solutions by default; (3) makes the student self-explain or trace; (4) offers an AI version only *after* the student's own version, framed as "compare and explain the differences"; (5) closes with a quick check without AI help, with spaced return of missed items; (6) adapts help to prior knowledge, with more structure for weaker students; (7) keeps hints short and opt-in so friction doesn't eat coverage or motivation.

### Gaps
- Most pattern evidence comes from short lab sessions with immediate tests. Kumar's coach-hint harm and Eedi's coverage trade-off show patterns need testing per task type.

## Citation verification ledger

### Takeaway
Most core citations were confirmed against Crossref DOI metadata or arXiv or publisher pages this session. Numeric details drawn from memory or secondary coverage are marked [check] inline.

### Cited Findings
- **Verified by Crossref DOI** (title, authors, venue matched):
  - Stadler et al. 2024 (10.1016/j.chb.2024.108386)
  - Darvishi et al. 2024 (10.1016/j.compedu.2023.104967)
  - Gerlich 2025 (10.3390/soc15010006)
  - Bastani et al. 2025 (10.1073/pnas.2422633122)
  - Kestin et al. 2025 (10.1038/s41598-025-97652-6)
  - Fan et al. 2024 (10.1111/bjet.13544)
  - Lee et al. 2025 (10.1145/3706598.3713778)
  - Pan & Carpenter 2023 (10.1007/s10648-023-09814-5)
  - Bisra et al. 2018 (10.1007/s10648-018-9434-x)
  - Adesope et al. 2017 (10.3102/0034654316689306)
  - Rowland 2014 (10.1037/a0037559)
  - Brunmair & Richter 2019 (10.1037/bul0000209)
  - Bertsch et al. 2007 (10.3758/BF03193441)
  - DeVerna et al. 2024 (10.1073/pnas.2322823121)
  - Melumad & Yun 2025 (10.1093/pnasnexus/pgaf316)
  - Pardos & Bhandari 2024 (10.1371/journal.pone.0304013)
  - Prather et al. 2024 (10.1145/3632620.3671116)
  - Kazemitabaar et al. 2023 (10.1145/3544548.3580919)
  - Kazemitabaar et al. CodeAid 2024 (10.1145/3613904.3642773)
  - Kazemitabaar et al. IUI 2025 (10.1145/3708359.3712104)
  - Kumar et al. CHI 2025 (10.1145/3706598.3714198)
  - Spatharioti et al. CHI 2025 (10.1145/3706598.3714082)
  - Doshi & Hauser 2024 (10.1126/sciadv.adn5290)
  - Kreijkes et al. 2026 (10.1016/j.compedu.2025.105514)
  - Lehmann et al. SSRN v1 (10.2139/ssrn.4941259)
  - Barcaui SSRN (10.2139/ssrn.5353041)
  - Lee et al. JMIR mHealth 2025 (10.2196/53133)
  - Henkel et al. 2024 (10.1007/978-3-031-64315-6_34)
  - Abdelhalim & Alsehibany 2025 LLT (10.64152/10125/73635)
  - Tutor CoPilot, Research Square preprint (10.21203/rs.3.rs-5363154/v1)
- **Verified on arXiv** (abstract or HTML page read, or listing matched):
  - Lehmann et al. 2409.09047
  - Kumar et al. 2410.03703
  - Lira et al. 2502.02880
  - Akgun & Toker 2504.10249
  - Kazemitabaar et al. 2410.08922 and 2302.07427
  - Prather et al. 2405.17739
  - Wang et al. 2410.03017
  - Fang et al. 2503.17473
  - Kosmyna et al. 2506.08872
  - LearnLM 2412.16429
  - Eedi exploratory RCT 2512.23633
  - Spatharioti et al. 2307.03744
  - Shen & Tamkin 2601.20245 (ID stated on Anthropic's page)
- **Verified on publisher or organisation page**: Anthropic coding-skills post (29 Jan 2026); Google/Eedi expanded RCT PDF (29 Oct 2026; full text read); World Bank WPS 11125 listing; Anthropic Claude for Education post (2 Apr 2025); Anthropic education report (Apr 2025).
- **Check**:
  - Sierra Leone Guided Learning report (May 2026; repository summary only)
  - Barcaui journal DOI (SSHO)
  - Hennemann et al. SSRN 5281283
  - 2026 narrative-framing RCT (PubMed 42308911)
  - MDPI *Information* vocabulary study
  - 297-learner L2 process-feedback study (PubMed 42984807)
  - Qadri et al. 2025
  - BMC Med Educ 2026 AI-MCQ RCT
  - arXiv 2507.05629 retrieval-practice study
  - JITE 2025 cohort study
  - Psychology Today think-first studies
  - Thinking Skills & Creativity crossover study (pii S187118712500207X)
  - KICSS 2025 (arXiv 2512.20628)
  - JMIR citation-fabrication study
  - Renkl & Atkinson 2003; Kalyuga et al. 2003; Rawson et al. 2013
  - Product launch dates for ChatGPT Study Mode and Claude learning modes (secondary sources)

### Inferences
- Wherever a number is flagged [check], the report writer should either drop it or confirm it from the primary paper before publishing.

### Gaps
- The arXiv API was rate-limited (HTTP 429), so some arXiv confirmations rely on arXiv pages surfaced in search rather than API metadata.
- OpenAI's study-mode page and the ScienceDirect page for Kreijkes returned HTTP 403.
