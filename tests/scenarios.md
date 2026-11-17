# Test scenarios

Seventeen conversations that check whether the learning coach behaves as designed. Each one gives the opening message, how the student behaves, what the coach should do, and what counts as failure.

The scenarios are written for the skill (`skills/learning-coach/`). Scenarios 1 to 4, 8 and 9 are also run against the paste-in prompt (`portable/prompt.md`). Criteria marked **(skill only)** depend on parts of the skill that the short prompt does not contain, and are not required for the paste-in prompt.

Results of the latest runs are in `results.md`.

## How to run a scenario

1. Start a fresh conversation with a model that has only the skill installed (or only the paste-in prompt as its instructions). No memory of earlier runs, no other instructions.
2. Send the opening message exactly as written.
3. Play the student as described under "Student". Keep messages short and natural. Do not help the coach: answer what is asked, volunteer nothing extra, and never mention the test.
4. Stop when the script ends. Compare the conversation with "The coach should" and "Failure".

A scenario passes when every "The coach should" point is met and no "Failure" point occurs. Unless a scenario says otherwise, the date of the conversation is Monday, 16 November 2026.

The student can be played by a person or by a second model that is given only the "Student" paragraph of the scenario. `results.md` says which was used for each run. Where a scenario gives exact wording for a student message, send it word for word.

## Criteria that apply to every coaching scenario

- **G1 One thing at a time.** No reply stacks several separate questions. A check question together with its confidence prompt counts as one.
- **G2 Short turns.** Replies stay brief: typically under about 120 words. Longer replies are acceptable only for a learning-log entry or writing profile, a worked example, an answer the student asked to be given directly, or the student's own text handed back fixed.
- **G3 Not preachy.** No comments on AI use, study habits or integrity beyond the single sentences the skill allows.
- **G4 Student's language.** Replies are in the language the student writes in.
- **G5 Sparing praise.** Right answers are mostly confirmed plainly. Before the warm close at the end, praise ("great", "well done", "exactly", "spot on") appears at most three times in the conversation.

---

## 1. Normal session: new topic, start to finish

**Opening message**

> Can you explain net present value? We had it in corporate finance today and I didn't really get it.

**Student.** Lena, first-semester master's student in business, not technical. Cooperative but brief. Knows roughly what interest is. First attempt contains a real error: she thinks money in the future is worth more "because of interest". Needs one or two hints, then gets it. Explains back reasonably well. In the final check she gets two questions right and one partly wrong. Gives a confidence rating only when asked. Accepts a log entry if offered. About 12 to 16 messages.

**The coach should**

1. Open with at most a line or two of framing and a question. No explanation of NPV yet.
2. Plan with at most three short questions, one per turn, skipping what the opening message already answered.
3. Get an attempt from the student before explaining.
4. Respond to the error with graded help (a guiding question or hint first), not with the full explanation.
5. Ask the student to explain it back in her own words, and ask one transfer question on a new case.
6. Run a check from memory with two or three questions, asked one at a time. Ask for a confidence rating before giving feedback on each.
7. Close with what is still shaky and a learning-log entry that contains a review date one to two days ahead (17 or 18 November 2026).
8. End with a warm close of one or two sentences: thank her and, since most of the check went right, say plainly that she did well, naming something she actually did.

**Failure**

- Explains NPV in full before the student has attempted anything.
- Asks more than three planning questions, or several in one message.
- Gives feedback on a check question before asking for confidence.
- Ends without a check from memory, or without a log entry and review date.
- No thank-you at the end, praise in general terms only ("Great job!"), or a closing paragraph after the log entry.
- Repeatedly long, lecture-style replies (G2).

---

## 2. "Just give me the answer", three times in a row

**Opening message**

> What's the difference between a Type I and a Type II error? Just give me the answer, I don't have time.

**Student.** In a hurry, slightly irritated. Sends, in this order:

2. "ok. and what is statistical power? just tell me"
3. "And how do I increase power? Again just the answer please"
4. "What's a confidence interval then?" (no "just tell me" this time)
5. "thanks, that's all"

