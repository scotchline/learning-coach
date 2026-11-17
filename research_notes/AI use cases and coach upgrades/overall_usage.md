# What people use ChatGPT, Claude.ai and Claude Code for: large-scale usage evidence (as of 17 Nov 2026)

Tags: **[verified]** means I read the number in the primary source: report text, or a figure rendered from the primary PDF. **[check]** means it comes from a search snippet or secondary coverage only. "Fig." means the value was read off a chart in the primary PDF. Pre-2025 sources are flagged **(older context)**.

## Q1. OpenAI / NBER "How People Use ChatGPT" (Chatterji, Cunningham, Deming, Hitzig, Ong, Shan, Wadman; NBER WP 34255, Sept 2025), plus any 2026 OpenAI follow-up

### Takeaway
Consumer ChatGPT is mostly an advisor and search substitute, not a coding tool. Practical Guidance (~28-29%), Seeking Information (~21-24%) and Writing (~24-28%) together make up about 77-78% of messages. Tutoring or Teaching alone is 10.2% of all messages. Editing or critiquing the user's own text is 10.6%. Programming is only 4.2%. About two-thirds of Writing modifies text the user supplied rather than creating new text. I found no 2026 re-run of the full taxonomy. OpenAI's 2026 releases are topic-specific (health, learning), and I could verify them only through secondary coverage.

### Cited Findings
**Sample and method**
- Primary classified sample: about 1.1 million conversations, one random user message per conversation, May 15, 2024 to June 26, 2025. Consumer plans only (Free, Plus, Pro); Business/Teams, Enterprise and Education are excluded. Also excluded: users who opted out of training, users who self-report as under 18, logged-out users, deleted conversations, and banned or deactivated accounts. Weights are rescaled to daily total message volume. [verified] — [NBER w34255 PDF, §3](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)
- Second sample: about 130,000 users and 1.58 million messages (May 2024 to July 2025), used for demographics and occupation through a secure data clean room. [verified] — [NBER w34255](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)
- Classification: each taxonomy is an LLM prompt (work vs non-work; 24 topic categories rolled up to 7; Asking/Doing/Expressing; O*NET work activity), and no human reads any message. Validated against human labels on public WildChat messages. Asking/Doing/Expressing model-to-human-plurality agreement is Cohen's κ = 0.56 (human-human κ = 0.47). The work classifier's model-plurality κ is 0.83. [verified] — [NBER w34255 App. B](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)
- Scale: by July 2025, 700 million weekly active users sent 18 billion messages a week, about 10% of the world's adults. [verified] — [NBER w34255](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)

**Coarse topic shares**
- Pooled May 2024 to June 2025 (Fig. 9): Practical Guidance 28.3%, Writing 28.1%, Seeking Information 21.3%, Technical Help 7.5%, Multimedia 6.0%, Other/Unknown 4.6%, Self-Expression 4.3%. [verified, Fig.] — [NBER w34255 Fig. 9, p.16](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)
- Trend from July 2024 to about July 2025:
  - Practical Guidance was "roughly 29%" and constant.
  - Writing fell from 36% to 24%.
  - Seeking Information rose from 14% to 24%.
  - Technical Help fell from 12% to "around 5%". The authors attribute part of this to coding moving to the API, code editors and agents such as Codex.
  - Multimedia rose from 2% to "just over 7%", spiking in April 2025 with image generation.
  - The top three together are "about 77%" in the body text and "nearly 80%" in the abstract.
  [verified] — [NBER w34255 §5.2](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)

**Granular shares (24 categories, % of all messages, pooled May 2024 to June 2025, Fig. 9)** [verified, Fig.] — [NBER w34255 Fig. 9](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)
- Practical Guidance:
  - Tutoring or Teaching 10.2%. This is 36% of Practical Guidance; definition: "Explaining concepts, teaching subjects, or helping the user understand educational material."
  - How-To Advice 8.5% (30% of Practical Guidance)
  - Health, Fitness, Beauty or Self-Care 5.7%
  - Creative Ideation 3.9%
- Writing:
  - Edit or Critique Provided Text 10.6%
  - Personal Writing or Communication 8.0%
  - Translation 4.5%
  - Argument or Summary Generation 3.6%
  - Write Fiction 1.4%
- Seeking Information: Specific Info 18.3%, Purchasable Products 2.1%, Cooking and Recipes 0.9%.
- Technical Help: Computer Programming 4.2%, Mathematical Calculation 3.0%, Data Analysis 0.4%.
- Multimedia: Create an Image 4.2%, Generate or Retrieve Other Media 1.1%, Analyze an Image 0.6%.
- Self-Expression: Greetings and Chitchat 2.0%, Relationships and Personal Reflection 1.9%, Games and Role Play 0.4%.
- Other/Unknown 4.1%; Asking About the Model 0.4%.

**Editing vs generating**
- Three Writing sub-categories modify user-provided text: Edit/Critique, Translation, and Argument/Summary. Together they are "two thirds of all Writing conversations." From Fig. 9 that is 10.6 + 4.5 + 3.6 = 18.7% of all messages, versus 9.4% for new text (Personal Writing 8.0% + Fiction 1.4%). [verified] — [NBER w34255 §5.2](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)

