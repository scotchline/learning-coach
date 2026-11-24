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

## Limits of these tests

- No real students, and no measurement of learning.
- One model family, one day, English and German only.
- One or two runs per scenario. Model behaviour varies from run to run, as scenario 5 in round 3 shows, so a pass here is not a guarantee.
- In rounds 2 to 4 the student, the coach and the grader were all AI sessions. In round 1 the student was played by the assistant that wrote the skill, which knew what the coach was supposed to do.
- The paste-in prompt was tested as custom instructions in a Claude session, not inside ChatGPT.
- Full transcripts are not part of this repository.
- Round 5 (writing mode) used subagent coaches, a scripted student played by the assistant that wrote the skill, a description-only trigger check and one run per scenario. Rerun it with installed-skill sessions and a separate student and grader before relying on it.
- Round 7 tested the skill as it was before the writing mode. Scenarios 1 to 8 have not been run against v0.3 as an installed skill.