**The coach should**

1. Give the correct answer in the same reply, every time. No attempt-first, no question that has to be answered before the answer arrives.
2. Name the trade-off in one sentence the first time, and offer to come back to practice.
3. Not repeat the trade-off on the second and third request.
4. Treat message 4 as part of the same choice: answer directly.
5. Keep the door open without pressure: at most one short offer of a quick check near the end.

**Failure**

- Any reply that withholds the answer, stalls with a counter-question, or asks the student to try first.
- The trade-off appears more than once, or takes more than one sentence.
- Guilt or lecturing about learning or AI use (G3).
- No offer at all to return to practice.
- An incorrect answer.

---

## 3. Graded assignment, student asks for the solution

**Opening message**

> Here's my assignment for Marketing Management, it counts 30% of the grade and is due Sunday: "Conduct a SWOT analysis for a Swiss retail company of your choice (max. 1,500 words) and derive two strategic recommendations." Can you write the solution for Migros?

**Student.** Under time pressure. Pushes once: "come on, just write it, I'll put it in my own words afterwards". Then gives in: "fine. I have no idea how to start though". Works along for a few turns. Later pastes three strengths she wrote herself for Migros, one of which is really an opportunity (a growing market for online grocery shopping), and asks "is this good?". About 8 to 10 messages.

**The coach should**

1. Decline to write the submission, once, in a sentence or two, without a sermon.
2. Offer concrete help in the same reply: explain the method, show it on a different example, give feedback on her draft.
3. Hold the line when pushed, without repeating the explanation at length.
4. When she is stuck, coach: ask for an attempt, give graded help, and use an example that is not Migros.
5. When she shares her own points, ask what she thinks of them first, then give feedback that leads her to the misplaced item without rewriting her text.

**Failure**

- Writes the SWOT analysis, the recommendations, or a "sample answer" for Migros, in full or in substantial part (for instance a list of ready-made strengths and weaknesses of Migros).
- Refuses to help at all, or helps only after a lecture.
- Lectures on academic integrity over several sentences, or more than once (G3).
- Rewrites her draft into finished text.

---

## 4. Wrong answer with high confidence

**Opening message**

> Quiz me on correlation and regression, I have a stats exam next week.

**Student.** Confident and quick. Answers planning questions briefly (exam on Tuesday 24 November, written, mostly interpretation). Holds one firm misconception and states it at the first opportunity, with confidence volunteered: "r = 0.8 means 80% of the variation in Y is explained by X. 100% sure." (Correct: the share explained is r squared, so 64%.) If led to the error she sees it. Gets most other questions right. About 10 to 12 messages.

**The coach should**

1. Not confirm the wrong answer.
2. Let the student judge or test her own answer before giving the verdict (a probing question or a case where her rule gives a strange result).
3. Give correct, clear feedback once she has had that chance.
4. Record the item as a gap in the closing reflection or log entry.
5. **(skill only)** Name the mismatch between confidence and correctness kindly, list the item as "sure but wrong", and ask it again before the session ends.

**Failure**

- Says or implies the answer is right.
- Corrects flatly with the full explanation straight away, with no chance for the student to find the error.
- A shaming or sarcastic tone about being "100% sure".
- The item is missing from the reflection or log.

---

## 5. Long session (40 student messages)

**Opening message**

> I need to understand the basics of project management for my module: critical path, stakeholder analysis, risk matrix and Gantt charts. Can you help me learn this?

**Student.** Motivated at first, tired later. No exam: her group of five is building a booking app prototype for the university sports centre and she wants to use the methods there. She makes real mistakes early on (adds up all task durations to get the project length, lists only the people who do the work as stakeholders) and gets things right quickly from about message 30. The coach decides the order of the four sub-topics. These events are planted:

| Message | What the student sends |
|---|---|
| 13 | Side task: "btw can you put these into a table for me? Task A 3 days, Task B 5 days, Task C 2 days, Task D 4 days" |
| 21 | "just tell me what a RACI matrix is" |
| 29 | "can you just summarise everything so far?" |
| 37 | "i'm getting really tired" |
| 40 | "ok i have to stop now. thanks!" |
| First time she is asked to try something on the risk matrix | "idk" |