**Work vs non-work**
- Non-work share of daily messages rose from 53% (June 2024; 238M of 451M a day) to 73% (June 2025; 1,911M of 2,627M a day). Each figure is a 7-day average. Most of the shift happened within cohorts rather than from changes in who uses ChatGPT. [verified] — [NBER w34255 Table 1](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)
- Work-related messages only:
  - Writing is about 40% (July 2025) and 41.8% pooled (Fig. 11). The conclusion says 42%.
  - Practical Guidance is 24%.
  - Technical Help fell from 18% to "just over 10%".
  - Writing is more than half of work messages for management and business occupations.
  [verified] — [NBER w34255 §5.2, Fig. 11, Conclusion](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)

**Asking / Doing / Expressing**
- Pooled: Asking 48.9%, Doing 39.8%, Expressing 11.3% (Fig. 10; the text rounds to 49/40/11). [verified, Fig.]
- Trend: in July 2024 Asking and Doing were roughly even, with Expressing just under 8%. By late June 2025 the split was Asking 51.6%, Doing 34.6%, Expressing 13.8%. [verified]
- Work messages: Doing 55.8%, Asking 35.3%, Expressing 8.9%. Doing+Writing alone is 34.9% of all work messages. [verified, Fig. 11]
- Cross-tab, pooled, as % of all messages (Fig. 10). [verified, Fig.]
  - Practical Guidance = 19.7 Asking + 6.4 Doing + 2.2 Expressing
  - Writing = 3.9 Asking + 22.1 Doing + 2.1 Expressing
  - Seeking Information = 18.6 Asking + 1.9 Doing + 0.8 Expressing
  - Technical Help = 3.7 Asking + 3.2 Doing + 0.6 Expressing
- Asking messages are rated "Good" more often than Doing or Expressing, by both a satisfaction classifier and thumbs feedback. Self-Expression has the best good-to-bad ratio (more than 7). Multimedia (1.7) and Technical Help (2.7) are the lowest. [verified]
- All of the above — [NBER w34255 §5.3, §5.5](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)

**O*NET work activities (all messages, pooled)**
- Getting Information 19.3%; Interpreting the Meaning of Information for Others 13.1%; Documenting/Recording Information 12.8%; Providing Consultation and Advice 9.2%; Thinking Creatively 9.1%; Making Decisions and Solving Problems 8.5%; Working with Computers 4.9%. These seven sum to 76.9%. [verified] — [NBER w34255 §5.4](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)

**Demographics**
- Users with typically masculine first names fell from about 80% just after launch to 48% (June 2025).
- Nearly half of adult messages come from users under 26.
- Growth has been faster in low- and middle-income countries.
- [verified] — [NBER w34255](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)

**Internal inconsistencies in the paper**
- The conclusion says Expressing is "1%", not 11%. This is a typo; all figures show about 11%.
- The work-Writing share is given as 40% in the introduction and 42% in the conclusion.
- [verified] — [NBER w34255 Conclusion](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)

