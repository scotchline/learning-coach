# What students use ChatGPT, Claude and similar AI assistants for (status: 17 Nov 2026)

Legend. **[verified]** means I read the number in the primary source: the publisher's page, or text I extracted from its PDF. **[check]** means the number comes only from secondary coverage, a search snippet, or a page I could not fully open. **[self-report]** means a survey of students. **[log]** means an analysis of conversation logs (it measures conversations or messages, not students). **[RCT]** means a randomised experiment. Charts in the HEPI 2026 PDF were read from extracted text, and values were matched to labels by series order. Each match was cross-checked against the figures HEPI states in its prose. Where a match could not be confirmed, the note says so.

## 1. Anthropic education data: "How university students use Claude" (Apr 2025) and later reports

### Takeaway
Anthropic analysed 574,740 student conversations on Claude.ai [log]. Students mostly use Claude to create or improve educational content (39.3%) and to get technical explanations or solutions (33.5%). Translation and proofreading are only 2.4%. Computer science is heavily over-represented (38.6% of conversations, against 5.4% of US degrees). The four interaction styles are roughly equal (23–29% each), and about 47% of conversations are "direct" (answer-seeking). There is no 2026 Anthropic student report. The later Anthropic data are an educators report (Aug 2025), an Economic Index note on coursework seasonality (Mar 2026), and general affective-use data.