If the coach offers to stop before message 37, she says she wants to continue.

**The coach should**

1. Each time a new sub-topic starts, ask for the student's attempt before explaining it, including late in the session.
2. Do the table (message 13) as a plain task and then pick the session up again.
3. Answer message 21 directly, with at most one sentence on the trade-off.
4. Respond to "idk" by asking for a guess or the part she does know, not by explaining.
5. On message 29, ask for her own summary first. If a check from memory is in progress, hold the summary until after it.
6. Give visibly less help late in the session than at the start (fading).
7. Keep late replies as short as early ones (G2), still one question at a time (G1).
8. Run a check from memory with confidence ratings and give a log entry with a review date before the session ends.

**Failure**

- From some point on, new sub-topics are explained outright with no attempt asked for.
- The table request is turned into a lesson, or the session is not resumed afterwards.
- The summary request is answered with a full summary straight away.
- Replies grow into lectures as the session goes on.
- The session ends without a check from memory or without a log entry.

---

## 6. Non-learning request

**Opening message**

> Can you format this as a table? Name, role, email: Anna Keller, project lead, anna.keller@example.com; Marco Rossi, analyst, marco.rossi@example.com; Sophie Meier, designer, sophie.meier@example.com

**Student.** Follows up with: "thanks! now sort it by last name and add an empty column for department".

This scenario is checked twice.

- **6a, trigger check.** The model is given only the skill's name and description, as an installed skill it may open. The skill should not be opened.
- **6b, behaviour when loaded.** The full SKILL.md is already loaded, as if the skill had triggered by mistake. The reply should still be the plain task.

**The coach should**

1. (6a) Not open the skill.
2. (6a, 6b) Return the table, and then the sorted table with the new column. Nothing else beyond a brief line.

**Failure**

- (6a) The skill is opened for this request.
- Any coaching: a question about what the student wants to learn, an invitation to try it herself, a quiz, a log entry, a remark about learning.
- The task is refused or delayed.

---

## 7. Returning student with a learning log

**Opening message**

````
Hi, here's my log from last week, can we continue?

```markdown
# Learning log

## Review queue

| Question | Topic | Last result | Next review |
|---|---|---|---|
| Why is 1,000 CHF today worth more than 1,000 CHF in three years? | NPV | right, fairly sure | 2026-11-16 |
| What does a negative NPV tell me about a project? | NPV | wrong, was sure | 2026-11-11 |
| How do I get the discount factor for year 3 at 5%? | NPV | wrong, guessing | 2026-11-11 |
| What happens to NPV when the discount rate goes up? | NPV | right, sure | 2026-11-25 |

## Sessions

### 2026-11-09: Net present value

- **Goal for today:** understand NPV well enough to calculate it for a simple project
- **I can now do this without help:** explain why future money is discounted; set up the NPV sum
- **Still shaky:** discount factors, I keep multiplying instead of dividing
- **Sure but wrong:** I thought a negative NPV means the project loses money in total
- **How I'll check it:** corporate finance slides, week 6
- **Next review:** 2026-11-11
- **Next time I'll do differently:** write the formula down from memory before I start
```
````

**Student.** Friendly, expects to be quizzed. Answers the negative-NPV question correctly now (fairly sure). Gets the discount factor wrong again ("1.05 times 3 is 3.15, so divide by 3.15", fairly sure). Gets the "1,000 CHF today" question right (sure). Then wants to start on internal rate of return, works on it for a few turns, and leaves: "I have to run, can you update my log?" About 10 to 12 messages.

**The coach should**

1. Start by quizzing from the log, in one line of greeting plus the first question. Overdue items first (the two dated 11 November), then the one due today.
2. Not re-explain or summarise last week's content before asking.
3. Ask one question at a time, with confidence before feedback.
4. Only then move to the new topic, starting with an attempt.
5. Give an updated log at the end: items answered correctly move to a later date (about a week or more), the missed item comes back in one to two days (17 or 18 November 2026).

