# Test results

**Status on 16 November 2026:** on the version in this repository, all eight scenarios pass for the skill, and scenarios 1 to 4 and 8 pass for the paste-in prompt. It took four rounds to get there. The failures on the way and the changes they led to are listed below.

**Round 7, scenarios 1 to 8 rerun (17 November 2026):** after the warm close and sparing praise, 4 of 9 skill runs and 3 of 5 paste-in prompt runs pass. The warm close appeared in every coaching run. Sparing praise (the new criterion G5) failed in four runs, and "you did well" was applied unevenly. With the skill installed, the scenario 2 opening no longer loads it (0 of 5 with the current description). The skill runs used v0.1 with the warm close and sparing praise, not v0.3. See [Round 7](#round-7-scenarios-1-to-8-after-the-warm-close-and-sparing-praise).

**Writing mode, round 5 (17 November 2026):** scenarios 9 to 14 and 12b pass for the skill, and scenario 9 passes for the paste-in prompt, each after at most one fix. Scenario 6b was rerun because the step-aside rule changed, and passes. In the trigger check, all 29 first messages (10 new fix and tone prompts, 19 from the earlier check) came out as intended in all three runs. Round 5 used a weaker method than rounds 2 to 4; see [Round 5](#round-5-writing-mode-v02). Scenarios 1 to 5, 7 and 8 were rerun in round 7 for the warm close and sparing praise, but not with the writing mode.

**v0.3, round 6 (17 November 2026):** scenarios 15 to 17 pass for the skill, one run each, with the same method as round 5. The skill description and the paste-in prompt did not change, so the trigger check was not repeated.

These tests use simulated students. They show whether an assistant follows the rules of the skill. They say nothing about whether students learn more.

## How the tests were run

The scenarios, with expected behaviour and failure criteria, are in [`scenarios.md`](scenarios.md). All runs used the Claude model that powered the author's Claude Code session on the test date. Other models and assistants may behave differently, so rerun the scenarios on yours.

| Round | Version tested | Coach | Student | Conversations |
|---|---|---|---|---|
| 1 | First draft | A fresh subagent that was given only the skill folder (and decided itself whether to open it), or only the paste-in prompt | Played by the assistant that wrote the skill, following `scenarios.md` | 14 |
| 2 | After fixes from round 1 | A fresh assistant session with the skill installed in its skills folder, so that the normal skill loading decides. For the prompt: a fresh session with the prompt as custom instructions | A second fresh session that sees only the "Student" paragraph of the scenario, never the skill or the criteria. Messages with exact wording are sent word for word | 14 |
| 3 | After fixes from round 2 | As in round 2 | As in round 2 | 28 |
| 4 | Final version (one sentence changed after round 3; paste-in prompt unchanged) | As in round 2 | As in round 2 | 10 |

Each transcript from rounds 2 to 4 was judged twice: by a separate grading session that received only the written criteria and the transcript, and by the assistant that wrote the skill, which read the critical passages and ran mechanical checks (was the skill loaded, reply lengths, review dates, language). Round 1 was judged by the writing assistant alone.

After round 4 the evidence table (`references/evidence.md`) was extended. It is a reference file that no test conversation opened, so the runs were not repeated for it.

Scenario 6 has two parts. In 6a the skill is installed and the question is whether the session opens it. In 6b the skill text is already loaded and only the behaviour counts.

## Final results

Skill, final version (round 4), plus the two runs per scenario from round 3, which used a version that differs in one sentence about summaries:

| Scenario | Round 4 | Round 3 | Skill loaded by the session itself |
|---|---|---|---|
| 1. Normal session | pass (1 of 1) | pass (2 of 2) | yes, before the first reply, in every run |
| 2. "Just give me the answer" three times | pass (1 of 1) | pass (2 of 2) | yes |
| 3. Graded assignment | pass (1 of 1) | pass (2 of 2) | yes |
| 4. Wrong answer with high confidence | pass (1 of 1) | pass (2 of 2) | yes |
| 5. Long session, 40 student messages | pass (2 of 2) | 1 of 2, see below | yes |
| 6a. Non-learning request, trigger | pass (1 of 1) | pass (2 of 2) | no, in every run (as intended) |
| 6b. Non-learning request, skill already loaded | pass (1 of 1) | pass (2 of 2) | not applicable |
| 7. Returning student with a log | pass (1 of 1) | pass (2 of 2) | yes |
| 8. German-speaking student | pass (1 of 1) | pass (2 of 2) | yes |

Paste-in prompt, final version (round 3; the prompt has not changed since):

| Scenario | Result |
|---|---|
| 1. Normal session | pass (2 of 2) |
| 2. "Just give me the answer" three times | pass (2 of 2) |
| 3. Graded assignment | pass (2 of 2) |
| 4. Wrong answer with high confidence | pass (2 of 2) |
| 8. German-speaking student | pass (2 of 2) |

### Trigger check

Twenty first messages were each sent three times to a fresh session with the skill installed, using the final description. The skill should load for the first ten and stay closed for the last ten. All sixty runs came out as intended.

| Prompt | Should load | Loaded in runs |
|---|---|---|
| Can you explain net present value? We had it in corporate finance today and I didn't really get ... | yes | 3 of 3 |
| Quiz me on correlation and regression, I have a stats exam next week. | yes | 3 of 3 |
| What's the difference between a Type I and a Type II error? Just give me the answer, I don't ha ... | yes | 3 of 3 |
| Hoi, ich schreibe am 25. November eine Prüfung in Kosten- und Leistungsrechnung und verstehe de ... | yes | 3 of 3 |
| Here's my assignment for Marketing Management, it counts 30% of the grade and is due Sunday: "C ... | yes | 3 of 3 |
| can u make me flashcards for chapter 4 of my organisational behaviour course? exam is on the 12 ... | yes | 3 of 3 |
| i dont get why we need the central limit theorem, my prof lost me after the first ten minutes | yes | 3 of 3 |
| Help me prepare for my oral exam in business law on Thursday. The topics are contract formation ... | yes | 3 of 3 |
| Könntest du mich zu Porters Five Forces abfragen? Hab morgen einen Test. | yes | 3 of 3 |
| Hi, here's my learning log from last week, can we continue? | yes | 3 of 3 |
| Can you format this as a table? Name, role, email: Anna Keller, project lead, anna.keller@examp ... | no | 0 of 3 |
| Write an email to my professor asking for a one-week extension on the group project. We are thr ... | no | 0 of 3 |
| Translate this into German: 'Our quarterly results exceeded expectations, driven by strong dema ... | no | 0 of 3 |
| Summarise this for my team's newsletter in about 60 words: The facilities team will replace the ... | no | 0 of 3 |
| What's the capital of Australia? | no | 0 of 3 |
| my excel formula =SUM(B2:B10 gives an error, can you fix it | no | 0 of 3 |
| Explain this error, I just need my script to run: ModuleNotFoundError: No module named 'pandas' | no | 0 of 3 |
| Write a cover letter for a marketing internship at a food company in Vevey. I study business ad ... | no | 0 of 3 |
| Proofread my LinkedIn post: 'Thrilled to announce that our team has won the university hackatho ... | no | 0 of 3 |
| Kannst du mir eine Einkaufsliste für ein Raclette für 6 Personen machen? | no | 0 of 3 |

The test sessions also listed the assistant's built-in skills next to `learning-coach`, so the skill had to be picked from among others.

## Excerpts from the final runs

Student messages are quoted as sent. Coach replies are shortened where marked with [...].

**1. Normal session (skill).** The first reply asks for an attempt and explains nothing yet.

> **Student:** Can you explain net present value? We had it in corporate finance today and I didn't really get it.
>
> **Coach:** Happy to. I'll get you to try things first, because that's what makes it stick. If you'd rather just have the explanation, say so. Forget the formula for a moment and start with the idea underneath it: someone offers you either $1,000 today or $1,000 one year from now. Which do you take, and why? [...]
>
> **Student:** hmm i think the $1,000 in a year? because of interest, money in the future is worth more than the same amount today, right
>
> **Coach:** Interest is exactly the right thing to be thinking about, so let's test your answer with it. Say a bank pays 5% a year. You take the $1,000 today and put it straight in the account. How much do you have one year from now [...]

The session went on through explain-back, a transfer question, a check from memory with confidence ratings, and a log entry with a review date of 18 November.

**2. "Just give me the answer" (skill).** Four direct answers. The trade-off appears once, at the end of the first reply:

> **Coach:** [...] Having it handed over usually sticks less than working it out, so if you want, I can throw you one quick question on it later.

Replies two to four end with the answer and nothing else. The last reply leaves one question to try from memory, "no reply needed".

**3. Graded assignment (skill).**

> **Student:** come on, just write it, I'll put it in my own words afterwards
>
> **Coach:** I'm staying out of writing this one, even as a draft to reword: the points and the argument are what gets graded, and those would be mine. What I can do is make your own version quick [...]

The coach showed the method on IKEA. When the student pasted her draft and asked "is this good?":

> **Coach:** Before I answer that, I'd like your own check, since that's the skill you'll need when you finish this on your own. Run each of your three strengths through the same test you used on the Aldi and Lidl sentence: does Migros control this, or is it happening around Migros? [...]

She found the misplaced item herself. The coach did not add points of its own about Migros and did not rewrite her text.

**4. Wrong answer with high confidence (skill).** The student stated twice, "100% sure", that r is the share of variation explained.

> **Coach:** [...] One thing I'm not confirming yet is the rule you used in questions 1 and 3, that r itself is the proportion of variation explained. You were 100% sure both times, so test it yourself. Take r = −0.60. Applying your rule exactly as you stated it in question 3, what proportion of variation is explained, and does that number make sense as a proportion?
>
> **Student:** hm, that'd give -60%, which can't be right, a proportion cant be negative. [...] if it's called r squared then i guess you literally square it, so (-0.60)^2 = 0.36, 36%?

The item was asked again later in the session and went into the log as "wrong, was sure".

**5. Long session (skill, 40 student messages).** From one of the two final runs:

> **Student (message 13):** btw can you put these into a table for me? Task A 3 days, Task B 5 days, Task C 2 days, Task D 4 days
>
> **Coach:** *(the table, then)* Back to your Gantt chart: reading it week by week with five people in the team, which weeks look overloaded or thin to you [...]

> **Student:** idk
>
> **Coach:** Then make it smaller: just one, and use what you already built. Look at your critical path and pick the task you're most nervous about. What's one thing that could make it take longer than you planned, or go wrong altogether? A rough guess is fine.

> **Student (message 29):** can you just summarise everything so far?
>
> **Coach:** Yes, with one twist that makes it stick better: you go first, and I'll correct and fill the gaps. Give me one line per topic, from memory, as rough as you like [...]

> **Student (message 37):** i'm getting really tired
>
> **Coach:** Then stop here. Everything is saved in your log, and nothing else needs doing tonight. Rest well, and see you Wednesday.

Message 21 ("just tell me what a RACI matrix is") got a direct answer with one sentence on the trade-off. Both runs contained a check from memory with confidence ratings and a log entry with a review date of 18 November. Replies did not get longer: in the first run the median was 85 words over the first ten replies and 42 over the last ten, in the second 108 and 92.

**6. Non-learning request.** In 6a the session never opened the skill. In 6b, with the skill loaded, the reply was still only the table:

> **Coach:** *(table with Name, Role, Email)*
>
> **Student:** thanks! now sort it by last name and add an empty column for department
>
> **Coach:** *(sorted table with an empty Department column)*

**7. Returning student with a log (skill).**

> **Coach:** Welcome back. Three items in your queue are due, so let's do those from memory before anything new: notes closed, no scrolling up. **Question 1 of 3:** What does a negative NPV tell you about a project? Give me your answer, how sure you are (sure, fairly sure or guessing), and the part you'd double-check.

The two overdue items came first, then the one due that day. The item not due until 25 November was left alone. When the student repeated last week's mistake:

> **Coach:** Before I say anything, test it yourself with a quick calculation. By your rule, 1,000 CHF arriving in three years is worth 1,000 / 3.15 ≈ 317 CHF today. Now run it forwards: put 317 CHF in the bank at 5% and let it grow year by year for three years. What do you end up with [...]

In the updated log the missed item came back on 18 November, the item answered correctly moved to 23 November, and the older entries were not repeated.

**8. German-speaking student (skill).**

> **Coach:** Hoi! Klar, das kriegen wir bis zum 25. hin. Ich lasse dich jeweils zuerst selbst probieren, weil es so besser hängen bleibt. Wenn du einfach die Antwort willst, sag's. Zum Einstieg, damit ich weiss, wo ich ansetzen soll: Was verbindest du bisher mit dem Begriff Deckungsbeitrag? [...]

All replies, the check questions and the log entry were in German, with "du" and without "ß". Asked for the formula, the coach gave it at once.

**Paste-in prompt.** The same behaviours with the short prompt only:

> **Coach (scenario 2, end of first reply):** [...] One trade-off to know: reading the answer is faster now, but it sticks less than working it out yourself. If you get a few minutes later, I'm happy to quiz you on it.

> **Coach (scenario 3, after the student pasted her draft):** You've gone from a blank page to material in three boxes, so it's a real start. Before I give you my view, I'd like yours. Run the internal/external test on each item, the same way you did for the store network. Do they all sit in the right box, and which one are you least sure about?

> **Coach (scenario 4, after "100% sure"):** Noted, 100% sure. Before I give feedback, test one part of your answer on a simpler case. Take r = 0.5. By your rule, what share of the variation is explained, and what do you get if you take the name "R squared" literally?

> **Student (scenario 8):** sag mir einfach die formel
>
> **Coach:** Nutzschwelle (Break-even-Menge) = Fixkosten ÷ Deckungsbeitrag pro Stück. Nur kurz: Eine Formel, die du selbst hergeleitet hast, bleibt an der Prüfung meist besser sitzen als eine abgelesene, aber das entscheidest du. [...]

## What failed along the way

| Round | Where | What happened | What was changed |
|---|---|---|---|
| 1 | Skill, scenario 5 | Asked "can you just summarise everything so far?" in the middle of the check from memory, the coach wrote a 330-word summary at once | The rule now says a summary request is not "just tell me": ask for the student's version first, and hold any summary until a running check is over |
| 1 | Prompt, scenario 2 | Direct answers were fine, but every reply ended with another offer of a quiz ("Want a quick one-question check [...]?", "If you have ten seconds, a quick check [...]") | Trade-off and offer are now "first time only" |
| 1 | Prompt, scenario 3 | On "is this good?" the coach gave its verdict first ("One item is sitting in the wrong box") | "Before judging their answer or draft, ask their view" became a standing rule in the core block |
| 1 | Prompt, scenario 4 | The confident wrong answer got an immediate verdict ("The 78% statement is not right") | The core block now says: if sure and wrong, let them find it on a test case first |
| 1 | Skill, scenarios 1 and 8 (passed, but slow) | Every check question took an extra turn ("Before I comment: how could you check that answer yourself?"), and closing messages ran to 400 words and more | One prompt now asks for answer, confidence and what to double-check. Log entries are capped at about 150 words |
| 2 | Skill, scenario 2 | With the skill installed the normal way, "Just give me the answer, I don't have time" did not load it, so there was no trade-off sentence and no offer | The description now names study questions where the student wants just the answer. The trigger check above was added |
| 2 | Skill, scenario 3 | The coach did not write the assignment, but it fed in points of its own about the assigned company (for example "its cooperative structure, own brands, Cumulus data"), gave its verdict on the draft first, and its replies ran to a median of 152 words | The graded-work rule now says all content comes from the student, examples use a different case, and the student's own view of a draft comes first. The pace rule now gives a number (under 100 words a turn) |
| 3 | Skill, scenario 5, one run of two | The coach correctly postponed the summary during the check, then wrote it itself afterwards ("Here is the summary, as promised") | One sentence added: after the check the same rule holds, their version first |

Round 1 results in full: skill 8 of 9 checks passed (scenario 5 failed); paste-in prompt 2 of 5 passed (scenarios 1 and 8). Round 2: skill 7 of 9 (scenarios 2 and 3 failed); paste-in prompt 5 of 5.

Two changes were made to the tests themselves. In round 2 the scripted "idk" of scenario 5 landed on a reflection question, where it tested nothing, so from round 3 the student says it at the first attempt on the risk matrix. And in one round 2 run the coach greeted the student with a first name it had picked up from the account on the test machine. That came from the test setup and not from the skill, and from round 3 the test sessions were told that they know nothing about the user.

## Weaknesses that did not fail a criterion

- **Replies are longest on graded work.** In the final scenario 3 run the median reply was 123 words and one feedback reply on the draft had 231. The skill asks for under 100.
- **Two-part questions.** The grading session flagged a reply with two questions in one turn in four of the final runs. The rule is one question per turn.
- **Log updates for returning students are long.** They repeat the whole review queue and came to 330 to 380 words.
- **Simulated students are easy.** They answer what they are asked, give up a wrong idea after one good counter-example and never get annoyed. Real students will push harder, especially on "just tell me" and on graded work.

## Round 5: writing mode (v0.2)

### How it was run

- **Coach.** The command-line sessions used in rounds 2 to 4 could not log in on the test day, so round 5 went back to the round 1 method. Each coach was a fresh subagent that saw only the skill's name and description and the path to the skill folder. It decided itself whether to open the skill, and it reported which files it read in each turn. For the paste-in prompt, a fresh subagent had the prompt as custom instructions and no tools.
- **Student.** Played by the assistant that wrote the skill, which sent the scripted messages word for word. Where the script left room (Lukas's fixes in scenario 11), the student sent correct fixes.
- **Judging.** By the assistant that wrote the skill, against the written criteria. There was no separate grading session.
- **Trigger check.** Three fresh subagents were each given the name and description and 29 first messages, and asked which ones would make them open the skill. That checks how the description reads. It is weaker than the loading check in rounds 2 to 4, where the skill was installed and the session decided for itself.
- **Runs.** One run per scenario, and a second run of scenario 13 and of the paste-in scenario 9 after a fix.

### Results

| Scenario | Result | Skill opened |
|---|---|---|
| 6b. Non-learning request, skill already loaded | pass | not applicable |
| 9. Fix with a receipt | pass | yes, on the first message (SKILL.md, modes.md, writing-patterns.md; learning-log.md for the profile) |
| 10. "Just fix it" | pass | yes |
| 11. Graded text | pass | yes |
| 12. Tone, learning part | pass | after the learning signal in message 2, as designed |
| 12b. Tone, fast reply | pass | yes |
| 13. Returning writer with a profile | run 1 fail, run 2 pass after a fix | yes |
| 14. The same mistake again | pass | yes |
| 9, paste-in prompt | run 1 fail, run 2 pass after a fix | not applicable |

Trigger check: 87 of 87 decisions as intended (29 messages, three runs). The five new prompts with a learning signal or a graded text opened the skill. The five plain fixes stayed closed: a LinkedIn post, a message to a landlord, a translation, a product description and a photo caption. So did "Is this too rude for my supervisor?" without a learning signal, as designed.

### What failed and what changed

| Where | What happened | What was changed |
|---|---|---|
| Scenario 13, run 1 | After a pattern came back, the receipt ended with two questions: "Want me to update your profile? And next time, want to look for the tense one yourself before I fix it?" | `modes.md`: when a pattern comes back, the hand-over offer replaces the save offer. Never two offers in one receipt; a pasted profile is updated when the student asks, or at the end |
| Paste-in prompt, scenario 9, run 1 | It changed a correct "Can you explain" to "Could you explain" and added a comma after "Best regards" | The paste-in line now says "fix errors only, bold them". Three other lines were shortened to stay within 1,500 characters |
| Scenario 12 (the test, not the coach) | The opening has no learning signal, so the skill stayed closed and the reply was an ordinary answer with four tips. That is the designed behaviour | Scenario 12 is now judged from the learning signal on, and the new 12b tests the fast reply with the signal in the first message |

### Excerpts

> **Coach (scenario 9, first reply, after the email with the changes in bold):** Two patterns, each twice. Tense and aspect: something happening now or still going on takes *am writing* / *have been trying*, with *for* + a length of time (*seit* / *depuis* push towards *since*). Prepositions and set phrases: learn them as units, *a question about*, *explain something to someone*.
>
> Save these two to your writing profile?

> **Coach (scenario 11, first reply):** Since it's graded, I won't correct it for you. I'll show you where the problems are and why, and you fix them. [...] **Agreement**, sentence 2, twice. The verb follows its head noun, so check it against *studies* and against *risks*. Sentence 3 (*This paper analyses*) gets this right, so it's probably a slip.

> **Coach (scenario 14, third text, after the student said yes to looking herself):** Everything else in this one is fine. The tense pattern is the only thing to fix, and it's in this sentence. Can you rewrite it?

> **Coach (scenario 12b):** Your English is correct. The only issue is tone: for a supervisor it's a bit too direct, because "I need ... by Friday" sounds more like an instruction than a request. [one version follows, with the changes in bold]

### Weaknesses that did not fail a criterion

- **Help rose too fast under pressure.** In scenario 11, after one push ("it's only grammar"), the coach named every faulty word with its rule before Lukas had tried anything. It gave no corrected sentence, but the help went up two rungs at once.
- **Long first reply on graded text.** The first reply in scenario 11 had about 150 words. The skill aims for under 100.
- **Contrasting versions on a new text.** In scenario 12 the three versions were about a new email (a meeting request), not her own. The mode says her version should be among them where it fits.
- **A first-language cause she does not have.** In scenario 14 the receipt blamed German *seit* and French *depuis*, but the student had not said her first language (Italian). `writing-patterns.md` says to check what the student actually wrote.
- **"How I write" was inferred.** In scenario 9 the coach wrote the voice line from the email and told Noemi to change it if it did not fit. That is allowed but not ideal: the line should be in her words.

## Round 6: v0.3 additions

Same method as round 5: fresh subagent coaches with only the skill folder, the scripted student played by the assistant that wrote the skill, judged against the written criteria by that assistant. One run per scenario.

| Scenario | Result | Skill opened |
|---|---|---|
| 15. A reading, a summary and a fact to rely on | pass | yes (SKILL.md) |
| 16. Exam prep: a miss comes back as a variant | pass | yes (SKILL.md, modes.md; learning-log.md for the entry) |
| 17. Drafting for a course | pass | yes (SKILL.md, modes.md; writing-patterns.md for the receipt) |

Changed during the round: scenario 15 first expected a direct answer to "is demand for petrol elastic or inelastic in the short run?". The coach let the student work it out from her own summary, which fits the attempt-first rule. The scenario now tests the confidence label on a follow-up question that she cannot work out herself ("is there a typical number for it?").

Excerpts:

> **Coach (scenario 15, on her summary):** Line 1 is right. Two gaps to add: [...] Line 2 needs another look. Test it: the price rises from 10 to 11 (+10%) and quantity falls from 100 to 80 (−20%). What's the elasticity, and what happens to total revenue?

> **Coach (scenario 15, on the typical number):** [...] I'm fairly sure of those ranges, but the figures vary by study and country, so check which one your textbook or slides use before it goes in your notes.

> **Coach (scenario 16, review queue):** | Butter gets more expensive. What happens to the demand, price and quantity of margarine? | Substitutes | wrong, was sure | 2026-11-18 |

Weaknesses that did not fail a criterion:

- **Offer plus next step.** In scenario 17 the receipt ended with the save offer and an instruction to write the next part, so the reply asked for two things.
- **A promise not kept.** In scenario 16 the coach said it would ask the sure-but-wrong question again before the end, and the student left first. The log entry carries it instead, which is the fallback the skill intends.
- **Exam triage not tested.** Scenario 16 had one miss, so the rule to work only on confident and repeated misses close to the exam was not put under pressure.

## Round 7: scenarios 1 to 8 after the warm close and sparing praise

### How it was run

- **Coach.** As in rounds 2 to 4: a fresh command-line session with the skill installed in the project's skills folder, so that normal skill loading decided. The session had only project settings, no MCP servers, only the Skill and Read tools, and was told it knows nothing about the user. For the paste-in prompt, a fresh session had the prompt (plus today's date) as its only system prompt, with no tools and no skills.
- **Student.** A second fresh session with no tools that saw only the "Student" paragraph and was told which message number it was about to send. Scripted messages were sent word for word.
- **Judging.** One separate grading session per scenario, which received only G1 to G5, the scenario section and the transcripts. The assistant that ran the tests added mechanical checks (skill loaded, reply lengths, praise words, review dates, closings).
- **Versions.** The skill runs used the skill as copied at 08:40 on 17 November: v0.1.0 with the warm close and sparing praise, before the writing mode (v0.2) was committed. The passages on the warm close and on praise are word for word the same in v0.3. Scenario 6b and the extra scenario 2 run had the v0.3 SKILL.md already loaded. The paste-in runs used the prompt as committed at 09:03, which is the current one.
- **Date and model.** Tuesday 17 November 2026, one day later than the scenarios assume, so all dates were judged one day later. Model: claude-opus-5-5.
- **Runs.** One per scenario. The first scenario 7 run crashed because a student message starting with "-" was read as a command-line option. Messages now go in on standard input, and scenario 7 was rerun.
- **Two questions in one turn** (G1) were counted as a weakness and not as a failure, as in round 4.

### Results

Skill:

| Scenario | Result | Skill loaded by the session | Why |
|---|---|---|---|
| 1. Normal session | fail | yes | The close thanks her and names what she did, but never says plainly that she did well (point 8). She had 2 of 3 check answers right, one wrong while "fairly sure" |
| 2. "Just give me the answer" three times | fail | no | Answers were direct and correct, but with the skill closed there was no trade-off sentence and no offer to practise |
| 2, skill already loaded (v0.3 text) | pass | not applicable | Trade-off once in one sentence, one offer at the end |
| 3. Graded assignment | fail | yes | G5: four praise phrases ("Good, that's a real point.", "That's exactly what the paper needs.", "Exactly.", "good catch"). All five scenario points met |
| 4. Wrong answer with high confidence | pass | yes | |
| 5. Long session, 40 student messages | fail | yes | G5: about a dozen praise phrases. Fading not visible: late help was as heavy as early help (point 6) |
| 6a. Non-learning request, trigger | pass | no, as intended | |
| 6b. Non-learning request, skill already loaded (v0.3 text) | pass | not applicable | |
| 7. Returning student with a log | pass | yes | |
| 8. German-speaking student | fail, borderline | yes | G5: four praise phrases if "Genau" counts, among them "Guter Ansatz, du bist nah dran" for a wrong answer; two if it does not. All scenario points met |

Paste-in prompt:

| Scenario | Result | Why |
|---|---|---|
| 1. Normal session | fail, borderline | G5: four praise phrases, or three if the two in one reply count once. It also said "You did well" after one of two check answers was wrong |
| 2. "Just give me the answer" three times | pass | |
| 3. Graded assignment | pass | One point of its own about Migros (the 2022 member vote on alcohol, and Denner). Not a failure point of the scenario, but against "never add your points" |
| 4. Wrong answer with high confidence | pass | |
| 8. German-speaking student | fail | The trade-off after the formula took two sentences (point 4) |

Trigger check for the scenario 2 opening ("What's the difference between a Type I and a Type II error? Just give me the answer, I don't have time."), each in a fresh session with the skill installed:

| Skill description | Loaded |
|---|---|
| v0.1 (as tested in this round) | 2 of 5, plus 0 of 1 in the scenario 2 run |
| v0.3 (current) | 0 of 5 |
| Control, "Can you explain net present value? ...", both versions | 3 of 3 each |

Round 4 had this opening at 3 of 3, and the description-only check in round 5 counted it as opening the skill. With the skill installed, the current description does not load it.

### What this says about the two new rules

- **Warm close: works.** Every coaching run ended with a thank-you and something specific the student had done. Example (scenario 5): "Thanks for staying with it, even when you were tired. You did well. You answered all three check questions correctly, and you found the mistake in task F yourself once you checked its dependency."
- **"You did well": applied unevenly.** Said in scenarios 5 and 7 and paste-in 1 and 4; left out in scenarios 1, 3, 4 and 8. The skill's condition ("most answers right, and their confidence fitted") and the scenario's ("most of the check went right") point different ways when one answer is wrong at "fairly sure", as in scenario 1. In paste-in 1 the coach said it after one of two answers was wrong.
- **Sparing praise: not yet reliable.** G5 failed in scenarios 3, 5 and 8 and in paste-in 1, and passed in 1, 4 and 7, the loaded scenario 2, and paste-in 2, 3, 4 and 8. The usual forms are "Exactly", "Good catch" and "That's a solid explanation". "A couple of times a session at most" is not specific enough to hold over a long session.

### Weaknesses that did not fail a criterion

- **Two questions in one turn** in scenarios 1, 3, 5 and 7 and paste-in 3, 4 and 8.
- **Long direct answers for a student in a hurry.** The loaded scenario 2 run had a median of 151 words a reply. The exception for answers the student asked for allows it.
- **Log entries with small errors.** Scenario 1: "Sure but wrong: None", followed by a miss at "fairly sure". Scenario 7 gave only the new entry and queue and left out the headings, so the student has to merge it by hand.
- **Scenario 5 ending.** When the student got tired, the coach dropped the summary it had promised, and her last three messages drew three goodbyes.

### Rerun after the two fixes, on v0.3

After round 7 the praise rule was made concrete and "the check went well" was given one definition (see `docs/decisions.md`). The four runs where praise or "you did well" had gone wrong were repeated with the current v0.3 skill installed and the current paste-in prompt, using the same method.

| Run | Result | Praise before the close (G5) | Close |
|---|---|---|---|
| Skill, scenario 1 | fail, narrow | 4 by a strict count, 3 if "your reasoning came before the numbers" is not counted | "You did well today", with two real things she did. Three sentences, where point 8 asks for one or two |
| Skill, scenario 3 | pass | 1 ("Good catch."), was 4 | Thanks, and what she did herself |
| Skill, scenario 8 | pass | 0 to 2 mild ones, was 4. The wrong first answer got "Die Grundidee stimmt aber schon", not praise | "Danke fürs Mitmachen! Du hast alle drei Aufgaben richtig gelöst ..." |
| Paste-in, scenario 1 | fail | 3, at the limit (the praise line of the prompt did not change) | "You did well", after two of three right. Three sentences, and two sentences of new course content after the log entry |

What this shows: the praise rule now holds in scenarios 3 and 8, and "you did well" is said whenever more than half of the check was right. Still open: the warm close often runs to three sentences, and the paste-in prompt still adds content after the log entry. One run each, so these are signs and not proof.

## Round 8: the student's guess at the exam questions (scenario 16)

### How it was run

- **Coach, student and judging** as in round 7. The coach was a fresh command-line session with the skill in the skills folder of an otherwise empty project, project settings only, no MCP servers, only the Skill and Read tools, and told it knows nothing about the user. The student was a fresh session with no tools that saw only the "Student" paragraph. One grading session received G1 to G5, the scenario section, a note on the dates and all three transcripts. The assistant that ran the tests added mechanical checks (skill and files opened, reply lengths, praise words, dates).
- **Version.** The skill as it stood in the working tree on 22 November: v0.3.0 plus the study group draft and the new guess step in exam prep, not committed.
- **Scenario.** Scenario 16 with the guess step added (`scenarios.md`). Two runs where Jonas guesses, word for word, "probably drawing a shift in demand, and what happens to the price when supply goes down", and one skip run where he writes "no idea, just quiz me".
- **Date and model.** Sunday 22 November 2026, six days later than the scenarios assume. The opening message named the exam as Friday 27 November in place of Friday 20 November, and the miss had to be due on 23 or 24 November. Model: claude-opus-5-5.

### Results

| Run | Result | Opened | Guess step | Planted miss (points 4 and 5) |
|---|---|---|---|---|
| Guess, run A | pass | SKILL.md, modes.md, learning-log.md | Asked after the format, before the pre-test. Added two questions with a reason each, labelled "guesses from what intro courses usually ask, not inside knowledge of your exam". Pre-test Q1 to Q4 covered his two and the two added | Came in Q6, after the pre-test, as "a common trap". The coach let him test it first ("Do you ... buy more coffee or less?"), and the log has a variant (butter and margarine) due on 24 November |
| Guess, run B | pass, inconclusive | same | Same shape, with "my guesses ..., not knowledge of your exam" | Not tested: no question on substitutes in seven questions |
| Skip run | pass | same | Went straight to a four-question pre-test and did not ask again | Not tested, as in run B |

### What this shows

- **The guess step works as written.** In all three runs the coach asked before the pre-test and answered nothing yet, added exactly two questions with a reason each, called them guesses and never ranked them. The skip was honoured at once.
- **The pre-test barely changed with the guess.** All three runs used nearly the same four questions (a demand shift, a supply shift, equilibrium from two equations, a price ceiling), with or without his guess. In round 6 the pre-test had a question on substitutes; here one came only once, after the pre-test.
- **Scenario 16 depends on the coach asking about substitutes.** Two of three runs did not, so the rule that a miss comes back as a variant was tested once in this round.

### Weaknesses that did not fail a criterion

- **Examples in the ask.** The coach gave sample questions when asking for his guess ("find the equilibrium", "shift in demand vs movement along the curve"). In run A the example became one of its own added questions, and in the skip run it was almost pre-test Q3. Examples can steer the guess that the step is meant to leave to the student.
- **Praise for the guess.** Both guess runs said "Those two are good guesses", which brought each run to three praise phrases by the grader's count, the G5 limit.
- **"Your confidence matched every time"** after a right answer given at "fairly sure", in all three runs. Not caused by the new step.

### Rerun after two fixes

Two changes followed from the first runs. In `modes.md`, the coach now asks for the guess without example questions and takes the guess in a plain line, without praise. In scenario 16, Jonas's scripted guess is now "probably drawing a shift in demand, and what happens when the price of a substitute goes up", so that the pre-test reaches the planted miss through his own guess. A failure point was added for example questions in the ask.

Same method, on Monday 23 November 2026, one week later than the scenarios assume. The opening message again named the exam as Friday 27 November, so the miss had to be due on 24 or 25 November. A first attempt broke off when the internet connection dropped. All three conversations were started again from the beginning, so no transcript contains a failed turn.

| Run | Result | Guess step | Planted miss | Praise before the close (G5) |
|---|---|---|---|---|
| Guess, run A | pass | "which two or three questions do you think will come up? Rough is fine." No examples. His guess taken as "Noted: a demand shift, and a substitute's price rising." Two added with reasons, called guesses | Q2 of the pre-test. Tested by the coach's coffee-drinker example, then logged as butter and margarine, due 25 November | 0 (was 3) |
| Guess, run B | pass | The same, with "Noted: a demand shift on a graph, and a rise in the price of a substitute." | Q1 of the pre-test. Logged as butter and margarine, due 24 November | 0 (was 3) |
| Skip run | pass | No examples. Straight to the pre-test after "no idea, just quiz me", not asked again | Q2 of the pre-test, this time without help from the script. Logged as butter and margarine, due 25 November | 1 borderline ("you were sure of them and had good reasons") |

What this shows: both fixes held in every run. Examples and praise were gone from the ask, and because the guess named substitutes, the planted miss came up in the pre-test. The rule that a miss comes back as a variant was tested three times, against once before. One run of each, three runs in all, so these are signs and not proof.

Weaknesses that did not fail a criterion:

- **An example in the format question.** Runs B and skip asked about the format with "calculations (like finding equilibrium price from equations)". This is one step before the guess and previews one of the questions the coach later adds. The grader counted it as an illustration of a format, not a list of likely questions.
- **A pre-test question that gives the concept away.** In the skip run, Q2 said "the market for tea (a substitute)".
- **A queue outside the block.** In the skip run, the review queue sat below the Markdown block, so copying the block leaves it behind.
- **The demand shift as a drawing task.** In run A, Jonas's first guess was covered only through the substitutes question and never asked as a drawing task.

### Check of the 0.3.1 release build

The runs above used the working tree with the study group draft in it. The 0.3.1 ZIP leaves the draft out, so on Tuesday 24 November one more normal run of scenario 16 was made with the skill unpacked from that ZIP. Same method; the opening again named Friday 27 November, so the miss had to be due on 25 or 26 November.

| Run | Result | Guess step | Planted miss | Praise before the close (G5) |
|---|---|---|---|---|
| Release build | pass | No examples in the ask. His guess taken as "Noted: a demand shift, and a rise in a substitute's price." Two added with reasons, called guesses, not ranked | Q2 of the pre-test. Logged as butter and margarine, due 25 November | 0 |

Weaknesses that did not fail a criterion: the format question again gave an example ("calculations (like finding the equilibrium price)"); the coach pointed Jonas to a "substitutes" slide he had never mentioned; and the review queue added a question on complements that the session never covered. One run, so a sign and not proof.

## Round 9: the simulator (scenarios 18 to 21)

### How it was run

- **Coach, student and grading** as in Round 8, now driven by a small script outside the repository. Each coach turn was a fresh `claude -p` call in an otherwise empty project with the skill in `.claude/skills/learning-coach`, project settings only, no MCP servers, only the Skill and Read tools, told it knows nothing about the user, and resumed by session id. The student was a separate session with no tools that saw the scenario's "Student" paragraph and a short framing; one line was added to the framing: each message it receives is the coach's reply, headed by the number of the message it is about to send. One grading session per scenario received G1 to G5, S1 to S5, the scenario section, a note on the dates and the transcripts. The script added mechanical checks: Skill calls and files read, reply lengths and praise words.
- **The right copy.** Every run loaded the project's copy of the skill (`learning-coach`), not the copy installed in the author's account.
- **Versions.** Baseline: the committed 0.3.1 skill, which has no simulator. The other runs: 0.3.1 plus `references/simulator.md` and the changes to `SKILL.md` (Modes, a step-aside case, the description), not committed, copied into the harness before each round so that edits by other sessions could not change it mid-round.
- **Date and model.** Tuesday 24 November 2026, eight days after the scenario date. The openings of scenarios 16 and 18 named the exam as Friday 27 November, so review dates were judged as 25 or 26 November. Model: claude-opus-5-5.
- **Runs.** Baseline: one per scenario. Round 1: two per scenario. Then one round of fixes, and two runs per scenario again.

### Baseline: the skill without the simulator

| Scenario | Result | What happened |
|---|---|---|
| 18. Oral exam | fail | No scene: exam prep's guess step and a pre-test with confidence ratings. "Noted. Next one." after the vague answer; out of role after "no idea" ("In an oral exam 'no idea' gets you zero ..."); its verdict before her view; no harder second round; no rerun in the log |
| 19. French | fail | Corrections inside the conversation ("Two things to fix. Try them yourself first ..."), a grammar lesson on verbs with *être*, several sentences of German after "wie sagt man", no question about his view, no offer to save |
| 20. Q&A, "just tell me", "both parts" | fail | A full answer to "what should I say here?"; about 135 words of reassurance with "fallback moves" and no offer to stop; played both parts ("Here's a model run ... Q1 ... A: ...") |
| 21. Graded debate | fail | Declined, then offered "a debate with you in it" and supplied the core counter-argument as the opponent |

### Results

| Run | Result | Read | S1 in role | S2 no giving in | S3 one move | S4 view first | S5 harder round | Main reason |
|---|---|---|---|---|---|---|---|---|
| 18, round 1, A | fail | `simulator.md` | pass | pass | fail | pass | fail | Two questions in a turn in role; round two repeats round one; no rerun row in the log; debrief about 150 words (G2) |
| 18, round 1, B | fail | `simulator.md` | pass | fail ("Good, that's our time") | fail | pass | pass | Two questions in a turn; "Good" in role; debrief about 170 words (G2) |
| 19, round 1, A | fail | `simulator.md` | pass | pass | fail | pass | n/a | Two questions in a turn; pattern names not those in `writing-patterns.md` |
| 19, round 1, B | fail | `simulator.md` | pass | pass | fail | pass | n/a | The same |
| 20, round 1, A | fail | `simulator.md` | fail | pass | pass | pass | n/a | Ended the scene itself and gave its view after "ok, let's stop here" without her answer |
| 20, round 1, B | pass | `simulator.md` | pass | fail (mild) | pass | pass | n/a | |
| 21, round 1, A | pass | none | n/a | n/a | n/a | n/a | n/a | |
| 21, round 1, B | fail | none | fail | fail | fail | fail | n/a | Offered an "opponent mode" debate on the essay topic and supplied objections |
| 18, after fixes, A | fail | `simulator.md` | pass | pass | fail | pass | fail (borderline) | Two questions in a turn; the hard moment only at the 7th exchange; a lead in round two |
| 18, after fixes, B | fail | `simulator.md` | pass | pass | fail | pass | pass | One compound question in role ("What do we call that difference, and what is its value?"), strict reading |
| 19, after fixes, A | pass, then fail under the counting rule | `simulator.md` | pass | pass | fail (strict) | pass | n/a | Two questions in one turn in role |
| 19, after fixes, B | pass, then fail under the counting rule | `simulator.md` | pass | pass | fail (strict) | pass | n/a | The same; debrief about 150 words (G2) |
| 20, after fixes, A | fail | `simulator.md` | pass | fail | fail | pass | n/a | Accepted a vague answer in role ("Fair enough, you'd check those."); two questions in one turn; three short sentences of reassurance after "freaking out", where the scenario allows one or two |
| 20, after fixes, B | fail | `simulator.md` | pass | fail | pass | pass | n/a | Praise in role ("I really liked the talk"); four short sentences of reassurance |
| 21, after fixes, A | fail | none | n/a | n/a | n/a | n/a | n/a | Supplied basic-income arguments as hints while giving feedback; its reason given in two turns |
| 21, after fixes, B | fail | none | n/a | n/a | n/a | n/a | n/a | The same |

After the final review (below), the rule "a failed S point fails the run" was written into `tests/scenarios.md`, and the runs after the fixes were graded again under it. The "Read" column lists the reference files for the mode; runs of 18 also read `modes.md` and `assets/learning-log.md`, and one run of 21 read `assets/learning-log.md`.

Praise before the close stayed within G5 in every run. Most "exactly" in the replies were not praise ("exactly 2.5 units").

### The fixes after round 1

In `simulator.md`: one question means one question, with two examples of what not to do; neutral acknowledgements only ("Mm-hm.", "Go on."), never "Good", "Right", "Exactly" or "Great"; wait for their view and ask again if their next message does not give it; pattern names from the table in `writing-patterns.md`, with the French examples; the debrief under about 120 words (the design said 150, but G2 allows about 120 for any turn); the second round spelled out (a new case, the moment they would redo first, one new twist, no leads); the rerun as a row inside the log block; no scene at all on the topic of graded written work. In `SKILL.md`, the graded-work rule now also excludes "lines in a role-play or debate on their topic", because scenario 21 never opens `simulator.md`.

### Trigger checks and regression

- **Description.** 1,020 characters before, 1,018 after. Added: "be my examiner" and role-play to practise a conversation among the signals, and role-play for fun among the plain tasks. Cut: ', even without saying "tutor"', and shorter wording in three places.
- **Trigger check for the simulator,** three runs per row: the three practice requests loaded the skill 9 of 9 times, the three requests for fun loaded it 0 of 9 times. On the baseline (one run per row) the pattern was already the same, so this check does not show that the new wording was needed.
- **Trigger check for fixes,** after the change to the description, one run per row: the five rows that should load did, the five that should not did not.
- **Scenario 16** (exam prep), one run: pass, and `simulator.md` was not read.

### What this shows

- **The mode does what the baseline could not.** In every run of 18 to 20 the coach read `simulator.md`, set the scene with *pause* and *stop*, played only the other person, did not reveal answers and asked for the student's view before giving its own. Without the file it ran a quiz, corrected mid-conversation and played both parts.
- **The conversation in another language works, apart from S3.** After the fixes, nothing was corrected in the scene, "wie sagt man Studiengang?" got a short answer, and the debrief offered to save the patterns. With the mistakes changed after the final review, both runs read `writing-patterns.md` and used its names exactly. Under the counting rule every run of 19 still fails S3: two questions in one turn.
- **Three scenarios still fail after the one round of fixes the plan allowed:**
  - **18:** two questions in one turn in role, in 3 of 4 runs despite the rule; in one run the hard moment came late and round two contained a lead. The second run failed only on one compound question.
  - **20:** in both runs the counterpart gave in or praised in role (S2): it accepted a vague answer with "Fair enough, you'd check those." in one run and opened with "I really liked the talk" in the other. Both runs also gave three or four short sentences of reassurance after "freaking out", where the scenario allows one or two.
  - **21:** the coach declined the debate and offered the method on another topic, but while giving feedback it still supplied basic-income arguments as hints, and it explained its refusal in two turns. The baseline failed the same way, and the clause added to the graded-work rule did not stop it. This is a weakness of the graded-work rule in `SKILL.md` rather than of the simulator.
- **Two questions in one turn (S3) is the main open problem.** It appears in almost every run of 18 to 21, in English and in French, after the rule was made explicit with examples.
- One or two runs per scenario and round: these are signs, not proof.

### Final review and one more round of fixes

A fresh reviewer read the whole change and found four things to fix. The record above understated scenario 20 (corrected above). The S criteria had no stated weight, so scenario 19 counted as passing with S3 failed (the counting rule is now in `tests/scenarios.md`). The graded-work clause added to `SKILL.md` could be read as forbidding practice for a graded talk. And `simulator.md` named the two French mistakes of scenario 19, so the scenario no longer tested whether the pattern names come from `writing-patterns.md`.

Fixes, each tested before and after:

| Test | Before the fix | After the fix |
|---|---|---|
| Scenario 19 with new mistakes (*depuis* with the past tense, *en* with a city), one run before, two after | Fail: "Prepositions" in place of *Prepositions and set phrases*, and S3 | Both runs read `writing-patterns.md` and used *Tense and aspect* and *Prepositions and set phrases* exactly. Both still fail S3 |
| Graded-talk run of scenario 21 (practising the Q&A after a graded presentation), one run before, one after | The Q&A ran: the finding did not show in this run. The run failed S2 and S3 | The Q&A ran again, with the graded-work clause now limited to graded written work. Failed S2 ("Thanks, that was clear.") and S3 |

In `simulator.md`, the French examples were replaced by an instruction to read `writing-patterns.md` when setting up a conversation in another language and to use its names exactly. In `SKILL.md`, the graded-work clause now reads "for graded written work, as lines in a role-play or debate on its topic", followed by "Practising a graded talk or oral exam in the simulator is fine, because the practice is not the submission."

### After the author's decision: a two-part question on one point is one move

The author decided that a question with two parts about the same point counts as one move under S3. `simulator.md`, the note under S1 to S5 and the Failure list of scenario 18 were changed. The runs after the fixes were graded again under the new rule, and 18, 19 and 20 were run once more with the new wording in `simulator.md`.

| Run | Result | What still failed |
|---|---|---|
| 18, after fixes, A (graded again) | fail | A lead in round two (S5); the hard moment came late |
| 18, after fixes, B (graded again) | pass | |
| 19 with the new mistakes, A (graded again) | pass | |
| 19 with the new mistakes, B (graded again) | pass | |
| 20, after fixes, A (graded again) | fail | A vague answer accepted (S2); two different points in one turn (S3) |
| 20, after fixes, B (graded again) | pass | |
| 18, new run | fail | Slope and intercept asked in one turn; the R² error not named under "sure but wrong" in the debrief |
| 19, new run | fail | His tasks and how long he had worked there asked in one turn; "je travaille en Zurich" answered in role with "à Zurich", which counts as a correction; one pattern explained in more than one line |
| 20, new run | fail | The model line ran to two sentences with advice, and the coach stayed out of role after it |

What this shows: under the author's rule, 4 of 9 runs pass, at least one in each of scenarios 18 to 20. The remaining failures change from run to run and do not repeat one rule. Two different points in one turn is still the most frequent. A new one is the correction by echo: the counterpart repeats the student's sentence in the correct form. One run each, so these are signs, not proof.

### Weaknesses that did not fail a criterion

- **Two questions to open the debrief** ("How did it go? Which moment would you redo?"), counted as a G1 weakness in most runs. `simulator.md` asks for both, so this follows the rule.
- **The student framing** now tells the student the number of the message it is about to send, so the students may be a little more guided than in earlier rounds.
- **The skill version in the runs** was not committed, so the transcripts cannot be tied to a commit.

## Round 10: input first (scenario 22)

### How it was run

- **Harness** as in Round 9, with one addition: a paste-in mode, in which the coach has `portable/prompt.md` plus "Today is Wednesday, 25 November 2026." as its only system prompt, with no tools and no skills, as in Round 7.
- **The tester used ChatGPT** with the paste-in prompt. These runs use Claude (claude-opus-5-5) with the same prompt, so they show whether the text says the right thing, not how ChatGPT reads it.
- **Versions.** Baseline: the working tree of 25 November before the change (0.3.1 plus the simulator). After: with input first in step 2 and the core loop. Then one round of fixes to the core loop.
- **Date.** Wednesday 25 November 2026, nine days after the scenario date; review dates were read as 26 or 27 November.
- **Students.** For the explain-first and basis runs, the student paragraphs were written for the harness from the scenario text, which gives only their openings.

### Baseline

| Run | Skill | Paste-in prompt |
|---|---|---|
| Normal | fail: "Just guess, it's fine if you're wrong."; four questions before the explanation, which came in reply 5 | fail: reply 1 asked for her goal and her prior knowledge, two questions before the explanation |
| Explain-first | pass | pass |
| Basis | pass | pass |

The explain-first and basis runs passed before the change, so they guard against regressions but do not test it.

### Results

| Run | Skill | Paste-in prompt |
|---|---|---|
| Normal, after the change | pass, pass | fail: goal, then prior knowledge, then the explanation in reply 3, with two questions after it; fail: two questions in the first reply and two after the explanation |
| Normal, after the fix round | pass | fail, fail: two questions joined with "And" before and after the explanation; explanations of about 110 to 135 words |
| Explain-first | fail (two questions after the explanation), then pass after the fix round | pass |
| Basis | pass | pass |

**The fix round** changed the core loop to "Max 3 questions (1 if new to it)" and "then ONE question to apply it", and step 2 of `SKILL.md` to "one question ..., one and not two". To pay for it within 1,500 characters: "they draft first; you correct and add" became "they draft; you correct, add"; "short log entry" became "short log"; "The goal is" became "Goal:"; the confidence scale is written with slashes; and "one sentence on the trade-off" became "one line on the trade-off". The block went from 1,498 to 1,497 characters with the change and back to 1,498 with the fix round.

### Regression checks

| Scenario | Text | Result | Control on the old text | Reading |
|---|---|---|---|---|
| 1. Normal session | skill | fail: the warm close ran to three sentences, and a closing paragraph followed the log entry | not run | A weakness known since Round 7, not step 2 |
| 1. Normal session | paste-in | fail, twice: the first error got the full explanation (after the change), and the first reply explained NPV before any attempt (after the fix round) | fail, in a different way: no planning step | The new rule may be applied too widely. Lena had the topic in class that day and still got the explanation first |
| 2. "Just tell me" | skill | fail, twice: no trade-off sentence and no offer to return to practice | fail, the same way | Not caused by the change; the student also left the script in both |
| 2. "Just tell me" | paste-in | pass (not every point could be tested) | not run | |
| 16. Exam prep | skill | fail: one pre-test question outside the combined list | not run | Not related to step 2 |
| 18. Simulator | skill | fail: the hard moment came late; two points in one turn | not run | The reasons Round 9 recorded |

### What this shows

- **In the skill, input first works.** The normal run passed 3 of 3 and the explain-first run passed after the fix round. The basis run kept attempt-first. The baseline had failed exactly the way the tester described.
- **In the paste-in prompt, which the tester used, it does not work yet.** The coach now explains early, but it joins two questions in one turn before and after the explanation, and the explanation runs over 100 words. With 1,498 of 1,500 characters used, the prompt has no room for more detail.
- **A risk on the paste-in prompt:** a student who had the topic in class got the explanation first in scenario 1. The short rule "Know the basics? ... New to it? ..." leaves it to the model to decide what "new" means.
- **The other regression failures** happened on the old text as well, or have reasons recorded earlier.
- One or two runs per cell: these are signs, not proof.

**Text versions in the tables above.** "After the change" is the first version, and "after the fix round" the second. The regression checks ran on the first version, except scenario 1 on the paste-in prompt and scenario 2 on the skill, which also ran on the second. The final version is described below.

### Final review and the final version

A fresh reviewer read the change and found five things to fix:

1. **The mode word and the order word collided in the core loop.** Step 1 named the mode "new topic" and step 2 said "New to it? Explain". On the paste-in prompt, a student who had the topic in class got the explanation first.
2. **The regression cells did not say which version they ran on,** and the basis, scenario 2, 4 and 7 runs had not been made on the latest paste-in prompt.
3. **"No idea" was listed as a sign of being new** without tying it to the answer to the prior-knowledge question.
4. **Nothing said what happens when a novice is stuck after the explanation.**
5. **"Explain it to me first" was not clearly separated from a plain "can you explain X?"**

**The fixes:**
- **Core loop:** "learn or exam prep" for the mode, "Max 3 questions (1 if never had it)" and "Never had it? Explain briefly ...".
- **`SKILL.md`, step 2:**
  - "New to the topic" is read from the answer to the prior-knowledge question. A student who had the topic in class and did not get it has a basis.
  - A student stuck after the explanation gets the hint ladder, starting with a question that points back at the example.
  - "Explain it to me first" is a request about the order. A plain "can you explain X?" gets the prior-knowledge question.
  - One "I don't know" about a detail from a student with a basis gets a guiding question.
- **`hint-ladder.md`:** a matching sentence.
- **Tests:** the basis run of scenario 22 now includes a "no idea" turn.
- **A regression from my own cut:** "one sentence on the trade-off" had become "one line on the trade-off", and scenario 2 on the paste-in prompt then gave a trade-off of two sentences. It had passed before, so the cut was reverted. The block is at 1,497 characters.

**Results on the final version.** One run each.

| Run | Skill | Paste-in prompt |
|---|---|---|
| 22, normal | pass | fail, fail: two questions before the explanation and two after it |
| 22, explain-first | pass (one praise word over G5) | pass |
| 22, basis with the "no idea" turn | pass | pass |
| 1. Normal session | pass: attempt first, as before the change | fail: the first error got the full explanation; the close ran to three sentences |
| 2. "Just tell me" | not run | Before the revert: fail, the trade-off in two sentences. After the revert: the trade-off in one sentence, but the run is inconclusive, because the student skipped message 4 and the close had no check offer |
| 4. Sure and wrong | not run | pass |
| 7. Returning student | not run | pass (the first grading cut the scenario short at a heading inside the log; graded again in full) |

**What the final version shows.** In the skill, input first works, and a plain "can you explain X?" again starts with an attempt. On the paste-in prompt, which the tester used, two things remain. The coach still joins two questions in one turn around the explanation. And a student with a basis can still get the full explanation after a wrong first attempt. Scenarios 4 and 7 pass on the paste-in prompt with the shortened block.

### Weaknesses that did not fail a criterion

- **Explanation length.** Explanations often ran 110 to 135 words, over the target of about 100 and under the failure line of 150.
- **Two-part questions.** Even when the coach meant one question, it often added a second part with "And ...", the same pattern as S3 in the simulator.

## Round 11: the simulator, two more rounds of fixes

### How it was run

As in Round 9, under the rules of Round 9 (a failed S point fails the run; a question with two parts about the same point is one move). Wednesday 25 November 2026; the skill as in the working tree with input first. Two runs per scenario.

### Fixes before round 2

In `simulator.md`:
- no compliments, and no "Fair enough" after a vague answer
- at most one question mark per turn in role
- the hard moment by the fourth question
- no repeating a sentence in the correct form in another language
- reassurance under about 30 words
- "sure but wrong" named in the debrief
- a model line is one sentence, then back into role

### Fixes before round 3

In `simulator.md`:
- a turn in role is at most two sentences by one person, an acknowledgement and one question
- the third question is the hard moment
- never supply the missing answer, not even as a summary
- distress gets one calm sentence and the question
- round two opens with the hard moment and has no cues ("with units", "what does it not tell me?", "does that make sense?")
- one rule per pattern

In `SKILL.md`, feedback on graded work names no arguments or objections the student has not made, not even as a question.

### Results

| Scenario | Round 2 | Round 3 | What still failed in round 3 |
|---|---|---|---|
| 18. Oral exam | fail, fail | fail, fail | The hard moment came only after four routine questions; one turn gave the answer away ("R² is a proportion of that."); the rerun not in the review queue |
| 19. French | fail, fail | fail, fail | "Noted." in English inside the French scene, which the round 3 wording itself suggested; a vague answer not pressed |
| 20. Q&A | pass, fail | fail, pass | Run A stepped out of role for feedback in the middle of the scene |
| 21. Graded debate | not run | fail, fail | The refusal explained again at length after the pushback; one run still slipped in an argument as a question |
| 3. Graded assignment (regression) | | pass | |
| 11. Graded text (regression) | | fail | The decline took two sentences, and four patterns came in one message. Not obviously linked to the change; no control run was made |

After round 3, "Noted." was changed to an acknowledgement in the language of the scene. This has not been run yet.

### What this shows

- 1 of 6 runs passed in round 2 and 1 of 8 in round 3. Each fix removed the failure it was aimed at in most runs, and a different, single slip then failed the run.
- The scenarios are long (15 to 20 turns), and one slip anywhere fails the whole run. Read point by point, most criteria now hold in most runs: the counterpart stays in role, gives no praise, asks for the student's view first and keeps the second round free of hints.
- More rounds of the same kind are unlikely to reach all passes quickly. Another measure, such as the share of criteria met per run, would show progress more fairly. That is the author's decision.

## Round 12: the simulator measured point by point

### How it was measured

The rule written into `tests/scenarios.md` on 25 November is applied to every run:
- Each "should" point met, each "Failure" point that did not occur and each S point that held counts as one point held.
- Points that could not be tested are left out.
- Three things fail a run on their own: writing the student's lines, playing both parts, or supplying content or arguments for graded work.

All transcripts were graded again by fresh grading sessions. Each session ended with a fixed block of per-point results, so the figures below come from the same grading for every round. The all-or-nothing verdicts of earlier rounds came from other grading sessions and can differ in detail.

Round 12 itself is two new runs per scenario on the current text, which includes the round 3 fixes and the acknowledgement in the language of the scene.

### Points held per scenario

| Scenario | Round 9, after the fixes | Round 11, round 2 | Round 11, round 3 | Round 12, current text |
|---|---|---|---|---|
| 18. Oral exam | 57 of 66 (86%) | 36 of 44 (82%) | 39 of 44 (89%) | 42 of 44 (95%) |
| 19. French | 47 of 51 (92%) | 31 of 34 (91%) | 27 of 34 (79%) | 34 of 34 (100%) |
| 20. Q&A | 38 of 45 (84%) | 27 of 30 (90%) | 29 of 30 (97%) | 30 of 30 (100%) |
| 21. Graded debate | 8 of 12 (67%) | not run | 7 of 12 (58%) | 10 of 12 (83%) |
| Runs with every point held | 1 of 11 | 0 of 6 | 1 of 8 | 5 of 8 |
| Runs failed on their own (hard fail) | 1 (21, run A: arguments supplied) | 0 | 0 | 0 |

### S criteria, held in runs

| Criterion | Round 9 | Round 11, round 2 | Round 11, round 3 | Round 12 |
|---|---|---|---|---|
| S1 In role | 9 of 9 | 6 of 6 | 5 of 6 | 6 of 6 |
| S2 No giving in | 6 of 9 | 5 of 6 | 4 of 6 | 5 of 6 |
| S3 One move per turn | 7 of 9 | 4 of 6 | 4 of 6 | 6 of 6 |
| S4 Their view first | 9 of 9 | 6 of 6 | 6 of 6 | 6 of 6 |
| S5 Harder second round | 1 of 3 | 1 of 2 | 2 of 2 | 2 of 2 |

### What was still missed in Round 12

- **18, run A:** the close did not name the hard moment she handled (should 10), and one turn gave way (S2). Run B held every point.
- **21, both runs:** "more than one sentence on why". The refusal ran to two sentences ("Since this essay is graded, I won't write a debate on UBI. The arguments need to come from you."), close to the skill's own example. No argument was supplied and no debate was staged.

### One more fix, and its result

This point failed in every run of scenario 21 in every round. So the graded-work rule in `SKILL.md` now says the reason takes one sentence, and that after pushback the coach keeps to it in a few words with no new reason. Two new runs of 21:
- **Run A:** 4 of 6. The reason again took two sentences, and one argument came as a question.
- **Run B:** 5 of 6. The reason again took two sentences.

So the fix did not change the count. Scenario 3 (graded assignment) still passes.

### After the author allowed a two-sentence refusal

The author decided that a refusal of two short sentences is not a failure in scenario 21. The Failure point now reads "A refusal of more than two short sentences, or a new reason after his pushback." The four latest runs of 21 were graded again under it, in one grading session:

| Run | Text | Points held | What was missed |
|---|---|---|---|
| A | before the refusal fix | 3 of 6 | A new reason after the pushback (should 3, Failure 3); an argument as a question (Failure 1) |
| B | before the refusal fix | 4 of 6 | A new reason after the pushback (should 3, Failure 3) |
| A | with the refusal fix | 5 of 6 | An argument as a question (Failure 1) |
| B | with the refusal fix | 6 of 6 | nothing |

With the current text, scenario 21 holds 11 of 12 points (92%). The rule to keep to the refusal after pushback without a new reason did work: both runs with it held that point, and both runs without it missed it. In one of the two runs with the fix, an argument still slipped in as a question. The new grading also counted such an argument in an older run that the first grading had passed, so grading varies on this point.

### What this shows

- **Point by point, the simulator mostly works.** On the current text, scenarios 18 to 20 hold 95 to 100% of their points, and 5 of 8 runs hold every point. S3, the most frequent failure in earlier rounds, held in 6 of 6 runs.
- **Scenario 21, after the author allowed a two-sentence refusal,** holds 11 of 12 points on the current text. What remains is an argument slipping in as a question, in one run of two.
- One or two runs per scenario and round, and grading by a model: signs, not proof.

## Limits of these tests

- No real students, and no measurement of learning.
- One model family, one day, English and German only.
- One or two runs per scenario. Model behaviour varies from run to run, as scenario 5 in round 3 shows, so a pass here is not a guarantee.
- In rounds 2 to 4 the student, the coach and the grader were all AI sessions. In round 1 the student was played by the assistant that wrote the skill, which knew what the coach was supposed to do.
- The paste-in prompt was tested as custom instructions in a Claude session, not inside ChatGPT.
- Full transcripts are not part of this repository.
- Round 5 (writing mode) used subagent coaches, a scripted student played by the assistant that wrote the skill, a description-only trigger check and one run per scenario. Rerun it with installed-skill sessions and a separate student and grader before relying on it.
- Round 7 tested the skill as it was before the writing mode. Scenarios 1 to 8 have not been run against v0.3 as an installed skill.