### Cited Findings
- **Method [log, verified]:** Clio (Anthropic's automated privacy-preserving analysis tool) was run on about 1 million anonymised Claude.ai Free and Pro conversations from accounts with higher-education email addresses, over an 18-day window. After filtering for academic relevance, 574,740 conversations remained. Published 8 Apr 2025. — [Anthropic Education Report: How university students use Claude](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- **Four interaction styles [log, verified]:** Direct Problem Solving, Direct Output Creation, Collaborative Problem Solving and Collaborative Output Creation. Anthropic does not give exact shares per style, only that each falls "between 23% and 29% of conversations". About 47% of conversations were Direct (seeking answers or content with minimal engagement). — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- **Top use categories, share of student conversations [log, verified]:**

  | Category | Share |
  |---|---|
  | Creating and improving educational content | 39.3% |
  | Technical explanations or solutions for academic assignments | 33.5% |
  | Analysing and visualising data | 11.0% |
  | Supporting research design and tool development | 6.5% |
  | Creating technical diagrams | 3.2% |
  | Translating or proofreading | 2.4% |

  — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- **Bloom's taxonomy [log, verified]:** these are the cognitive operations Claude performed, not what students did. Creating 39.8%, Analysing 30.2%, Applying 10.9%, Understanding 10.0%, Remembering 1.8%. Anthropic itself cautions that applying Bloom's taxonomy to an AI is imperfect. — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- **Subjects, share of conversations vs share of US bachelor's degrees [log, verified]:**

  | Subject | Conversations | US degrees | |
  |---|---|---|---|
  | Computer Science | 38.6% | 5.4% | over-represented |
  | Natural Sciences & Mathematics | 15.2% | 9.2% | over-represented |
  | Business | 8.9% | 18.6% | under-represented |
  | Health Professions | 5.5% | 13.1% | under-represented |
  | Humanities | 6.4% | 12.5% | under-represented |

  The page also gives 36.8% for CS in its key-findings section, a small internal inconsistency. Education accounts for 3.8% of conversations, and 74.4% of those are output creation. — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- **Cheating share [log, verified]:** Anthropic gives no percentage. It says how many conversations involve cheating is "hard to answer" because the classroom context is unknown. Stated caveats: early adopters, Claude.ai is only one tool among several, the 18-day window misses seasonality, some "student" accounts may belong to staff, and the data show which tasks are delegated, not whether learning happened. — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- **Educators report, 27 Aug 2025 [log + small survey, verified]:** about 74,000 conversations from 22 May to 2 Jun 2025 (11 days), from higher-ed accounts with K-12 excluded, plus a survey of 22 Northeastern University faculty. Developing curricula 57%, academic research 13%, assessing student performance 7%. Grading conversations were 48.9% automation-heavy, and faculty rated grading as the task where AI was least effective. Student usage was explicitly not studied. — [Anthropic: How educators use Claude](https://www.anthropic.com/news/anthropic-education-report-how-educators-use-claude)
- **Economic Index, Mar 2026 [log, verified]:** coursework fell from 19% of Claude.ai conversations (Nov 2025) to 12% (5–12 Feb 2026), while personal use rose from 35% to 42%. Anthropic attributes part of the drop to winter breaks: the fall was 5 percentage points in countries where term was running. Samples were 1M conversations each from Claude.ai and the API. "12% of Tutor tasks" used Opus, against 34% of software-developer tasks. — [Anthropic Economic Index, March 2026](https://www.anthropic.com/research/economic-index-march-2026-report)
- **Affective use, Jun 2025 [log, verified, all users, not students]:** 2.9% of Claude.ai Free and Pro conversations are affective. Breakdown: interpersonal advice 2.26%, coaching 1.13%, psychotherapy or counselling 0.34%, companionship 0.31%, romantic or sexual roleplay under 0.1%. The base was about 4.5M conversations, yielding 131,484 affective ones. — [Anthropic: support, advice and companionship](https://www.anthropic.com/news/how-people-use-claude-for-support-advice-and-companionship)
- **AI Fluency Index, Feb 2026 [log, check: search snippet only]:** 9,830 multi-turn conversations from one week in Jan 2026; 85.7% showed iteration and refinement. Not student-specific. — [Anthropic AI Fluency Index](https://www.anthropic.com/research/AI-fluency-index)
- **Learning mode [check]:** Claude for Education's Learning mode asks questions instead of giving answers and points students to the underlying concepts. Coverage says students can switch back to normal mode, so it is a soft barrier. I found no published usage data for it. — [eWeek](https://www.eweek.com/news/anthropic-claude-learning-mode/); [Educators Technology, Feb 2026](https://www.educatorstechnology.com/2026/02/claude-for-education.html)

### Inferences
- Claude's student traffic is a technically skewed sample (CS, STEM). Its "translating or proofreading 2.4%" says little about the broad student population. Self-report surveys put writing improvement and translation far higher (see Q7).
- About 47% of conversations are Direct, and "Creating" dominates the Bloom's distribution. Together this suggests a large share of output delegation, which a learning coach can redirect toward collaborative modes.
- Coursework share is seasonal: it drops in holidays. Any log-based share depends heavily on the sampling window.

### Gaps
- I found no Anthropic report on student usage in 2026, and no usage statistics for Learning mode (adoption, retention, effect on learning).
- Exact per-style shares of the four interaction styles are not published; only the 23–29% range is.

## 2. OpenAI data on student usage (Feb 2025 report, NBER paper, Aug 2026 back-to-school report, study mode)

### Takeaway
OpenAI reports that over a third of US 18–24-year-olds use ChatGPT, and that about a quarter of their messages concern learning, tutoring or schoolwork [log]. In OpenAI's survey of 1,229 US students aged 18–24, the top uses were starting papers or projects (49%), summarising long texts (48%), brainstorming (45%), exploring topics (44%) and revising writing (44%) [self-report]. Across all ChatGPT users, "Tutoring or Teaching" is 10.2% of messages, and two thirds of writing requests modify text the user supplied [log]. OpenAI's Aug 2026 report adds up to 70M self-testing conversations per week, but it gives no data on how widely study mode is used.

### Cited Findings
- **"Building an AI-Ready Workforce", Feb 2025 [log + self-report, verified]:**
  - Over one-third of US 18–24-year-olds use ChatGPT. Among them, over one-quarter of messages are about "learning, tutoring, and school work", followed by writing help, miscellaneous questions, programming help and how-to advice. Usage data are from Jan 2025.
  - The survey covered 1,229 US college and graduate students aged 18–24, fielded by a third-party provider from 13 Dec 2024 to 2 Jan 2025. It excluded "AI rejectors".
  - Uses reported in the survey: starting papers or projects 49%, summarising long texts 48%, brainstorming creative projects 45%, exploring topics 44%, revising writing 44%.
  - Three in four students want AI training, but only one in four institutions provides it.

  — [OpenAI report PDF](https://cdn.openai.com/global-affairs/openai-edu-ai-ready-workforce.pdf)
- **NBER Working Paper 34255 "How People Use ChatGPT", Sep 2025 [log, verified, all consumer users, not students]:** about 1.1M sampled conversations from 15 May 2024 to 26 Jun 2025.
  - Practical Guidance is steady at about 29% of messages. Writing fell from 36% (Jul 2024) to 24% (Jul 2025). Seeking Information rose from 14% to 24%. Technical Help fell from 12% to about 5%.
  - "Tutoring or Teaching" is 10.2% of all messages and 36% of Practical Guidance.
  - About two-thirds of Writing messages modify the user's own text. The largest Writing sub-category is "Editing or Critiquing Provided Text", followed by personal writing, translation, and argument or summary generation.
  - Computer programming is 4.2% of messages. Relationships and personal reflection are 1.9%.

  — [NBER w34255](https://www.nber.org/papers/w34255)
- **"Learning never stops", 26 Aug 2026 [log, verified on the OpenAI page; PDF details verified through a text-extraction query]:**
  - Volumes: up to 70 million conversations per week are devoted to "testing what they know" (all ages). US classwork and homework prompts peak at more than 460 million messages per week during the school year and stay above 180 million per week in summer. People aged 18–21 were about 25% of users and 30% of messages in the homework analysis. — [OpenAI](https://openai.com/index/learning-never-stops/); [PDF](https://cdn.openai.com/pdf/learning-never-stops-back-to-school-report-august-2026.pdf)
  - Behaviour within self-testing conversations: answer-checking or sharing work for validation 63%, iterative learning 59%, showing one's own attempt 58%, requesting practice 51%, misconception checks 36%.
  - OpenAI's own caveat: the analysis "does not yet establish how often these interactions reflect productive practice versus quick-answer seeking or cognitive offloading."

  — [PDF](https://cdn.openai.com/pdf/learning-never-stops-back-to-school-report-august-2026.pdf)
- **RCTs cited by OpenAI [RCT, verified as cited in the Aug 2026 PDF; the underlying studies were not read]:**
  - About 1,000 high-school maths students in Turkey: unrestricted AI improved practice performance but "reduced later unaided test performance by 17%". A tutor set up with teacher-designed hints largely avoided that effect.
  - A Harvard physics AI tutor produced more than twice the median immediate learning gains of an active-learning classroom.

  — [OpenAI PDF](https://cdn.openai.com/pdf/learning-never-stops-back-to-school-report-august-2026.pdf)
- **Study mode [check]:** launched July 2025, optional, and students can switch back to normal ChatGPT. An OpenAI study from Mar 2026 reportedly found students using study mode scored about 15% higher than a no-AI control in microeconomics. In neuroscience the effect could not be distinguished from ordinary online resources. The OpenAI page returned HTTP 403. — [OpenAI: understanding AI and learning outcomes](https://openai.com/index/understanding-ai-and-learning-outcomes/); [Axios, 4 Mar 2026](https://www.axios.com/2026/03/04/openai-chatgpt-learning-students-cognitive); [eWeek on the launch](https://www.eweek.com/news/openai-chatgpt-study-mode/)

### Inferences
- In OpenAI's 2025 survey, "start a paper", "summarise" and "brainstorm" lead. These are front-loading and compression tasks, which is where a coach can insert a check like "show me your attempt first".
- Self-testing and "share my attempt for validation" behaviour exists at scale (63% and 58% inside self-testing conversations). That is evidence that students want feedback on their own work, not only answers.

### Gaps
- I found no published share of ChatGPT users or student conversations that use study mode.
- I could not read the full Mar 2026 OpenAI RCT write-up (sample size, institutions). The 15% figure is unverified.

## 3. HEPI / Kortext Student Generative AI Survey 2025 and 2026 (UK)

### Takeaway
UK undergraduate use is near-universal: 95% use AI in some way and 94% use it for assessed work (2026). The top assessment-related uses are explaining concepts (61%), summarising articles (49%), suggesting research ideas (40%) and structuring thoughts (39%). Among tool categories, enhancing or editing writing (Grammarly-type) is 37%. Fear of being accused of cheating (42%) and hallucinations (35%) are the main deterrents, both down from 2025. 20% say "I will learn more if I do not use AI". 49% say AI improved their student experience and 16% say it made it worse.

### Cited Findings
- **Method 2026 [self-report, verified]:** 1,054 full-time UK undergraduates, polled by Savanta in Dec 2025. Weighted by gender, institution type and year of study; margin of error about 3%. Published Mar 2026 as HEPI Report 199. — [HEPI 2026 PDF](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
- **Method 2025 [self-report, verified]:** 1,041 full-time undergraduates, polled by Savanta in Dec 2024. Published 26 Feb 2025. — [HEPI 2025](https://www.hepi.ac.uk/reports/student-generative-ai-survey-2025/)
- **Headline use [verified]:**
  - Any AI use: 66% (2024), 92% (2025), 95% (2026).
  - AI for assessments: 53% (2024), 88% on the 2025 page, 94% (2026). The 2026 report restates 2025 as 89%, a 1-point discrepancy between the two publications.

  — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf); [HEPI 2025](https://www.hepi.ac.uk/reports/student-generative-ai-survey-2025/)
- **AI use for any purpose by tool category, 2026 [verified, chart-read]:** this question asks "which of the following have you used AI for this academic year", for any purpose.

  | Tool category (HEPI's example) | 2026 |
  |---|---|
  | Generating text (ChatGPT) | 56% (down from 64% in 2025) |
  | Summarising, note-taking or quizzing textbooks (Kortext) | 38% |
  | Enhancing and editing writing (Grammarly) | 37% |
  | Translation or language support | 31% |
  | Generating images, video or audio | 22% |
  | Speech-to-text | 18% |
  | Writing code | 17% |
  | Data analysis | 17% |
  | Friendship, company, advice or tackling loneliness (new) | 15% |
  | Counselling or therapy provided solely by AI | 8% |
  | Counselling or therapy provided partly by AI | 4% |
  | None | 5% |

  The prose confirms 56%, 15%, 8% and 4%, and the ranking text confirms the order of 2nd and 3rd. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
- **"When preparing assessed work, which have you ever done?" [verified, chart-read; prose confirms 61, 49, 36, 13, 12, and 8% for 2025]:**

  | Use | 2026 | 2025 |
  |---|---|---|
  | Explain concepts | 61% | 58% |
  | Summarise a relevant article | 49% | 47% |
  | Suggest research ideas | 40% | 40% |
  | Structure my thoughts | 39% | 39% |
  | Search the internet (new) | 36% | – |
  | Generate text, then edit it before including | 25% | 25% |
  | Generate text and edit it with a digital tool | 17% | 18% |
  | Generate visual aids or media (new) | 13% | – |
  | Include AI text directly in assessed work | 12% | 8% (3% in 2024) |
  | None | 6% | 11% |

  — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
- **Acceptability of the same uses, 2026 [verified, chart-read]:** explain concepts 58%, summarise 50%, research ideas 46%, structure 43%, search 39%, generate-then-edit 23%, include directly 15%. No use reaches two-thirds acceptance. The average gap between use and acceptability shrank from 16 percentage points (2024) to 6 (2025) to 4 (2026). — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
- **Reasons that make students more likely to use AI, 2026 (2025 in brackets) [verified, chart-read; prose confirms 47, 45, 29 and the 51% for 2025]:** improve the quality of my work 47% (50%); save time 45% (51%); instant support 38% (40%); personalised support 31% (32%); broaden the learning content available 29% (new); improve my AI skills 29% (28%); support outside study hours 28% (29%); "I learn more if I use AI than if I don't" 19% (20%); institution encourages 14%; other students use it 14%; no interest 6%. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
- **Reasons that make students less likely to use AI, 2026 (2025 in brackets) [verified, chart-read; the 2025 values 53, 51 and 15 match the HEPI 2025 page]:** accused of cheating 42% (53%); false results or hallucinations 35% (51%); biased results 32% (37%); environmental impact 23% (15%); institution discourages or bans 21% (31%); **"I will learn more if I do not use AI" 20% (18%)**; unfair to others 19% (21%); data privacy 18% (23%); too expensive 17%; trained without authors' consent 15%; benefits oversold 14%; hard to access 12%; dislike edtech 8%; fully comfortable 5% (4%). — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf); [HEPI 2025](https://www.hepi.ac.uk/reports/student-generative-ai-survey-2025/)
- **Reliance on AI vs traditional sources, 2026 [verified]:** 34% lean towards traditional sources (13% mostly traditional, 21% more traditional), 29% use an equal balance, and 37% lean towards AI (29% more AI, **8% mostly AI and rarely traditional**). 53% use AI weekly to discover and understand traditional sources. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
- **Effect on the student experience, 2026 [verified]:** significantly better 9%, somewhat better 40% (49% better in total), no significant impact 35%, somewhat worse 13%, significantly worse 3% (16% worse in total). Free-text reasons:
  - Worse: changes to assessment, anxiety about false AI-detection accusations, unfairness, skill erosion ("It encourages you to think less"), isolation, jobs.
  - Better: understanding concepts, structuring, time saving, 24/7 help, asking "without judgement" and "as many times as I want", "a study buddy".

  — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
- **Loneliness and wellbeing, 2026 [verified]:** 21% feel less lonely because of AI, 20% more lonely, 59% no impact. 15% use AI for friendship, company, advice or tackling loneliness. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
- **Skills and institutions, 2026 [verified]:**
  - 68% say AI skills are essential to thrive, but only 48% say staff help them develop those skills for their careers. Arts and Humanities students feel least supported.
  - 36–37% agree their institution encourages AI use (28% in 2025).
  - 38% say their institution provides AI tools (23% in 2025, 9% in 2024); 50% say it should.
  - 65% say assessment has changed a lot because of AI (56% in 2025).
  - 51% had used generative AI at school before university (44% in 2025); 33% had not.

  — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
- **2025 extras [verified]:** 42% say staff are "well-equipped" to help with AI (18% in 2024); 36% had received AI skills training. — [HEPI 2025](https://www.hepi.ac.uk/reports/student-generative-ai-survey-2025/)
- **Case study in the 2026 report [small study described by HEPI, verified as reported]:** medical students working virtual patient cases with AI support and no feedback scored lowest but were the most confident. AI support combined with human feedback performed best. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)

### Inferences
- The UK ranking is stable across years: explain, then summarise, then ideas, then structure. Direct inclusion of AI text is small but rising (3% to 8% to 12%).
- The deterrent "I will learn more if I do not use AI" (20%) is a measurable form of the "fear of not learning". It is smaller than cheating or accuracy fears but rising.
- The medical case study shows that AI with feedback beats AI alone, and that AI alone breeds overconfidence. This is a strong design argument for a coach that gives feedback and checks understanding.

### Gaps
- I did not reliably extract the 2025 column of Figure 1 (tool categories) and the 2024 values from the chart text. Only figures confirmed in HEPI's prose are given for those years.
- HEPI's published breakdowns by gender and subject for the specific uses were not extracted (the XLSX was not read).

## 4. Digital Education Council (DEC) global surveys (2024, 2026, Latin America 2026)

### Takeaway
DEC 2024 had 3,839 students in 16 countries. Its top uses were searching for information (69%), checking grammar (42%), summarising (33%), paraphrasing (28%) and a first draft (24%) [check: secondary]. The DEC Global Survey 2026 reports 88% student use. Its top uses are searching for information (58%), brainstorming (54%), refining written work (49%), learning new concepts (45%), drafting (43%) and summarising (43%), with n=8,422 AI-using students [verified]. 66% of students worry that AI makes learning "too shallow". About 1 in 5 report dependence: harder to work without AI 21%, depend on AI for better work 20%, retain less 19%.

### Cited Findings
- **DEC 2024 method [verified]:** 3,839 responses, 16 countries, bachelor's, master's and doctoral students; published Aug 2024. The full report requires login. — [DEC Global AI Student Survey 2024](https://www.digitaleducationcouncil.com/post/digital-education-council-global-ai-student-survey-2024)
- **DEC 2024 uses and attitudes [check: secondary coverage]:**
  - 86% use AI in their studies; 54% weekly.
  - Uses: search for information 69%, grammar check 42%, summarise documents 33%, paraphrase 28%, first draft 24%.
  - Tools: ChatGPT 66%, Grammarly 25%, Copilot 25%.
  - 58% feel they lack AI knowledge and skills; 48% feel unprepared for an AI-enabled workforce; 80% say their university's AI integration falls short of their expectations.

  — [Campus Technology, 28 Aug 2024](https://campustechnology.com/articles/2024/08/28/survey-86-of-students-already-use-ai-in-their-studies)
- **DEC Global Survey 2026, method [verified]:** 45,398 responses (27,284 students, 18,114 faculty) across 35 countries, in regions APAC, EMEA, US & Canada and Latin America. The report says it draws on the 2024 student survey, the 2025 faculty survey and the 2026 Latin America survey. The use and impact questions report n=8,422 (students answering "yes" to using AI). It is therefore unclear how much of the 27,284 belongs to the 2026 wave itself. I did not find fieldwork dates. — [DEC Global Survey 2026 PDF](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
- **DEC 2026 adoption [verified]:** 88% of students use AI in their learning globally. Latin America 92%, EMEA 85%, APAC 78%, US & Canada 65%. — [DEC 2026 PDF](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
- **DEC 2026 top 6 student uses [verified, n=8,422, select all that apply]:** searching for information 58%, brainstorming for ideas 54%, refining written work 49%, learning new concepts 45%, drafting work 43%, summarising documents 43%. — [DEC 2026 PDF](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
- **DEC 2026 perceived impact on learning [verified, n=8,422]:**
  - Benefits: "I spend less time on repetitive tasks and focus more on thinking through ideas" 61%; attempting more challenging work 31%.
  - Dependence: "harder to work through problems without AI" 21%; "I depend on AI to produce better work" 20%; "I notice I retain less because I rely on AI" 19%; no real change 15%.
  - "AI could make learning too shallow and discourage critical thinking and creativity": 66% agree (40% agree, 26% strongly), rising to 81% in US & Canada. 73% of faculty think students use AI at the expense of developing their own skills.

  — [DEC 2026 PDF](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
- **DEC 2026 overall influence on the study experience [verified, n=8,422]:** game-changing 13%, very helpful 32%, somewhat helpful 43%. "Mostly negative" and "no noticeable change" are about 5–6% each; which label carries 5% and which 6% is ambiguous in the extracted chart text. — [DEC 2026 PDF](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
- **DEC 2026 integration, guidance, skills wanted and worries [verified]:**
  - Integration: AI is built into many courses for 15%, a few for 42–43%, none for 43%. Among students who have met it in courses: transformational 5%, enhances understanding 28%, somewhat helpful 42%, mostly novel with little learning benefit 24%.
  - Guidance: only 29% think their instructors are well-equipped to guide them on AI (17% in US & Canada).
  - Skills students most want: critically evaluate and fact-check AI output 51%; know when and when not to use AI 45%.
  - Worries: 60% worry about classmates' unfair misuse; 41% worry AI will reduce job opportunities.
  - "Disappointed if AI were banned": 51% agree globally; 43% in US & Canada strongly disagree.

  — [DEC 2026 PDF](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
- **DEC Latin America 2026 [verified on DEC's news page; full report is members-only]:** 92% use AI, 67% daily or weekly, ChatGPT 88% among frequent users. 65% worry that AI makes learning "too shallow". 56% are concerned about privacy, and 56% about fairness when AI evaluates their work. 50% support teachers using AI to give feedback on assignments. — [DEC LatAm news](https://www.digitaleducationcouncil.com/post/ai-adoption-is-nearly-universal-among-students-but-confidence-is-not)

### Inferences
- From 2024 to 2026, "grammar check" (42%) became "refining written work" (49%), still in the top 3. Brainstorming rose to #2 (54%). Searching stays #1 in both waves.
- The "retain less" (19%) and "harder without AI" (21%) items give a self-reported over-reliance baseline of about 1 in 5 AI-using students.

### Gaps
- DEC 2026 fieldwork dates and a European or DACH country breakdown were not found in the extracted text (only EMEA aggregates).
- The DEC 2024 percentages could not be verified in the primary report, which requires login.

## 5. Germany, Switzerland, Austria

### Takeaway
German data are strong and recent:
- **von Garrel & Mayer (h_da), Dec 2024–Jan 2025:** 4,910 students, 91.6% use AI. The top use is explaining concepts: 66.7% of all students, 73.2% of users. Then text analysis or creation (51.7%), translation (48.9%), research (46.2%), problem solving (44.8%) and exam prep (37.1%). ChatGPT free 81.5%, DeepL 44.8%, Claude 1.9%.
- **CHE, WS 2024/25 (23,288 students) and WS 2025/26 (28,584):** research and overview leads, then brainstorming, then tutor or learning partner. Daily use roughly doubled from 24.9% to 46.5% (subject mixes differ). About 70% want clear ethics and data-protection guidelines.

Swiss data for 2025 exist only for French-speaking Switzerland (Fribourg/HES-SO). Austria appears only inside the CHE samples (6 and 8 Austrian institutions); I found no stand-alone Austrian student data.

### Cited Findings
- **von Garrel & Mayer 2025, method [self-report, verified]:** online survey from 2 Dec 2024 to 10 Jan 2025. A self-selection sample recruited through contact persons at 395 of 428 German HEIs; 4,910 students plus 626 lecturers. The 2023 wave had N=6,311 students. The authors state the sample is not representative. DOI 10.48444/h_docs-pub-533. — [h_da report PDF](https://opus4.kobv.de/opus4-h-da/frontdoor/deliver/index/docId/533/file/gpt-dokumentation-final-jvg.pdf)
- **von Garrel 2025, adoption [verified]:** 91.6% use AI tools for their studies (63.2% in 2023). Very often 26.2% (9.5%), often 24.3% (22.3%), occasionally 19.1% (3.0%), never 8.4% (36.8%). By field: engineering 95.5%, medicine and health 93.6%, law, economics and social sciences 90.7%, humanities 87.5%, art 79.2%. — [h_da report](https://opus4.kobv.de/opus4-h-da/frontdoor/deliver/index/docId/533/file/gpt-dokumentation-final-jvg.pdf)
- **von Garrel 2025, tools [verified]:** ChatGPT free 81.5%, ChatGPT paid 17.4%, DeepL 44.8%, DALL-E 6.7%, Perplexity 4.3%, Gemini 4.1%, Midjourney 3.2%, Claude 1.9%. Microsoft Copilot is inconsistent within the report: the prose says 1.2%, the table says 399 respondents or 11.2%. — [h_da report](https://opus4.kobv.de/opus4-h-da/frontdoor/deliver/index/docId/533/file/gpt-dokumentation-final-jvg.pdf)
- **von Garrel 2025, uses ("Im Rahmen des Studiums nutze ich KI für…"), share of all students and share of AI users, 2023 in brackets [verified, Table 15]:**

  | Use | All students 2025 (2023) | AI users 2025 (2023) |
  |---|---|---|
  | Clarifying comprehension questions, explaining subject concepts | 66.7% (35.6%) | 73.2% (56.5%) |
  | Text analysis, processing and creation | 51.7% (24.8%) | 56.8% (39.3%) |
  | Translation | 48.9% (26.6%) | 53.8% (42.2%) |
  | Research and literature study | 46.2% (28.6%) | 50.8% (45.4%) |
  | Problem solving, decision making | 44.8% (22.1%) | 49.2% (35.1%) |
  | Exam preparation | 37.1% (12.8%) | 40.8% (20.3%) |
  | Programming and simulation | 25.1% (9.4%) | 27.6% (15.0%) |
  | Concept development, design | 24.0% (11.5%) | 26.3% |
  | Language processing | 22.3% (10.6%) | 24.5% |
  | Data analysis, visualisation, modelling | 18.1% (5.5%) | 19.9% |

  In engineering, exam prep is 47.2% and programming 55.3%. — [h_da report](https://opus4.kobv.de/opus4-h-da/frontdoor/deliver/index/docId/533/file/gpt-dokumentation-final-jvg.pdf)
- **CHE DatenCHECK, WS 2024/25 [self-report, verified]:**
  - Sample: 23,288 students at 171 HEIs, 6 of them Austrian, surveyed as part of the CHE Hochschulranking. Subjects: engineering, architecture, psychology, educational science, German studies and Romance studies.
  - Frequency: daily about a quarter, weekly 40% (65% regular), monthly 17.5%, never 6%.
  - Regular (weekly or daily) uses: research or overview 45.9%, brainstorming 36%, tutor or learning partner 31.4%, general study information about 4% (lowest).
  - Subject-specific figures: translation 55.5% in Romance studies; text generation 30.2% in mechatronics and 11.9% in German studies; coding 44.6% in mechatronics. Text correction (spelling, grammar) was the most frequent write-in under "other", with no figure given.
  - Expectations: clear ethics and data-protection guidelines 68.6%; more AI learning offerings 50.1%; allow AI in exams 35.6% agree vs 44.3% disagree. Satisfaction with AI-competence offerings 2.7 of 5 stars.

  — [CHE DatenCHECK WS 2024/25](https://hochschuldaten.che.de/kuenstliche-intelligenz-im-studium-die-sicht-von-studierenden-im-wintersemester-2024-25/); [Forschung & Lehre, 16 Jun 2025](https://www.forschung-und-lehre.de/lehre/zwei-drittel-der-studierenden-nutzen-ki-regelmaessig-7138)
- **CHE DatenCHECK 9/2026, WS 2025/26 [self-report, verified]:**
  - Sample: 28,584 students at 202 HEIs, 8 of them Austrian. Subjects: business, economics, business informatics, business psychology, industrial engineering, law and social work.
  - Frequency: daily 46.5%, weekly 34.5% (81% regular), monthly 9.9%, never 2.4%.
  - Regular uses: research or overview 68%, brainstorming 60%, tutor or learning partner 50%. The tutor share is 71.6% in business informatics, 24.4% in social work and 18.9% in law. Coding is 60.7% in business informatics. Text generation in law is 14.8%.
  - Expectations: clear ethics and data-protection guidelines 70%; more AI learning offerings about 58%; allow AI in exams 46% agree vs 31% disagree. Wish for AI-supported, individually tailored learning 59% agree (49% in WS 24/25). Satisfaction 3.3 stars.
  - CHE warns that the subject mix differs between waves, so the two are not directly comparable.

  — [CHE DatenCHECK WS 2025/26](https://hochschuldaten.che.de/kuenstliche-intelligenz-im-studium-die-sicht-von-studierenden-im-wintersemester-2025-26/)
- **University of Fribourg and HES-SO, spring 2025, French-speaking Switzerland [self-report, verified on the Unifr news page]:**
  - Sample: about 800 students and 362 lecturers.
  - Use: about 75% of students use AI daily or several times a week; ChatGPT leads, then Copilot.
  - Behaviour: 66% compare AI output with their own ideas; 56% use AI to deepen understanding; only 8% adopt AI-generated text directly, in whole or part.
  - Biggest worries: academic integrity and losing their own thinking ability (no percentages given).
  - Wishes: 76% want more information and clear rules on AI in exams and theses; 65% want free AI tools from the university.

  — [Unifr, 18 Dec 2025](https://www.unifr.ch/news/de/33969/ki-tools-sind-an-hochschulen-nicht-mehr-wegzudenken)
- **ETH Zurich survey, reported Jan 2024 [self-report, check: secondary only]:** 4,800 respondents. 80.5% had experienced problems with ChatGPT, such as wrong maths, hallucinations and inconsistent answers. 29.7% see AI as legitimate in assessments; 37.3% say it depends on the lecturer; 11.2% call it cheating. Uses mentioned without figures: writer's block, translation, correcting texts, improving phrasing, summarising teaching materials, a "better Google". — [Netzwoche, 29 Jan 2024](https://www.netzwoche.ch/news/2024-01-29/studierende-nutzen-ki-vertrauen-ihr-aber-nicht)
- **UZH 2023 [check: snippet only]:** 97% of 926 respondents had experience with AI tools. — [UZH DSI position paper](https://dsi.uzh.ch/dam/jcr:0d74a3a1-74b1-42fb-bbd4-4326841b7a73/dsi-strategy-lab-23-positionspapier-de.pdf)
- **Austria [check]:** the BMBWF project report "Von KI lernen, mit KI lehren" (Oct 2024) includes a student survey, but the PDF exceeded the fetch limit and was not read. — [BMBWF PDF](https://www.bmfwf.gv.at/dam/jcr:6998d7bc-2987-45cc-9a46-0caf6b88f947/KI-Publikation_2024-10_bf.pdf)

### Inferences
- In German samples, translation (48.9%, DeepL 44.8%) and exam prep (37.1%, tripled since 2023) are far more prominent than in UK or US surveys. A coach for DACH students should treat translation and language support, and exam preparation, as core use cases.
- "Explain concepts" is the top use in both the German (von Garrel) and UK (HEPI) data. The CHE "tutor or learning partner" item ranges from 31% to 50% and varies strongly by subject: high in business informatics and engineering, low in law and social work.
- Claude has low reach among German students (1.9%). They mostly come with ChatGPT habits.

### Gaps
- I found no 2025–2026 student survey from German-speaking Switzerland (ETH, UZH, ZHAW, FHNW or swissuniversities).
- No stand-alone Austrian results were extracted.
- von Garrel's 2025 report gives no figures on worries, over-reliance or perceived learning benefit in the sections I read. Neither CHE wave asked about worries.

## 6. Other large surveys: Tyton, EDUCAUSE, Pew (teens), Chegg, Inside Higher Ed, JIM (German teens)

### Takeaway
- **US university students:** in the Inside Higher Ed flash survey (Jul 2025, N=1,047), the top uses are brainstorming (55%), asking questions "like a tutor" (50%) and studying for exams or quizzes (46%). 55% say the effect on their learning is mixed.
- **Global:** in Chegg 2025 (11,706 undergraduates, 15 countries), 56% primarily use AI to understand concepts and 53% fear inaccurate information [check].
- **Secondary school:** in Pew (US teens, fall 2025), 54% use chatbots for schoolwork, 10% for all or most of it, 35% to edit their writing and 12% for emotional support. In JIM 2025 (German teens aged 12–19), 84% have used ChatGPT, and about three quarters use AI for homework or learning [74%: check].

### Cited Findings
- **Inside Higher Ed Student Voice flash survey [self-report, verified]:** 1,047 students at 166 two- and four-year US institutions, July 2025, with Generation Lab; margin of error ±3.
  - 85% used AI for coursework in the past year.
  - Uses: brainstorming 55%, asking questions like a tutor 50%, studying for exams or quizzes 46%, completing assignments 25%, writing full essays 19%.
  - Effect on learning and critical thinking (among users): positive 27%, mixed 55%, negative 7%. A negative effect on critical thinking is reported by 12% of essay-writers vs 6% of students who use AI to study.
  - More than a third of men vs about one in five women say AI improves their thinking.
  - Wishes: 97% want institutions to respond to integrity threats; 53% want education on ethical AI use; only 21% want AI-detection software; 18% want to limit technology in class.

  — [Inside Higher Ed](https://www.insidehighered.com/index%2Ephp/node/189916)
- **Pew, "How Teens Use and View AI", 24 Feb 2026 [self-report, verified]:** 1,458 US teens aged 13–17 and their parents, surveyed 25 Sep to 9 Oct 2025 via the Ipsos KnowledgePanel; margin of error ±3.3.
  - Chatbot uses: searching for information 57%, schoolwork help 54%, fun 47%, summarising articles, books or videos about 4 in 10, creating images or videos about 4 in 10, casual conversation 16%, emotional support or advice 12%.
  - Share of schoolwork done with chatbots: all or most 10%, some 21%, a little 23%, none 45%.
  - Specific school uses: research and solving maths problems each about 4 in 10 or more; editing something they wrote 35%.
  - Helpfulness: about 25% say very or extremely helpful, 25% somewhat.
  - Cheating: 59% say AI cheating happens at least somewhat often at their school; among teens who use chatbots for schoolwork, 76% say it happens at least sometimes.
  - Of teens expecting a negative personal impact, 34% cite over-reliance or loss of critical thinking or creativity. The denominator was summarised and should be confirmed on the page.

  — [Pew Research Center](https://www.pewresearch.org/internet/2026/02/24/how-teens-use-and-view-ai/)
- **Pew, 15 Jan 2025 [self-report, verified]:** 1,391 US teens, 18 Sep to 10 Oct 2024. 26% used ChatGPT for schoolwork (13% in 2023), 31% in grades 11–12. Acceptable to use ChatGPT for researching new topics 54%, for solving maths problems 29%, for writing essays 18% (42% say essays are not acceptable). — [Pew short read](https://www.pewresearch.org/short-reads/2025/01/15/about-a-quarter-of-us-teens-have-used-chatgpt-for-schoolwork-double-the-share-in-2023/)
- **Chegg Global Student Survey 2025 [self-report, check: press-release coverage; Business Wire returned HTTP 403]:** 11,706 undergraduates aged 18–21 in 15 countries, interviewed by Yonder Consulting from 1 to 23 Oct 2024.
  - 80% have used generative AI for their studies; 29% turn to it first when stuck.
  - 56% of users primarily use it to understand concepts; 50% report better understanding of complex concepts (44% in 2023).
  - Top concern: incorrect or inaccurate information, 53% (47% in 2023).
  - Wishes: 50% want education-specific tools; 69% want their institution to provide AI tools.

  — [Business Wire release](https://www.businesswire.com/news/home/20250128439546/en/Chegg-Global-Student-Survey-2025-80-of-Undergraduates-Worldwide-Have-Used-GenAI-to-Support-their-Studies-But-Accuracy-a-Top-Concern); [Chegg.org](https://chegg.org/global-student-survey-2025)
- **Tyton Partners, Time for Class 2025 [self-report, verified for the headline only]:** over 3,300 students, instructors and administrators at more than 900 US institutions; published 11 Jun 2025. Weekly generative AI use: 42% of students, 30% of instructors. The page gives no breakdown of uses. — [Tyton 2025](https://tytonpartners.com/time-for-class-2025/)
  - [check] D2L's summary says student use of ChatGPT for academic support dropped from 30% (2024) to 17% (2025), and that students still prefer human help when struggling with concepts. — [D2L via search](https://www.d2l.com/resources/assets/rethinking-higher-education/students-and-chatgpt/)
- **Tyton Time for Class 2026 [verified on D2L's blog]:** daily AI use by administrators 43% vs students 32%, the first time administrators lead. Students' top challenge is workload anxiety (40%). The blog gives no data on what students use AI for. — [D2L blog](https://www.d2l.com/en-eu/blog/five-findings-from-the-2026-time-for-class-report-that-surprised-us/)
- **EDUCAUSE 2025 Students and Technology Report [self-report, check: report is members-only, figures from secondary summaries]:** nearly 40,000 undergraduates at more than 160 institutions; published Apr 2025.
  - 43% had not used generative AI for courses.
  - Among users: brainstorming 33%, refining ideas 24%, organising work 24%.
  - Only 51% had received guidance on AI use; 55% see generative AI as important for their careers, but 20% had received training.
  - The most common reason for non-use was instructors prohibiting it.

  — [EDUCAUSE Library](https://library.educause.edu/resources/2025/4/2025-educause-students-and-technology-report); [eCampus News summary](https://www.ecampusnews.com/student-wellbeing/2025/05/07/6-aspects-of-todays-student-experience-in-higher-ed)
- **JIM-Studie 2025, Germany, ages 12–19 [self-report]:**
  - [verified] 1,200 teens, interviewed 2 Jun to 12 Jul 2025 (50% by phone, 50% online), representative. ChatGPT ever used: 84% (57% in 2024). — [mpfs press release](https://mpfs.de/app/uploads/2025/11/Vorab-PM_JIM-Studie-2025.pdf)
  - [check] 74% use AI for homework or learning (65% in 2024): Gymnasium 79%, Haupt- or Realschule 64%. — [GEW](https://www.gew.de/aktuelles/detailseite/ki-wird-vor-allem-fuer-hausaufgaben-genutzt); [ZDF](https://www.zdfheute.de/panorama/ki-chatgpt-jugendliche-smartphones-jim-studie-100.html)
- **JIM-Studie 2026 [check: dpa-AFX coverage dated 13 Nov 2026; mpfs primary not read]:** 1,200 teens.
  - Reasons for using AI: information 76%, homework or learning 75%, understanding how things work 59%, use in class 47%, fun 42%, planning 30%, personal health questions 26%, discussing problems and worries 15%.
  - 63% use AI regularly.

  — [Der Aktionär (dpa-AFX)](https://www.deraktionaer.de/nachricht/alslernhilfeoderfreundinwiejugendlichekinutzen-565763.html)

### Inferences
- In secondary school, schoolwork help is mainstream but heavy delegation is a minority: 10% of US teens do all or most of their schoolwork with AI. Teens find research acceptable (54%) but essays not (18%). The incoming university cohort arrives with these norms; in HEPI, 51% of UK undergraduates had used AI at school.
- About 15% of German teens (JIM 2026) and 12% of US teens (Pew) use AI to discuss worries or for emotional support. This is in line with the 15% of UK undergraduates using it for company or advice.

### Gaps
- The primary reports for EDUCAUSE 2025 (members-only), Chegg 2025 (HTTP 403) and Tyton 2025/2026 (full PDFs) were not read, so their use breakdowns stay [check].
- I found no Swiss secondary-school equivalent (for example the JAMES study) with 2025–2026 AI-for-school figures.

## 7. How big is each use case? Cross-source sizes and a proposed top-10 ranking

### Takeaway
In self-report surveys of university students, the top uses are consistent:
1. Explain or understand concepts: 45–73%.
2. Search or research for an overview: 46–69%.
3. Brainstorming and ideas: 36–60%.
4. Summarising: 33–49%.
5. Improving one's own writing (grammar, proofreading, phrasing): 35–49%.

After these come translation (31–49%, highest in DACH), drafting text (24–43%; 12% paste AI text directly), structuring thoughts (39%), exam prep and practice (37–46%), and problem solving or homework solutions (about 40–45%). Coding (17–25% overall, 45–61% in informatics and engineering) and data analysis (17–18%) are niche overall. Emotional support or company is about 12–15%. Study planning is rarely measured and appears small for university students (about 4% for "study information" in CHE). Log analyses show something different: on Claude, technical and content creation dominate and proofreading is only 2.4%; on ChatGPT, editing user-supplied text is the largest writing sub-task.

### Cited Findings
- **Explain a concept or tutor-style Q&A:**
  - HEPI 2026: 61% (#1). — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - von Garrel 2025: 66.7% of all students, 73.2% of users (#1). — [h_da](https://opus4.kobv.de/opus4-h-da/frontdoor/deliver/index/docId/533/file/gpt-dokumentation-final-jvg.pdf)
  - Chegg 2025: 56% primary use [check]. — [Business Wire](https://www.businesswire.com/news/home/20250128439546/en/Chegg-Global-Student-Survey-2025-80-of-Undergraduates-Worldwide-Have-Used-GenAI-to-Support-their-Studies-But-Accuracy-a-Top-Concern)
  - Inside Higher Ed: "like a tutor" 50%. — [IHE](https://www.insidehighered.com/index%2Ephp/node/189916)
  - DEC 2026: "learning new concepts" 45%. — [DEC 2026](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
  - CHE: tutor or learning partner 31.4% (WS 24/25) and 50% (WS 25/26). — [CHE 24/25](https://hochschuldaten.che.de/kuenstliche-intelligenz-im-studium-die-sicht-von-studierenden-im-wintersemester-2024-25/); [CHE 25/26](https://hochschuldaten.che.de/kuenstliche-intelligenz-im-studium-die-sicht-von-studierenden-im-wintersemester-2025-26/)
  - [log] ChatGPT, all users: tutoring or teaching 10.2% of messages. — [NBER](https://www.nber.org/papers/w34255)
  - [log] Claude students: technical explanations or solutions 33.5%. — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- **Search, research or overview:**
  - DEC 2024: 69% (#1) [check]. — [Campus Technology](https://campustechnology.com/articles/2024/08/28/survey-86-of-students-already-use-ai-in-their-studies)
  - DEC 2026: 58% (#1). — [DEC 2026](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
  - CHE: 45.9% and 68% (#1 in both waves). — [CHE](https://hochschuldaten.che.de/kuenstliche-intelligenz-im-studium-die-sicht-von-studierenden-im-wintersemester-2025-26/)
  - von Garrel: research and literature 46.2%. — [h_da](https://opus4.kobv.de/opus4-h-da/frontdoor/deliver/index/docId/533/file/gpt-dokumentation-final-jvg.pdf)
  - HEPI 2026: search the internet 36%; suggest research ideas 40%. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - US teens: searching for information 57%. — [Pew](https://www.pewresearch.org/internet/2026/02/24/how-teens-use-and-view-ai/)
- **Brainstorming:**
  - Inside Higher Ed: 55% (#1). — [IHE](https://www.insidehighered.com/index%2Ephp/node/189916)
  - DEC 2026: 54% (#2). — [DEC 2026](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
  - CHE: 36% and 60% (#2). — [CHE](https://hochschuldaten.che.de/kuenstliche-intelligenz-im-studium-die-sicht-von-studierenden-im-wintersemester-2025-26/)
  - OpenAI survey: brainstorming 45%, starting papers or projects 49% (#1). — [OpenAI](https://cdn.openai.com/global-affairs/openai-edu-ai-ready-workforce.pdf)
  - EDUCAUSE: 33% (#1 among users) [check]. — [eCampus News](https://www.ecampusnews.com/student-wellbeing/2025/05/07/6-aspects-of-todays-student-experience-in-higher-ed)
- **Summarising readings:**
  - HEPI 2026: summarise an article 49% (#2); textbook summarising, note-taking or quizzing tools 38%. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - OpenAI survey: 48%. — [OpenAI](https://cdn.openai.com/global-affairs/openai-edu-ai-ready-workforce.pdf)
  - DEC 2026: 43%; DEC 2024: 33% [check]. — [DEC 2026](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
  - US teens: about 40%. — [Pew](https://www.pewresearch.org/internet/2026/02/24/how-teens-use-and-view-ai/)
- **Grammar, proofreading, improving one's own writing or tone:**
  - DEC 2026: refining written work 49% (#3). — [DEC 2026](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
  - OpenAI survey: revising writing 44%. — [OpenAI](https://cdn.openai.com/global-affairs/openai-edu-ai-ready-workforce.pdf)
  - DEC 2024: grammar check 42% (#2); paraphrasing 28% [check]. — [Campus Technology](https://campustechnology.com/articles/2024/08/28/survey-86-of-students-already-use-ai-in-their-studies)
  - HEPI 2026: enhancing and editing writing (Grammarly-type tools) 37% (#3 tool category). — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - US teens: editing something they wrote 35%. — [Pew](https://www.pewresearch.org/internet/2026/02/24/how-teens-use-and-view-ai/)
  - von Garrel: text analysis, processing and creation 51.7%, which mixes editing and generating. — [h_da](https://opus4.kobv.de/opus4-h-da/frontdoor/deliver/index/docId/533/file/gpt-dokumentation-final-jvg.pdf)
  - CHE: text correction (spelling, grammar) was the most frequent "other" write-in. — [CHE 24/25](https://hochschuldaten.che.de/kuenstliche-intelligenz-im-studium-die-sicht-von-studierenden-im-wintersemester-2024-25/)
  - [log] ChatGPT: about two-thirds of Writing messages modify user text, and editing or critiquing provided text is the largest Writing sub-category. — [NBER](https://www.nber.org/papers/w34255)
  - [log] Claude students: translating or proofreading only 2.4%. — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- **Translation:**
  - von Garrel: 48.9% of all students, 53.8% of users; DeepL used by 44.8%. — [h_da](https://opus4.kobv.de/opus4-h-da/frontdoor/deliver/index/docId/533/file/gpt-dokumentation-final-jvg.pdf)
  - CHE: 55.5% in Romance studies. — [CHE 24/25](https://hochschuldaten.che.de/kuenstliche-intelligenz-im-studium-die-sicht-von-studierenden-im-wintersemester-2024-25/)
  - HEPI 2026: translation or language support 31%. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
- **Drafting or generating text:**
  - HEPI 2026: generating text 56% (tool category, any purpose); generate then edit for assessed work 25%; include AI text directly 12%. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - DEC 2026: drafting 43%; DEC 2024: first draft 24% [check]. — [DEC 2026](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
  - Inside Higher Ed: full essays 19%, completing assignments 25%. — [IHE](https://www.insidehighered.com/index%2Ephp/node/189916)
  - Fribourg/HES-SO: 8% adopt AI text directly. — [Unifr](https://www.unifr.ch/news/de/33969/ki-tools-sind-an-hochschulen-nicht-mehr-wegzudenken)
  - [log] Claude: creating and improving educational content 39.3%. — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- **Structuring thoughts and organising:** HEPI 2026 39% [verified] — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf); EDUCAUSE organising work 24% [check] — [eCampus News](https://www.ecampusnews.com/student-wellbeing/2025/05/07/6-aspects-of-todays-student-experience-in-higher-ed)
- **Exam prep, practice questions, self-testing:**
  - Inside Higher Ed: studying for exams or quizzes 46%. — [IHE](https://www.insidehighered.com/index%2Ephp/node/189916)
  - von Garrel: 37.1% (12.8% in 2023), 47.2% in engineering. — [h_da](https://opus4.kobv.de/opus4-h-da/frontdoor/deliver/index/docId/533/file/gpt-dokumentation-final-jvg.pdf)
  - [log] OpenAI: up to 70M self-testing conversations per week. — [OpenAI](https://openai.com/index/learning-never-stops/)
- **Problem solving and homework solutions:**
  - von Garrel: problem solving and decision making 44.8%. — [h_da](https://opus4.kobv.de/opus4-h-da/frontdoor/deliver/index/docId/533/file/gpt-dokumentation-final-jvg.pdf)
  - US teens: solving maths problems about 4 in 10. — [Pew](https://www.pewresearch.org/internet/2026/02/24/how-teens-use-and-view-ai/)
  - [log] Claude: Direct Problem Solving is one of four styles at 23–29% each. — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- **Coding:**
  - von Garrel: 25.1% (55.3% in engineering). — [h_da](https://opus4.kobv.de/opus4-h-da/frontdoor/deliver/index/docId/533/file/gpt-dokumentation-final-jvg.pdf)
  - HEPI 2026: 17%. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - CHE: 44.6% in mechatronics, 60.7% in business informatics. — [CHE](https://hochschuldaten.che.de/kuenstliche-intelligenz-im-studium-die-sicht-von-studierenden-im-wintersemester-2025-26/)
  - [log] Claude: CS is 38.6% of student conversations. — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- **Data analysis:** von Garrel 18.1% — [h_da](https://opus4.kobv.de/opus4-h-da/frontdoor/deliver/index/docId/533/file/gpt-dokumentation-final-jvg.pdf); HEPI 17% — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf); [log] Claude 11.0% — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- **Study planning and organisation:**
  - CHE: "general study information (organisation, course selection)" about 4%, the lowest use. — [Forschung & Lehre](https://www.forschung-und-lehre.de/lehre/zwei-drittel-der-studierenden-nutzen-ki-regelmaessig-7138)
  - JIM 2026 (teens): "planning" 30% [check]. — [Der Aktionär](https://www.deraktionaer.de/nachricht/alslernhilfeoderfreundinwiejugendlichekinutzen-565763.html)
- **Emotional support, company, advice:**
  - HEPI 2026: 15%; counselling solely by AI 8%. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - US teens: 12%. — [Pew](https://www.pewresearch.org/internet/2026/02/24/how-teens-use-and-view-ai/)
  - German teens: discussing problems and worries 15% [check]. — [Der Aktionär](https://www.deraktionaer.de/nachricht/alslernhilfeoderfreundinwiejugendlichekinutzen-565763.html)
  - [log] Claude, all users: 2.9% affective. — [Anthropic](https://www.anthropic.com/news/how-people-use-claude-for-support-advice-and-companionship)

### Inferences
- **Proposed top 10 for university students** (self-report, weighted towards recent DACH and UK data; ranges are % of students):

  | # | Use case | Range |
  |---|---|---|
  | 1 | Explain or understand concepts (tutor Q&A) | 45–73% |
  | 2 | Research, search, topic overview | 46–69% |
  | 3 | Brainstorming, getting started | 36–60% |
  | 4 | Summarising readings | 33–49% |
  | 5 | Improving own writing (grammar, proofreading, flow, phrasing) | 35–49% |
  | 6 | Translation and language support (DACH: about 49%) | 31–49% |
  | 7 | Problem solving and homework solutions | about 40–45% |
  | 8 | Exam prep and practice questions | 37–46% |
  | 9 | Structuring thoughts and outlining | 24–39% |
  | 10 | Drafting text | 24–43%; 12% include it directly |

  Next come coding (17–25% overall, much higher in STEM), data analysis (about 17%) and emotional support (about 12–15%). Positions 6 to 10 are close together, and their order differs by country and subject.
- **Grammar and proofreading is large:** a top-5 use in self-reports (35–49%), and the biggest single writing sub-task in ChatGPT logs. Claude's 2.4% reflects its CS-heavy, technical student base, not the student population. For German-speaking students working in a second language (English papers) or a third (French, Italian), language polishing and translation are likely even more central. This is an inference supported by the von Garrel and CHE translation figures.
- **Self-report and logs measure different things.** Surveys give the share of students who ever or regularly do a task. Logs give the share of conversations or messages, and they are dominated by heavy users and by the platform's user base. Logs should not be ranked directly against survey percentages.

### Gaps
- No survey I found asks directly about "tone" or "style feedback", or about "feedback on my draft" as a separate item. The closest items are "refining written work", "revising writing", "editing" and "share my work for validation".
- Study planning or time management is almost never a survey item for university students.

## 8. Does AI help or hurt learning? Self-reported over-reliance, worries and wants

### Takeaway
Students report net benefit with ambivalence:
- 49% say AI made their student experience better and 16% worse (HEPI 2026).
- Among US users, 27% say the effect on their learning is positive, 55% mixed and 7% negative (Inside Higher Ed).
- About 1 in 5 AI-using students self-report dependence: 21% harder to work without AI, 19% retain less (DEC 2026).
- Two thirds worry AI makes learning "too shallow" (DEC 2026: 66%).

The top worries are being accused of cheating, accuracy or hallucinations, shallow learning or skill erosion, peer unfairness, and unclear rules. Students want clear rules, instant and personalised support, fact-checking skills, and tools provided by their institution. Experimental evidence shows unguided AI can hurt later unaided performance, while guided or feedback-rich setups help.

### Cited Findings
- **Helps or hurts [self-report]:**
  - HEPI 2026: better 49%, no impact 35%, worse 16% [verified]. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - Inside Higher Ed: positive 27%, mixed 55%, negative 7% [verified]. — [IHE](https://www.insidehighered.com/index%2Ephp/node/189916)
  - DEC 2026: game-changing 13%, very helpful 32%, somewhat helpful 43%; 61% say AI frees them to focus on thinking through ideas [verified]. — [DEC 2026](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
  - Chegg 2025: 50% report better understanding of complex concepts [check]. — [Business Wire](https://www.businesswire.com/news/home/20250128439546/en/Chegg-Global-Student-Survey-2025-80-of-Undergraduates-Worldwide-Have-Used-GenAI-to-Support-their-Studies-But-Accuracy-a-Top-Concern)
  - HEPI 2026: only 19% say "I learn more if I use AI than if I don't" [verified]. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
- **Self-reported over-reliance [self-report, verified]:**
  - DEC 2026: harder to work through problems without AI 21%; depend on AI for better work 20%; retain less 19%. — [DEC 2026](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
  - HEPI 2026: 8% "mostly use generative AI and rarely use traditional sources"; free-text comments such as "I'm not using my brain at all" and "My grades have dropped because AI is mitigating my ability to think critically". — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - US teens: of those expecting a negative personal impact, 34% cite over-reliance or loss of critical thinking. — [Pew](https://www.pewresearch.org/internet/2026/02/24/how-teens-use-and-view-ai/)
- **Fear of not learning, shallow learning:**
  - DEC 2026: 66% (81% in US & Canada) [verified]. — [DEC 2026](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
  - DEC Latin America 2026: 65% [verified]. — [DEC LatAm](https://www.digitaleducationcouncil.com/post/ai-adoption-is-nearly-universal-among-students-but-confidence-is-not)
  - HEPI 2026: 20% say "I will learn more if I do not use AI" is a reason to use AI less (18% in 2025) [verified]. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - Fribourg/HES-SO: losing one's own thinking ability is among the top two worries [verified, no %]. — [Unifr](https://www.unifr.ch/news/de/33969/ki-tools-sind-an-hochschulen-nicht-mehr-wegzudenken)
- **Accuracy:**
  - HEPI 2026: hallucinations 35% (51% in 2025) and bias 32% (37%) as deterrents [verified]. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - Chegg 2025: inaccurate information is the top concern, 53% [check]. — [Business Wire](https://www.businesswire.com/news/home/20250128439546/en/Chegg-Global-Student-Survey-2025-80-of-Undergraduates-Worldwide-Have-Used-GenAI-to-Support-their-Studies-But-Accuracy-a-Top-Concern)
  - ETH: 80.5% had experienced problems with ChatGPT [check]. — [Netzwoche](https://www.netzwoche.ch/news/2024-01-29/studierende-nutzen-ki-vertrauen-ihr-aber-nicht)
  - DEC 2026: the AI skill students most want is to "critically evaluate and fact-check AI-generated output", 51% [verified]. — [DEC 2026](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
- **Integrity and cheating anxiety:**
  - HEPI 2026: being accused of cheating is the #1 deterrent, 42% (53% in 2025); free text describes fear of false AI-detection flags [verified]. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - DEC 2026: 60% worry about peer misuse [verified]. — [DEC 2026](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf)
  - Pew teens: 59% say AI cheating happens at least somewhat often at their school [verified]. — [Pew](https://www.pewresearch.org/internet/2026/02/24/how-teens-use-and-view-ai/)
- **Wants:**
  - Clear rules: Fribourg/HES-SO 76% want clear rules for exams and theses — [Unifr](https://www.unifr.ch/news/de/33969/ki-tools-sind-an-hochschulen-nicht-mehr-wegzudenken); CHE 68.6–70% want clear ethics and data-protection guidelines — [CHE](https://hochschuldaten.che.de/kuenstliche-intelligenz-im-studium-die-sicht-von-studierenden-im-wintersemester-2025-26/); DEC 2026 says 57% find AI guidance for assessments inadequate [check: secondary] — [EdTech Innovation Hub](https://www.edtechinnovationhub.com/news/q6zw9wco2mttajdbd1jyeonjnpiovu)
  - Instant support 38% and personalised support 31% (HEPI 2026); free text praises asking "without judgement" [verified]. — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
  - AI-supported, individually tailored learning: 59% agree (CHE WS 25/26) [verified]. — [CHE](https://hochschuldaten.che.de/kuenstliche-intelligenz-im-studium-die-sicht-von-studierenden-im-wintersemester-2025-26/)
  - Feedback: 50% support teachers using AI for feedback (DEC Latin America) — [DEC LatAm](https://www.digitaleducationcouncil.com/post/ai-adoption-is-nearly-universal-among-students-but-confidence-is-not); in OpenAI self-testing conversations, 63% check answers or share work for validation and 51% request practice [log] — [OpenAI PDF](https://cdn.openai.com/pdf/learning-never-stops-back-to-school-report-august-2026.pdf)
  - Skills: knowing when and when not to use AI 45% (DEC 2026) — [DEC 2026](https://actualidad.udla.cl/wp-content/uploads/sites/15/2026/06/6a3b9fb2f4e0472d0160d771_Digital-Education-Council-AI-in-Higher-Education-Global-Survey.pdf); 68% say AI skills are essential but only 48% say staff help them (HEPI 2026) — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)
- **Experimental evidence [RCT, cited by OpenAI, verified as cited]:** unrestricted AI cut later unaided maths test scores by 17% in Turkish high schools, and a hint-based tutor largely avoided the effect. A designed AI physics tutor more than doubled immediate gains. — [OpenAI PDF](https://cdn.openai.com/pdf/learning-never-stops-back-to-school-report-august-2026.pdf)
- **Medical case study:** AI without feedback produced the lowest skill and the highest confidence (HEPI 2026 case study). — [HEPI 2026](https://www.hepi.ac.uk/wp-content/uploads/2026/03/HEPI-Report-199-Gen-AI-Survey-2026.pdf)

### Inferences
These are implications for the learning-coach prompt; they are not findings.
- Lead with the explain, research, brainstorm and writing-feedback use cases.
- Make "attempt first, then feedback" the default. This targets the dependence signals (about 20%) and matches students' own validation behaviour.
- Add fact-checking and source verification by default, because accuracy is the #2 worry and the #1 skill students want.
- Help students work within assessment rules and document their AI use, because cheating-accusation anxiety is the #1 deterrent.
- Support translation and second-language writing for DACH students.
- Handle the 12–15% emotional-support demand with care and signposting.
- Students' own framing ("helpful but makes me think less") suggests they would welcome a coach that explicitly protects their learning.

### Gaps
- No large survey measures how students want AI feedback (for example Socratic questioning vs direct correction), and I found no DACH data on over-reliance or worries with percentages.
- Self-reported benefit has not been validated against outcomes in these surveys. The RCT evidence is limited and context-specific (school maths, physics, one OpenAI study-mode trial with unverified details).
