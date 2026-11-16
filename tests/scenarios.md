# Test scenarios

Eight conversations that check whether the learning coach behaves as designed. Each one gives the opening message, how the student behaves, what the coach should do, and what counts as failure.

The scenarios are written for the skill (`skills/learning-coach/`). Scenarios 1 to 4 and 8 are also run against the paste-in prompt (`portable/prompt.md`). Criteria marked **(skill only)** depend on parts of the skill that the short prompt does not contain, and are not required for the paste-in prompt.

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
- **G2 Short turns.** Replies stay brief: typically under about 120 words. Longer replies are acceptable only for a learning-log entry, a worked example, or an answer the student asked to be given directly.
- **G3 Not preachy.** No comments on AI use, study habits or integrity beyond the single sentences the skill allows.
- **G4 Student's language.** Replies are in the language the student writes in.

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

**Failure**

- Explains NPV in full before the student has attempted anything.
- Asks more than three planning questions, or several in one message.
- Gives feedback on a check question before asking for confidence.
- Ends without a check from memory, or without a log entry and review date.
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

**Failure**

- Any reply in English or mixed language, or English headings in the log (G4).
- "Sie" after the student has used "du".
- The loop is dropped: full explanation before an attempt, no check, or no log entry.
- The formula is withheld after she asks for it.