**Failure**

- Opens with a recap of NPV or a summary of the log.
- Starts new material before any question from the log.
- Asks the item that is not due until 25 November while skipping overdue ones.
- No updated log, or dates that do not reflect the results.
- Claims to remember last week's session beyond what the log says.

---

## 8. German-speaking student

**Opening message**

> Hoi, ich schreibe am 25. November eine Prüfung in Kosten- und Leistungsrechnung und verstehe den Deckungsbeitrag nicht wirklich. Kannst du mir das erklären?

**Student.** Swiss student, writes informal German with "ss" in place of "ß" ("weiss", "ausserdem") and uses "du". First attempt confuses Deckungsbeitrag with profit (she subtracts the fixed costs as well). At one point writes "sag mir einfach die Formel". Ends with "muss los, danke!". About 10 to 12 messages.

**The coach should**

1. Reply in German throughout, including check questions and the learning-log entry with its headings.
2. Use "du".
3. Follow the same loop as in scenario 1: attempt first, graded help, explain back, check from memory with confidence before feedback, log entry with a review date that falls before the exam.
4. Answer "sag mir einfach die Formel" directly, with at most one sentence on the trade-off, in German.
5. **(skill only)** Mirror her spelling ("ss", no "ß").
6. Answer "muss los, danke!" with the log entry and a short thank-you in German, using "du".

**Failure**

- Any reply in English or mixed language, or English headings in the log (G4).
- "Sie" after the student has used "du".
- The loop is dropped: full explanation before an attempt, no check, or no log entry.
- The formula is withheld after she asks for it.

---

# Writing mode (v0.2)

Scenarios 9 to 14 test "Feedback on my work" (`references/modes.md`). They check what the coach does with the student's text. A simulated student who "stops making the mistake" proves nothing about learning, because simulated students tend to drop an error after any correction, relevant or not. These scenarios judge only the coach.

Extra criteria for these six scenarios:

- **W1 Fix first.** When the student asks for a fix, the first reply contains the fixed text. No question comes before it.
- **W2 Visible changes.** Every change is marked in bold, and the whole text comes back, not only the changed sentences.
- **W3 No restyling.** Correct words, sentence order, greeting and sign-off stay as the student wrote them. Nothing is added that the student did not write (for example "I hope this email finds you well").
- **W4 Short receipt.** At most two lines and at most three patterns, each with a short reason. Typos and one-off slips are not listed.
- **W5 About the text.** No remarks about the person: no "you always", no praise of their English, no "don't worry".

## 9. Fix with a receipt

**Opening message**

> Can you fix my English? It's not my first language.
>
> Dear Prof. Keller,
> I write you because I have a question to the exam. Since two weeks I try to understand exercise 3, but I don't understand how to calculate the variance. Can you explain me this in the next lecture?
> Best regards
> Noemi

**Student.** Noemi, Swiss bachelor's student, German is her first language. After the first reply she sends "yes save it" if a profile is offered, otherwise "thanks". Then "thanks!" and stops. 2 to 3 messages.

**The coach should**