**2026 OpenAI follow-ups (topic-specific, not a re-run of the taxonomy)**
- "AI as a Healthcare Ally" (Jan 2026):
  - More than 5% of all ChatGPT messages worldwide concern healthcare.
  - More than 40 million people a day ask health questions (global; Axios corrected an earlier "Americans" framing).
  - About 1 in 4 of more than 800 million regular users sends a health prompt each week.
  - 7 in 10 health conversations happen outside clinic hours.
  - [check: the PDF was over 10 MB and I could not read it, so these come from coverage] — [OpenAI PDF](https://cdn.openai.com/pdf/2cb29276-68cd-4ec6-a5f4-c01c5e7a36e9/OpenAI-AI-as-a-Healthcare-Ally-Jan-2026.pdf); [Axios](https://axios.com/2026/01/05/chatgpt-openai-health-insurance-aca)
- "Learning never stops" (Aug 26, 2026):
  - Up to 70 million conversations a week are spent testing what people know.
  - US classwork and homework prompts peak above 460 million messages a week in the school year and stay above 180 million a week in summer.
  - No share of total messages is given in the coverage.
  - [check: OpenAI's page returned HTTP 403] — [OpenAI](https://openai.com/index/learning-never-stops/); [TUN coverage](https://www.tun.com/home/openai-report-460m-weekly-student-messages-sent-to-chatgpt/)
- "About a quarter of messages from US 18-24-year-olds relate to learning and schoolwork" (2025 OpenAI analysis). [check, secondary only] — [search summary of OpenAI education coverage](https://www.tun.com/home/openai-report-460m-weekly-student-messages-sent-to-chatgpt/)

### Inferences
- Pooled shares overweight 2024. By mid-2025 the ranking of coarse topics is Practical Guidance (~29%), then Seeking Information (~24%) tied with Writing (~24%). At the granular level, Specific Info is probably larger than its pooled 18.3% and Edit/Critique probably smaller than its pooled 10.6%.
- The health figure (>5%, Jan 2026) agrees with the NBER sub-category Health/Fitness/Beauty/Self-Care at 5.7%. That suggests the health share was stable through late 2025.
- For a coach prompt: about 10% of all messages are tutoring, but the "learning" behaviour is wider. How-To Advice (8.5%, defined to include "learn new skills"), Asking-type Technical Help, and part of Seeking Information are also learning-adjacent. Writing help is mostly feedback on the user's own draft rather than ghost-writing: 18.7% of all messages versus 9.4%.

### Gaps
- No granular (24-category) table for a single recent month in the paper; only pooled values and coarse time series.
- No OpenAI 2026 re-run of the full topic or Asking/Doing taxonomy found as of Nov 2026.
- The OpenAI blog summary and the "Learning never stops" page could not be fetched (HTTP 403), and the health PDF was too large to read.
- Figure 7's monthly coarse values are read from the text, not the chart.

## Q2. Anthropic Economic Index (Feb 2025, Mar 2025, Sep 2025, Jan 2026, Mar 2026, Jun 2026): occupational mix, automation vs augmentation, and the trend in the "learning" pattern

### Takeaway
Claude.ai is far more technical than ChatGPT. Computer and Mathematical tasks are 34-40% of conversations over 2025 to Feb 2026. Educational Instruction and Library is the clearest riser: about 9% (Jan 2025) to 15% (Nov 2025). Arts/Design/Media, which includes copyediting and fiction, is about 8-10%. Augmentation (task iteration, learning, validation) was 55% in Jan 2025. It dropped below automation in Aug 2025 (47% vs 49%), then recovered to 52-53% (Nov 2025 to Feb 2026). The learning pattern has stayed at roughly a fifth to a quarter of Claude.ai conversations: about 23%, then about 28% (Mar 2025), lower in Aug 2025, then 21-25% in Feb 2026. Claude.ai shifted toward personal use in 2026: 35% to 42% personal; coursework fell from 19% to 12%. Note: the latest Index report is June 2026 ("Cadences"). I found no Index report dated Sept to Nov 2026.

### Cited Findings
**Feb 2025 report (Handa et al., arXiv 2503.04761)**
- Data: Claude.ai Free and Pro conversations from Dec 2024 to Jan 2025, analysed with Clio (privacy-preserving), mapped to about 20,000 O*NET tasks. Conversations were filtered to those plausibly involving an occupational task. [verified] — [arXiv 2503.04761](https://arxiv.org/abs/2503.04761)
- Shares: Computer and Mathematical 37.2% of queries; Arts, Design, Entertainment, Sports and Media 10.3%. [verified] — [arXiv 2503.04761](https://arxiv.org/abs/2503.04761)
- Educational Instruction and Library 9.3% (V1). [verified] — [Anthropic Sep 2025 report](https://www.anthropic.com/research/anthropic-economic-index-september-2025-report)
- Augmentation 57% (task iteration, learning, validation) vs automation 43% (directive, feedback loop). Human reviewers judged 86% of task assignments acceptable and 90.7% of collaboration-pattern labels optimal. [verified] — [arXiv 2503.04761](https://arxiv.org/abs/2503.04761)
- Directive share in Jan 2025 was 27%. [verified] — [Anthropic Jan 2026 report PDF, p.9](https://www-cdn.anthropic.com/096d94c1a91c6480806d8f24b2344c7e2a4bc666.pdf)

**Mar 2025 report (Claude 3.7 Sonnet; 1 million Claude.ai Free and Pro conversations over 11 days after launch; published Mar 27, 2025)**
- Learning interactions rose from about 23% to about 28%. Augmentation was unchanged at 57%.
- Computer and Mathematical had the largest absolute rise (+3 points).
- Librarians have the most learning interactions (about 56%); copywriters and editors lead task iteration (about 58%).
- Method change: the occupational-relevance filter was dropped and only safety-flagged conversations were removed.
- [verified] — [Anthropic, Mar 2025](https://www.anthropic.com/news/anthropic-economic-index-insights-from-claude-sonnet-3-7)

**Sep 2025 report (data: 1 million Claude.ai Free and Pro conversations, Aug 4-11, 2025; plus 1 million first-party API transcripts, Aug 2025)**
- Claude.ai:
  - Computer and Mathematical 36%.
  - Educational Instruction and Library 9.3% to 12.4%.
  - Life/Physical/Social Science 6.3% to 7.2%.
  - Business and Financial about 6% to 3%; Management about 5% to 3%.
  - Creating new code 4.1% to 8.6%; debugging 16.1% to 13.3%; developing instructional materials 0.2% to 1.5%.
- Directive share rose from 27% to 39%, "mainly at the expense of task iteration and learning". This was the first time automation exceeded augmentation on Claude.ai.
- API:
  - 77% of transcripts are automation versus 12% augmentation.
  - 97% of API tasks are automation-dominant, versus 47% on Claude.ai.
  - API mix: Computer and Mathematical 44%; Education 3.6% (vs 12.3% on Claude.ai); Arts 5.2% (vs 8.2%).
- [verified] — [Anthropic Sep 2025](https://www.anthropic.com/research/anthropic-economic-index-september-2025-report)

**Jan 2026 "Economic primitives" (data: Nov 13-20, 2025; 1 million Claude.ai Free/Pro/Max conversations and 1 million API transcripts)**
- Claude.ai collaboration over time (Fig. 1.3):
  - Augmentation: 55% (Jan 2025), 55% (Mar 2025), 47% (Aug 2025), 52% (Nov 2025).
  - Automation: 41%, 42%, 49%, 45%.
  - The body text cites Jan 2025 as 56% augmentation and 41% automation.
- Directive share: 27%, then 39%, then 32%. Augmentation's Nov 2025 rebound was "driven mainly by... task iteration rather than... learning."
- API: automation 77% (Aug 2025) and 75% (Nov 2025); directive 64% on the API vs 32% on Claude.ai.
- [verified, Fig.] — [Jan 2026 PDF pp. 9-10](https://www-cdn.anthropic.com/096d94c1a91c6480806d8f24b2344c7e2a4bc666.pdf)
- Computer and Mathematical on Claude.ai: peak of 40% (Mar 2025) down to 34% (Nov 2025). API: 44% to 46%. [verified] — [Jan 2026 PDF p.7](https://www-cdn.anthropic.com/096d94c1a91c6480806d8f24b2344c7e2a4bc666.pdf)
- Educational Instruction and Library went from 9% (Jan 2025) to 15% (Nov 2025) and is now the second-largest Claude.ai category: "mostly... help with coursework and review, and the development of instructional materials." Chapter 2 gives 16%. [verified] — [Jan 2026 PDF p.8](https://www-cdn.anthropic.com/096d94c1a91c6480806d8f24b2344c7e2a4bc666.pdf); [Jan 2026 page](https://www.anthropic.com/research/anthropic-economic-index-january-2026-report)
- Approximate chart readings (Fig. 1.2), Claude.ai, Jan / Mar / Aug / Nov 2025:
  - Educational Instruction: about 9.3, 10.9, 12.4, 15.1.
  - Arts/Design/Media: about 10.3, 9.4, 8.2, 9.9. The Aug-Nov rise came from "writing tasks, primarily copyediting and the writing and refinement of fictional pieces."
  - Office/Admin: about 7.9, 6.9, 8.2, 7.9.
  - Life/Physical/Social Science: about 6.3, 6.8, 7.1, 5.5.
  - Business/Financial: about 5.9, 4.4, 3.0, 3.2.
  - Management: about 4.5, 3.1, 2.6, 3.2.
  - [verified, Fig., approximate] — [Jan 2026 PDF p.8](https://www-cdn.anthropic.com/096d94c1a91c6480806d8f24b2344c7e2a4bc666.pdf)
- Use case split, Claude.ai Nov 2025: 46% work, 19% coursework, 35% personal. API: 74% work. [verified] — [Jan 2026 page](https://www.anthropic.com/research/anthropic-economic-index-january-2026-report)
- Task success, as judged by Claude:
  - 67% on Claude.ai vs 49% on the API.
  - Personal-task clusters 78%; software development 61%.
  - About 70% for conversations below high-school level; 66% for college level.
  - [verified] — [Jan 2026 page](https://www.anthropic.com/research/anthropic-economic-index-january-2026-report)
- Top 10 O*NET tasks were 24% of Claude.ai usage. The single most common task is "modifying software to correct errors" at 6%. [verified] — [Jan 2026 PDF p.6](https://www-cdn.anthropic.com/096d94c1a91c6480806d8f24b2344c7e2a4bc666.pdf)

**Mar 2026 "Learning curves" (data: Feb 5-12, 2026; "1 million conversations from both" Claude.ai and the first-party API; published Mar 24, 2026)**
- Computer and Mathematical was 35% of Claude.ai conversations.
- Top 10 tasks fell from 24% to 19%. Partly this is coding moving to the API, where "Claude Code has grown to represent a large share of sampled traffic."
- Coursework fell from 19% to 12%, partly due to winter break. Personal use rose from 35% to 42%. Work was about 45-46%; the figure label is ambiguous.
- Management rose from 3% to 5%.
- Average task value fell from $49.3 to $47.9 an hour, "mostly due to an increase in simple factual questions (e.g., sports outcomes, weather)" and less coding.
- The sample period overlapped with Anthropic's Super Bowl ads, which brought many first-time users.
- [verified] — [Mar 2026 PDF pp. 5-8, 18](https://cdn.sanity.io/files/4zrzovbb/website/4053bf3440c0c85b8852052770c5b4cf882689c3.pdf)
- Claude.ai augmentation vs automation, Jan 2025 / Mar 2025 / Aug 2025 / Nov 2025 / Feb 2026: augmentation 55, 55, 47, 52, 53%; automation 41, 42, 49, 45, 44%. The rise "was driven by small bumps in validation and learning patterns." The API's automation share "decreased sharply". [verified, Fig.; the series mapping is mine, but it sums consistently to 96-97%] — [Mar 2026 PDF p.7](https://cdn.sanity.io/files/4zrzovbb/website/4053bf3440c0c85b8852052770c5b4cf882689c3.pdf)
- **Collaboration modes by user tenure, Feb 2026 (Table 2.1):** low-tenure users (under 6 months) vs high-tenure users. [verified] — [Mar 2026 PDF p.15](https://cdn.sanity.io/files/4zrzovbb/website/4053bf3440c0c85b8852052770c5b4cf882689c3.pdf)

| Measure | Low tenure | High tenure |
|---|---|---|
| Directive | 38.1% | 29.4% |
| Feedback loop | 11.7% | 12.1% |
| Task iteration | 24.5% | 28.2% |
| Validation | 4.4% | 5.6% |
| Learning | 21.3% | 24.7% |
| Work | 41.6% | 48.9% |
| Personal | 44.3% | 40.3% |
| Coursework | 14.1% | 10.8% |
| Task success | 66.7% | 73.1% |

- High-tenure users have a success advantage of about 5 points raw, about 3 with task fixed effects, and about 4 with full controls. The authors flag survivorship bias and cohort effects. [verified] — [Mar 2026 PDF pp. 17-18](https://cdn.sanity.io/files/4zrzovbb/website/4053bf3440c0c85b8852052770c5b4cf882689c3.pdf)

**Jun 2026 "Cadences" (data: chat and Cowork conversations, Apr 10 to Jun 10, 2026; survey of about 9,700 respondents linked to usage, which the authors say is not representative)**
- The report classifies outputs rather than occupations:
  - Explanations 17%, documents and reports 15%, guidance 11%.
  - Personal use rises from about 35% of conversations on weekdays to just under 50% on weekends.
  - Work conversations: 20% produce documents or reports.
  - Coursework conversations: 21% documents or reports, 20% explanations.
  - Personal conversations: 25% explanations, 22% recommendations, 6% documents.
- No collaboration-mode percentages are published in this report.
- Survey: 68% say they learn more with AI; 57% say AI made their skills more valuable; about 10% think losing their job in the next year is likely.
- [verified] — [Anthropic Jun 2026](https://www.anthropic.com/research/economic-index-june-2026-report)

### Inferences
- **Learning-pattern trajectory on Claude.ai:**
  - About 23% (Dec 2024 to Jan 2025)
  - About 28% (Feb to Mar 2025)
  - Down by Aug 2025, as directive rose to 39% at the expense of learning and iteration
  - Not the driver of the Nov 2025 rebound
  - Back up slightly by Feb 2026, to about 21-25% (between the low- and high-tenure values)
  - Overall it is roughly flat at a fifth to a quarter of conversations, with a peak in early 2025.
- "Learning" in Anthropic's scheme means users asking for information or explanations. That overlaps OpenAI's Asking more than its narrower Tutoring or Teaching category. So Claude's 21-28% "learning" and ChatGPT's 10.2% "tutoring" measure different things and should not be compared directly.
- Claude.ai's education share (9% to 15%, then coursework falling to 12% in Feb 2026) is seasonal and depends on the user mix. The Feb 2026 drop coincides with winter break and an influx of casual users.
- Anthropic's categories are O*NET occupational groups, not use-case groups. "Arts, Design, Media" is the nearest proxy for writing and editing. "Educational Instruction" is the nearest proxy for tutoring. They are not a writing share or a tutoring share as such.

### Gaps
- Exact five-mode shares for each report are published only in figures or appendices I did not fully read. Missing are Jan 2025 feedback loop, task iteration and validation, the V3 learning share, and the aggregate Feb 2026 learning share.
- No Claude.ai occupational shares by category for Feb 2026 in the main text; they are only in the appendix.
- I could not find any Index report after Jun 2026 as of Nov 17, 2026. One third-party page mentions an "August 2026" publication that I could not corroborate.

## Q3. Claude Code vs Claude.ai: Anthropic's software-development report (Apr 2025) and later Claude Code usage data (2025-2026), including non-coding uses

### Takeaway
Claude Code is an automation tool. In April 2025, 79% of Claude Code conversations were automation versus 49% for coding chats on Claude.ai. Front-end web work led: JS/TS 31% and HTML/CSS 28% of queries. Anthropic's Oct 2025 to Apr 2026 study of about 400,000 sessions shows Claude Code broadening beyond fixing code. Debugging's share fell from 33% to 19%, while operating software, data analysis and non-code writing grew. Users from non-software occupations, such as business, finance, design and management, are a growing minority with similar success rates. Claude Code is not a learning surface: augmentation and learning are "substantially lower" there.

### Cited Findings
**Apr 28, 2025 report**
- Data: 500,000 coding interactions, Apr 6-13, 2025, split about evenly between Claude.ai (Free and Pro, coding only) and Claude Code (first-party API sessions). Platforms are reweighted equally.
- Claude Code is 79% automation and 21% augmentation; Claude.ai coding is 49% automation.
- Feedback loop: 35.8% on Claude Code vs 21.3% on Claude.ai. Directive: 43.8% vs 27.5%. "All augmentation subtypes, including Learning, were substantially lower on Claude Code."
- Languages, as share of queries across both platforms: JS/TS 31%, HTML/CSS 28%, Python 14%, SQL 6%. HTML on Claude.ai is likely inflated by Artifacts.
- Tasks: UI/UX component development 12%, web and mobile app development 8%.
- Users: startups were 32.9% of Claude Code work and enterprise 23.8%. I could not confirm these figures because my memory of the page differs; re-read before quoting. Students, academics, personal projects and tutorial or learning users made up "about half" of interactions on both platforms.
- [verified, from a page summary] — [Anthropic, Apr 2025](https://www.anthropic.com/research/impact-software-development)

**Jun 16, 2026 "How Claude Code is used in practice" (Hitzig et al.)**
- Data: about 400,000 interactive sessions from about 235,000 people, Oct 2025 to Apr 2026. Surfaces: CLI, Claude.ai and the desktop app. Excluded: third-party IDEs, SDKs and headless runs.
- Task mix over the full period: fixing 26%, writing or building code 25%, operating software 17%, planning or exploring 14%, analysis or prose 13%, testing and orchestration 5%.
- Changes from Oct 2025 to Apr 2026: fixing fell from 33% to 19%; operating software rose from 14% to 21%; writing and data analysis each roughly doubled, from about 10% to about 20%. The shift is toward "deploying and running code, analyzing data, and writing non-code documents."
- Occupation was inferred for about 70% of sessions.
  - Computer and Mathematical is largest.
  - Next come Business and Financial; Arts, Design and Media; Management; and Life/Physical/Social Sciences.
  - Management, sales and legal are the fastest-growing non-software groups.
  - Verified success: about 30% for software occupations vs about 26% for others. In code-producing sessions: 34% vs 29%.
- Novice-rated sessions: 15% verified success and 19% abandonment, versus 28-33% success and 5-7% abandonment for everyone else.
- Users make about 70% of planning decisions and about 20% of execution decisions.
- No learning or education share is reported.
- [verified] — [Anthropic, Jun 2026](https://www.anthropic.com/research/claude-code-expertise)

**Other Claude Code data points**
- Jun 2026 Index: Claude Code's AI-autonomy score is 0.37 points higher than chat or Cowork. Opus serves 54% of Claude Code sessions vs 10% of chat and Cowork. [verified] — [Anthropic Jun 2026](https://www.anthropic.com/research/economic-index-june-2026-report)
- Science study (Nov 2026; 207,049 consumer sessions, Aug 2 to Sep 30, 2026; 78,135 of them Claude Code): computer science is 32.7% of Claude Code science sessions; data analysis is 33.7% of sessions on Claude and 48.1% on Claude Code. [check, search snippet only] — [Anthropic "How scientists use Claude"](https://www.anthropic.com/research/how-researchers-use-claude)

### Inferences
- For a general-population learning coach, Claude Code is the wrong reference population. It is used by technical people and increasingly by knowledge workers, mostly to delegate. Its relevance is that non-developers now "build" with agents, and novices fail or abandon more often (15% success, 19% abandonment). That is a coachable gap.
- Coding's falling share on ChatGPT (12% to about 5%) and on Claude.ai (40% to 34-35%), alongside its rise on the API and Claude Code, points the same way. Coding demand has moved from chat to agentic tools rather than disappeared.

### Gaps
- No published share of Claude Code sessions that are explicitly learning or tutoring. No exact share of Claude Code users outside software occupations.
- The startup vs enterprise numbers in the Apr 2025 report need re-checking.

## Q4. Other large datasets for triangulation: Microsoft Copilot, Pew, WildChat and LMSYS, others

### Takeaway
Microsoft's 37.5 million-conversation consumer Copilot study (Jan to Sep 2025) publishes ranks, not shares. Searching is the #1 intent, then advice, creating and learning. Technology is the #1 topic, then work and career, health and fitness, and language learning and translation. Health dominates on mobile. In Microsoft's enterprise M365 Copilot Chat data, editing the user's text is the single largest intent, at about a quarter of usage. In Pew's Feb 2026 survey of US adults, searching for information is the most common self-reported use (42% of adults), and emotional support (10%) and companionship (4%) are small. Public research logs such as WildChat and LMSYS predate 2025 and are skewed toward creative writing and coding.

### Cited Findings
**Microsoft consumer Copilot, "It's About Time" (Costa-Gomes et al., arXiv 2512.11879, Dec 2025)**
- Data: 37.5 million de-identified conversations, randomly sampled at about 144,000 a day from Jan 7 to Sep 25, 2025. All enterprise traffic and commercial or educational accounts are excluded. Machine classifiers assign one of 30 topics and one of 11 intents per conversation; no human review.
- Overall ranks:
  - Topics: Technology 1, Work and Career 2, Health and Fitness 3, Language Learning and Translation 4, Society/Culture/History 5.
  - Intents: Searching 1, Advice 2, Creating 3, Learning 4, Technical Support 5.
- Health and Fitness with Searching is the most frequent topic-intent pair on mobile all year. Desktop is work and technology during business hours. No percentage shares are published.
- [verified] — [arXiv 2512.11879](https://arxiv.org/html/2512.11879v1); [Microsoft AI, Dec 10, 2025](https://microsoft.ai/news/its-about-time-the-copilot-usage-report-2025/)
- The Microsoft blog post says "searching for information remains Copilot's most popular feature" and reports "a clear rise in people seeking advice". [verified] — [Microsoft AI](https://microsoft.ai/news/its-about-time-the-copilot-usage-report-2025/)

**Microsoft M365 Copilot Chat, enterprise (Counts et al., arXiv 2605.23958, May 2026)**
- Data: 175,274 prompts (Feb 16-22, 2026) plus about 5.3 million prompts as a time series (Jun 1 to Sep 22, 2025). EU and education accounts are excluded.
- Information Inquiry plus Content Refinement is "almost 60%" of prompts.
- Editing text for content refinement is "almost one quarter of usage". General information questions are about 10%; data analysis 1.5%.
- Over Jun-Sep 2025, Information Inquiry fell from 38% to 33% and Content Refinement rose from under 22% to 28.5%.
- [verified] — [arXiv 2605.23958](https://arxiv.org/html/2605.23958v1)

**Microsoft Bing Copilot (Tomlinson et al., "Working with AI", arXiv 2507.07935, Jul 2025, revised Oct 2026)**
- About 200,000 conversations over 9 months. "The most common and successful AI-assisted work activities involve information work." No category percentages were in the abstract I read. [verified, abstract only] — [arXiv 2507.07935](https://arxiv.org/abs/2507.07935)

**Microsoft Copilot health (2026)**
- More than 500,000 health conversations (Jan 2026). Nearly 1 in 5 involve personal symptom assessment. About 1 in 7 personal health queries are on behalf of someone else. [check] — [Microsoft Research](https://www.microsoft.com/en-us/research/blog/msr-research-item/how-people-use-copilot-for-health/); [HIT Consultant](https://hitconsultant.net/2026/03/10/microsoft-copilot-health-usage-report/)

**Pew Research Center, "Americans and AI 2026" (published Jun 17, 2026; fielded Feb 17-23, 2026; 5,119 US adults on the American Trends Panel, weighted to the US adult population)**
- 49% of US adults use AI chatbots, up from 33% in 2024. 24% use them daily: 12% several times a day, 8% about once a day, 4% almost constantly.
- Chatbots used: ChatGPT 44%, Gemini 24%, Copilot 17%, Meta AI 14%, Grok 8%, Claude 6%, Character.ai 3%.
- Uses, as % of all US adults:
  - Searching for information 42%
  - Tasks at work 38% (of employed adults)
  - Fun or entertainment 25%
  - Creating or editing images or video 24%
  - Medical advice 20%
  - Diet and fitness information 20%
  - Getting news 13%
  - Emotional support or advice 10%
  - Companionship 4%
- Pew did not ask about writing, learning or coding.
- [verified] — [Pew, Jun 2026](https://www.pewresearch.org/internet/2026/06/17/americans-and-ai-2026-chatbots-smart-devices-and-views-on-impact/)
- Oct 2026: 8% of US adults say they use chatbots for election information (survey Oct 12-18, 2026). [check] — [Pew short read](https://www.pewresearch.org/short-reads/2026/10/23/few-americans-say-they-are-asking-ai-chatbots-for-2026-election-information/)

**Anthropic affective-use study (Jun 2025; started from about 4.5 million Claude.ai Free and Pro conversations, 131,484 affective conversations analysed)**
- 2.9% of Claude.ai conversations are affective. Companionship plus roleplay is under 0.5%; companionship alone is 0.31%.
- Sub-shares as reported: interpersonal advice 2.26%, coaching 1.13%, psychotherapy or counseling 0.34%. These sum to more than 2.9%, so the labels probably overlap.
- [verified] — [Anthropic, Jun 2025](https://www.anthropic.com/news/how-people-use-claude-for-support-advice-and-companionship)

**Informal learning in public chat logs (Chen et al., arXiv 2607.17643, Jul 2026)**
- 128,569 conversations with 491,685 user turns. "Cognitive engagement... appeared in 31.9%" of user turns; "constructive engagement, the deepest observable form of learning-oriented engagement, appeared in 4.9%." [verified, abstract] — [arXiv 2607.17643](https://arxiv.org/abs/2607.17643)

**WildChat (older context, 2024)**
- Zhao et al.: first-turn English prompts split into "assisting/creative writing" 61.9%, "analysis/decision explanation" 13.6%, coding 6.1%. [check, snippet only; the PDF was too large to fetch] — [arXiv 2405.01470](https://arxiv.org/abs/2405.01470)
- These logs come from free GPT-3.5/4 access through a research chatbot in 2023-24 and over-represent creative writing and role-play.

**LMSYS-Chat-1M (older context, 2023)**
- Topic clusters with heavy coding and benchmark-style prompts. No verified shares found. — [arXiv 2309.11998](https://arxiv.org/abs/2309.11998)

### Inferences
- Copilot's intent ranking (Searching > Advice > Creating > Learning) matches ChatGPT's Asking-heavy profile. Copilot's #4 topic, Language Learning and Translation, matches ChatGPT's Translation 4.5% plus some tutoring.
- In enterprise data (M365) editing the user's text is about 25%, while in consumer ChatGPT Edit/Critique is about 10.6% of all messages. Editing feedback is the dominant work use, and a secondary but large consumer use.
- Pew measures reach ("ever used for X"), not volume. Search at 42% of adults is about 86% of chatbot users, which is consistent with Seeking Information and Asking being the most widespread behaviours.

### Gaps
- No Google Gemini usage study with category shares was found. I searched only lightly; Pew gives reach (24% of US adults use Gemini) but no use mix.
- Microsoft's consumer Copilot study publishes ranks only. The Tomlinson et al. percentages were not read.
- No verified 2025-2026 analysis of WildChat or LMSYS task shares. The 2026 informal-learning paper's per-task breakdown was not retrieved.

## Q5. Where sources disagree (log analysis vs self-report, and across platforms)

### Takeaway
The biggest disagreements are coding and companionship. The size of the coding share depends on platform: about 4% of ChatGPT messages versus 34-40% of Claude.ai conversations. Companionship and therapy are tiny in logs (about 2-3%) but rank first in a forum-scraped HBR list and reach 10% of adults for emotional support in Pew's survey. Self-reports and logs agree that information-seeking and advice are the most widespread uses.

### Cited Findings
- **Coding:** 4.2% of ChatGPT messages vs 33% of work-related Claude conversations (Handa et al. 2025). The NBER authors attribute the gap to different user bases and to Anthropic's filter to "possibly occupational" queries. [verified] — [NBER w34255 fn. 8](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)
- Claude.ai Computer and Mathematical: 37.2% (Jan 2025), 40% (Mar 2025), 34% (Nov 2025), 35% (Feb 2026). [verified] — [arXiv 2503.04761](https://arxiv.org/abs/2503.04761); [Jan 2026 PDF](https://www-cdn.anthropic.com/096d94c1a91c6480806d8f24b2344c7e2a4bc666.pdf); [Mar 2026 PDF](https://cdn.sanity.io/files/4zrzovbb/website/4053bf3440c0c85b8852052770c5b4cf882689c3.pdf)
- **Companionship and therapy:** ChatGPT has 1.9% Relationships and Personal Reflection and 0.4% Games and Role Play. NBER contrasts this with Zao-Sanders (2025), which ranks Therapy/Companionship as the top use. NBER says that list was built from Reddit, Quora and articles and is "likely... unrepresentative". [verified] — [NBER w34255 pp. 2-3](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)
- Claude.ai is 2.9% affective, with under 0.5% companionship and roleplay. [verified] — [Anthropic, Jun 2025](https://www.anthropic.com/news/how-people-use-claude-for-support-advice-and-companionship)
- Pew: 10% of US adults use chatbots for emotional support or advice; 4% for companionship. [verified] — [Pew 2026](https://www.pewresearch.org/internet/2026/06/17/americans-and-ai-2026-chatbots-smart-devices-and-views-on-impact/)
- **Self-report bias:** NBER notes "there are reasons to expect bias in self-reports" and cites Ling and Imas (2025). [verified] — [NBER w34255 p.1](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)
- **Misquotation in the literature:** Microsoft's Copilot paper says OpenAI found "Writing was about 77% of conversations". The 77% is actually Practical Guidance, Seeking Information and Writing combined. [verified] — [arXiv 2512.11879 intro](https://arxiv.org/html/2512.11879v1) vs [NBER w34255](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)
- **Taxonomy mismatch:** OpenAI classifies topic and intent per message. Anthropic classifies O*NET occupation and task per conversation, plus collaboration mode. Microsoft gives one topic and one intent per conversation. Pew asks about ever having used chatbots for each purpose. [verified, synthesised from the methods sections above]

### Inferences
- Use logs for ranking shares of activity. Use Pew for reach across the adult population.
- Treat Anthropic's occupational shares as a technical-skewed upper bound for coding.
- Treat ChatGPT's mix as the best proxy for the general population. It is the largest and most consumer-heavy sample, but it excludes under-18s, logged-out users and opted-out users.

### Gaps
- No study classifies ChatGPT, Claude and Copilot logs with the same taxonomy.
- No log study covers under-18 users, who are excluded from NBER.

## Q6. Synthesis for the coach: top-10 use cases for the general population, and the size of the five coach-relevant buckets

### Takeaway
Using ChatGPT's 24-category pooled shares (May 2024 to June 2025, about 1.1 million messages) as the general-population anchor, the top 10 are below. Other sources move the order but not the membership. For a learning coach, the key sizes are:
- Seeking information: about 21-24% of messages; the #1 intent in Copilot and the #1 reach measure in Pew.
- Practical guidance and advice: about 28-29%, including how-to 8.5% and health 5.7%.
- Writing: about 24-28%, of which editing, critiquing, translating or summarizing the user's own text is about 19% of all messages and editing/critique alone 10.6%.
- Tutoring and teaching: 10.2% on ChatGPT; Claude.ai's Educational Instruction is 9-15%, and its learning collaboration pattern is about 21-28%.
- Coding: 4.2% on ChatGPT but 34-40% on Claude.ai, and dominant on Claude Code.

### Cited Findings
**Ranked general-population use cases, ChatGPT consumer messages, pooled May 2024 to Jun 2025** [verified, Fig. 9] — [NBER w34255](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)

| Rank | Use case (OpenAI sub-category) | % of all messages | Triangulation |
|---|---|---|---|
| 1 | Specific info / factual lookup | 18.3 | Copilot intent #1 "Searching"; Pew #1 use at 42% of adults |
| 2 | Edit or critique the user's text | 10.6 | M365 Copilot: editing about 25% of enterprise prompts |
| 3 | Tutoring or teaching | 10.2 | Claude.ai Educational Instruction 9-15%; Copilot intent "Learning" #4 |
| 4 | How-to advice | 8.5 | Copilot intent "Advice" #2 and rising |
| 5 | Personal writing or communication (emails, posts) | 8.0 | — |
| 6 | Health, fitness, beauty or self-care | 5.7 | OpenAI Jan 2026: >5% health [check]; Pew medical advice 20% of adults; Copilot mobile topic #1 |
| 7 | Translation | 4.5 | Copilot topic "Language learning and translation" #4 |
| 8 (tie) | Computer programming | 4.2 | Claude.ai Computer & Math 34-40% |
| 8 (tie) | Create an image | 4.2 | Pew images or video 24% of adults |
| 10 | Creative ideation | 3.9 | — |
| next | Argument or summary generation | 3.6 | — |
| next | Mathematical calculation | 3.0 | — |

- Coarse buckets at about mid-2025: Practical Guidance about 29%, Seeking Information about 24%, Writing about 24%, Multimedia about 7%, Technical Help about 5%, Self-Expression about 4%. [verified] — [NBER w34255 §5.2](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)
- Mode: Asking 51.6%, Doing 34.6%, Expressing 13.8% (late June 2025). [verified] — [NBER w34255 §5.3](https://www.nber.org/system/files/working_papers/w34255/w34255.pdf)

### Inferences
- **Writing and editing the user's own text:** about 19% of all ChatGPT messages. That is Edit/Critique 10.6%, Translation 4.5% and Summary 3.6%, two-thirds of Writing. It is the largest single work use: about 40-42% of work messages are Writing.
- **Tutoring and teaching:** about 10% of ChatGPT messages. A broader "learning" framing (Anthropic's learning mode, ChatGPT's Asking in Practical Guidance and Technical Help) puts it nearer 20-25%.
- **Practical guidance and advice:** about 28-29%, stable and the largest coarse bucket.
- **Seeking information:** about 21-24% and the fastest-growing. Asking messages also get the best satisfaction ratings.
- **Coding:** small in general consumer chat (about 4-5%) but a third of Claude.ai, and has largely moved to agents.
- Ranks 1-4 are robust across sources. Positions 5-12 sit within about 1.5 points of each other and could reorder with newer data. Multimedia and Seeking Information grew through 2025; Writing shrank.
- **Design implication:** most users arrive to ask and get advice, not to be taught. A coach prompt should treat factual and how-to asks as teachable moments. Explanation-first support for the user's own writing is the biggest "doing" use. In Anthropic's data, the more experienced users iterate and seek learning more, and succeed more often (+3 to +6 points).

### Gaps
- No 2026 general-population log study with category shares. The ChatGPT data ends June 2025 and the Claude.ai data ends June 2026, but on a non-representative user base.
- No study reports the share of tutoring delivered Socratically versus answer-giving. The closest is Chen et al. (2026): constructive learning engagement in 4.9% of user turns.