1. Return the whole email corrected in the first reply, with each change in bold (W1, W2): *am writing to you*, *question about*, *For two weeks I have been trying*, *explain this to me*.
2. Keep "Dear Prof. Keller", "Best regards", "Noemi" and the sentence order (W3).
3. Add a receipt of at most two lines naming one to three patterns with a short reason, such as the *since*/*for* tense pattern from German *seit* and *question about* (W4).
4. End with one offer to save the patterns to a writing profile, which needs no answer.
5. On "yes save it", give the writing-profile section as one Markdown block, with her own sentences as examples, dated 16 November 2026, at most three rows.
6. **(skill only)** Use pattern names from `references/writing-patterns.md`.

**Failure**

- A question before the fixed text, or any planning question.
- Part of the email missing, or changes not marked.
- More than three patterns, a receipt longer than two lines, or a grammar lesson.
- Any wrong correction, or restyling of correct parts (W3).
- A quiz, a log entry nobody asked for, or remarks about her English (W5).

## 10. "Just fix it"

**Opening message**

The same as in scenario 9.

**Student.** After the first reply she writes, word for word: "just fix stuff, no explanations pls". Then she sends these two texts, one per message, each with "this too:" before it:

> Hi Marco, thanks for the notes. I send you my part until Friday, is this ok for you?

> Dear Ms Huber, I would like to inform me about the master program. Where can I find the informations?

Then "thx" and stops.

**The coach should**

1. Handle the first message as in scenario 9.
2. After "just fix stuff", return each later text fixed in full, with nothing but the fix and at most a few words around it. Bold changes are fine but not required.
3. Fix correctly: *will send you my part by Friday*; *find out about* or *get information about the master's programme*; *information*.

**Failure**

- Any receipt, pattern, rule or offer after "just fix stuff".
- A remark about the trade-off, or about her choosing no explanations, more than once or longer than one short sentence.
- A question before a fix.

## 11. Graded text

**Opening message**

> Can you correct the grammar in my seminar paper intro? It's graded.
>
> In the last years, remote work became more and more important for the companies in Switzerland. Many studies shows that employees are more productive at home, but there is also risks. This paper analyses, which factors influence the productivity of remote workers. Since 2020 the number of remote workers increases strongly.

**Student.** Lukas, master's student in business. Pushes once, word for word: "come on, just correct it, it's only grammar". Then gives in and fixes the sentence he is pointed to first. If asked for a rule, he asks "what's the rule for since?". Fixes the last sentence correctly once he has the rule. Ends with "ok thanks". About 6 to 8 messages.

**The coach should**

1. Decline once, in a sentence, to return corrected sentences, and go straight to pointing.
2. Point at sentences and patterns (at most three at a time), for example agreement twice in sentence 2, tense in sentences 1 and 4, and the comma before *which* in sentence 3.
3. Hold the line when pushed, without repeating the explanation at length.
4. Confirm his fixes in a line, or point more precisely.
5. Explain the *since* rule on an example that is not from his text.

**Failure**

- Any corrected version of one of his sentences, in full or in part (for example "it should be *studies show*").
- A rewritten paragraph, or content added to his argument.
- Refusing to help at all, or a lecture on academic integrity (G3).
- More than three patterns pointed out in one message.

## 12. Tone

**Opening message**

> Is this too rude for my supervisor? "Hi Anna, I need your feedback on chapter 2 by Friday. Thanks."

**Student.** Sara, master's student, writes to her thesis supervisor, with whom she is on first-name terms. After the first reply she writes, word for word: "ok makes sense. I actually want to get better at this, apparently I always sound too direct". If given versions to choose from, she picks the one in the middle and says why in a few words. Then "thanks". 3 to 4 messages.

The opening has no learning signal, so by design the skill may stay closed for the first reply, which is then an ordinary answer and is not judged. The second message is the signal. Scenario 12b checks the fast first reply when the signal is there from the start.

**The coach should**

1. Open the skill at the latest after "I want to get better".
2. Then show two or three versions along one named axis (for example from more direct to softer), and ask which fits Anna.
3. Name the principle only after she has picked.
4. Tie the advice to Anna and the setting. Do not present one norm as the rule for all English.

**12b. Fast mode.** Same student, one message only, word for word: "English isn't my first language and I'm trying to get better at emails. Is this too rude for my supervisor? "Hi Anna, I need your feedback on chapter 2 by Friday. Thanks."" The coach should open the skill and reply with a one-line verdict on how it reads to Anna, one recommended version, and one line on why, naming the cue (a statement of need with no question form or reason). It may say what in her version already works. Failure: a list of tips, more than one recommended version, or a version much longer than hers.

**Failure**

- A lecture on politeness, or a list of tips.
- The principle before her pick in the learning part.
- More than one question in a reply (G1).
- A recommended version that is much longer or more elaborate than hers, or that adds phrases she would not use ("I hope you are doing well!").

## 13. Returning writer with a profile

**Opening message**

````
Here's my writing profile. I'm about to write to my exchange coordinator about my learning agreement.

```markdown
## Writing profile

**How I write:** short and friendly, mostly to lecturers and the exchange office. Keep "Best, Jonas". No exclamation marks.

| Pattern | My example (date) | The rule in my words | In my last texts | Caught it myself |
|---|---|---|---|---|
| Tense and aspect | "Since two weeks I try to reach the office" (2026-11-02) | still going on → have been + -ing; for + how long | 3 of last 4 | once |
| Prepositions and set phrases | "a question to the exam" (2026-11-09) | question about | 1 of last 4 | no |
```
````

**Student.** Jonas, Swiss exchange student. After the coach's first reply, he sends his draft:

> Dear Ms Lindqvist, since last week I wait for the signature on my learning agreement. Could you tell me if you need an information from my home university? Best, Jonas

Then: "can you update my profile?". If offered a find-the-error item, he tries it. Then "thanks". 3 to 5 messages.

**The coach should**

1. First reply: one line on what to watch for, naming at most two patterns from the profile (the tense pattern first), then stop. No quiz, no recap of the profile, no fix (there is no text yet).
2. After the draft: the full fix with bold changes (*have been waiting*, *any information*), keeping "Best, Jonas" and adding no exclamation marks.
3. Start the receipt with how the active patterns did, for example "Tenses: 1 this time" and "question about: none this time".
4. On "update my profile", give back the whole section updated: the tense pattern counted as seen in this new text, the preposition pattern counted as not seen, a new row for *an information* only if the coach explains why it qualifies or Jonas asks.
5. Offer at most one find-the-error item from an old profile sentence, and only after the fix.

**Failure**

- Re-explains every pattern, or quizzes him before he has written.
- Gives only new rows to append, or more than five active rows.
- Claims to remember earlier sessions beyond what the profile says.
- Counts fixes made as progress.
- Changes his sign-off or adds an exclamation mark (W3).

## 14. The same mistake again

**Opening message**

> I'm learning English for my exchange semester. Can you check this?
>
> I live in Zurich since three years. I study economics and I like it very much.

**Student.** Elena, Italian is her first language. After the first reply she sends, word for word: "ok thanks. next part:" and then:

> Since September I work in a café. The work is hard but the people is nice.

If offered to look for the pattern herself next time, she says "yes". She then sends: "and this one: I know my flatmate since we were children." If asked to find the error first, she finds it. Then "thanks". 3 to 5 messages.

**The coach should**

1. Fix the first text with a receipt that names the *since*/*for* tense pattern.
2. For the second text: fix it, and say in the receipt that the same pattern came back, naming the sentence. Name *people are* as its own pattern only if there is room within three.
3. Offer once to let her look for this pattern herself next time.
4. After her "yes", start the third text by asking her to find the tense error herself (spot it first, for that pattern only), then confirm in a line.

**Failure**

- The repeated pattern is fixed again without being named as a repeat.
- More than one offer to look for it herself.
- After her "yes", the third text comes back fixed before she has had the chance to find the error.

## Trigger check for fixes

Run each first message three times in a fresh session with the skill installed. The skill should load for the first five and stay closed for the last five. Add the results to the trigger table in `results.md`.

| First message | Should load |
|---|---|
| Can you fix my English? It's not my first language. "Dear Prof. Keller, I write you because I have a question to the exam." | yes |
| I keep making the same mistakes in English. Can you correct this paragraph? "Since two years I study in Basel and I am very interested for finance." | yes |
| I want to get better at writing emails. Is this too rude for my supervisor? "I need your feedback by Friday." | yes |
| Kannst du die Grammatik in der Einleitung meiner Seminararbeit korrigieren? Sie wird benotet. "Die Digitalisierung verändern die Arbeitswelt." | yes |
| Here's my writing profile, can you check my new email? (with a profile block and a short email) | yes |
| Proofread my LinkedIn post: "Excited to announce that I started a new position as data analyst at Helvetia!" | no |
| Fix the typos in this message to my landlord: "Hi Mr Brunner, the heatng in the kitchen is broken since yesterday. Could you sent someone?" | no |
| Translate this paragraph into French: "Our office will be closed on Friday." | no |
| Make this product description sound more professional: "Our app is super good for tracking your runs." | no |
| Check the grammar of this caption for our team photo: "Our team at the summer party in Lucerne." | no |

---

# v0.3 additions

## 15. A reading, a summary and a fact to rely on

**Opening message**

> Can you summarise this for me? It's for my micro class.
>
> Price elasticity of demand measures how strongly the quantity demanded reacts to a change in price. It is calculated as the percentage change in quantity divided by the percentage change in price. If the absolute value is above 1, demand is elastic: a price rise lowers total revenue. If it is below 1, demand is inelastic: a price rise raises total revenue. Demand tends to be more elastic when close substitutes exist, when the good takes a large share of the budget, and over longer time periods.

**Student.** Mia, first-year student. When asked for her own version, she sends, word for word: "elasticity = how much quantity reacts to price. elastic means above 1, then a price rise raises revenue. more elastic if there are substitutes." If given a test case, she works it out correctly. Then she asks, word for word: "ok. last thing, I'll put this in my notes: is demand for petrol elastic or inelastic in the short run?" If asked to work it out, she answers "inelastic, because in the short run there are no real substitutes, you still have to drive. fairly sure." and adds, word for word: "and is there a typical number for it? I'll put it in my notes". 4 to 5 messages.

**The coach should**

1. Ask for her version first, in a way that is small enough to be painless.
2. Reply to her version with what it misses or gets wrong, a line each: the revenue direction for elastic demand, the inelastic case, budget share and time. Not a full summary of its own.
3. On the petrol question, either answer it or let her work it out from the factors in her summary (both fit the skill).
4. On the typical number, give it and say in a few words how sure it is, with a place to check (her textbook or slides).

**Failure**

- A full summary before her version, or instead of the list of gaps.
- The revenue error is not named.
- No word on how sure the coach is about the number, or a disclaimer of more than one sentence.

## 16. Exam prep: a miss comes back as a variant

**Opening message**

> Quiz me on supply and demand, my exam is on Friday 20 November.

**Student.** Jonas. If asked about the format: "written, short calculations and explaining graphs". In the pre-test he answers the question about a rise in the price of a substitute wrong and says "sure" (he says demand for the good falls). He answers the other questions right. After the feedback he writes, word for word: "ok I have to go, can you give me my log entry?" About 8 to 10 messages.

**The coach should**

1. Run a short pre-test with confidence before feedback.
2. Work on the sure-but-wrong item first.
3. Give a log entry whose review queue holds a variant of the missed question (the same idea in a new case, not the same question), due on 17 or 18 November 2026.

**Failure**

- The missed question appears in the log only word for word as it was asked.
- The review date for the miss is later than 18 November 2026.
- New material is explained before the pre-test.

## 17. Drafting for a course

**Opening message**

> Help me write my motivation letter for the exchange semester in Lund. I want to get better at this kind of writing.

**Student.** Noemi. When asked for a rough version, she sends, word for word: "- study economics, 5th semester, Basel - Lund has sustainable finance courses - want to improve my english - worked as a tutor". When asked for sentences, she sends, word for word: "I am study economics in 5th semester at the University of Basel. I want to make my exchange in Lund because there is courses in sustainable finance, what interest me since a long time." Then "thanks". 3 to 4 messages.

**The coach should**

1. Not write the letter in the first reply. Ask for her rough version, in one question.
2. On the bullet points, ask her to turn the first one or two into rough sentences.
3. On her sentences, give the fix with the changes in bold and a receipt of at most two lines (for example *I am studying*, *there are courses*, *which have interested me for a long time*), and offer to do the next part the same way.

**Failure**

- A finished letter, or a full paragraph of the coach's own, before she has written sentences.
- More than one question in a reply.
- A receipt longer than two lines, or restyling beyond the errors.
