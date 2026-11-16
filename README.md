# learning-coach

An Agent Skill that turns a general AI assistant into a learning coach. Its aim is what you can do afterwards **without** the AI, so it gets you to do the thinking and keeps its own help small.

There is also a short paste-in prompt for assistants that do not support skills.

Version 0.1. Deutsche Kurzfassung [weiter unten](#kurz-auf-deutsch).

## Why this exists

Most students use AI as an answer machine, and the research suggests that this costs them. In a field experiment with nearly a thousand high-school mathematics students, those who practised with a plain chatbot did better during practice and worse on the later exam without it. A second version of the tutor, with guardrails, improved practice even more and largely avoided that harm (Bastani et al., 2025). In a randomised trial in a university physics course, students learned more with an AI tutor built on learning principles than in an active-learning class (Kestin et al., 2025).

This skill gives a general assistant the same kind of guardrails. What the sources support is that guardrails prevent harm and make practice more effective. Nothing here shows that the skill makes anyone learn faster or get better grades, and the skill itself has not been evaluated with students. See [Limits](#limits).

## What a session looks like

1. **Plan** (about a minute). The coach asks for your goal and what you already know. At most three short questions.
2. **Attempt first.** You try before anything is explained. If you are stuck, help comes in small steps: a guiding question, then a hint, then one step done for you, then a worked example followed by a similar problem that you solve alone.
3. **Explain back.** You say it in your own words, then answer one question about a new case.
4. **Check without AI.** Two or three questions from memory. You say how sure you are before you get feedback.
5. **Reflect and schedule.** You get a short entry for your learning log with a review date. Next time, paste the log and the coach starts by quizzing you from it.

Three things to know before you start:

- **You stay in charge.** Say "just tell me" and you get the answer. The coach mentions the trade-off once, in one sentence, and does not lecture.
- **Graded work.** The coach explains methods and gives feedback on your own draft. It does not write your submission.
- **Ordinary tasks.** Ask it to write an email or format a table and it simply does that.

## Install

### Claude (web or desktop app): upload a ZIP

You need a Claude account. Skills also work on the free plan.

1. Download **`learning-coach.zip`** from the [latest release](https://github.com/scotchline/learning-coach/releases/latest). Do not unpack it.
2. In Claude, open **Settings > Capabilities** and switch on **Code execution and file creation** (in the newer layout it is called *Create and edit files*). Skills need this.
3. Go to **Customize > Skills**, click **+**, then **Create skill**, then **Upload a skill**, and choose `learning-coach.zip`.
4. Check that the skill is switched on in the list.

Then start a new chat and ask something you want to learn, for example "Help me understand net present value". The skill loads on its own when you ask to learn, understand, revise or be quizzed.

If you would rather build the ZIP yourself, for example after changing the skill: download this repository (**Code > Download ZIP**), unpack it, and compress the folder `skills/learning-coach` on its own. If the upload fails, the usual cause is that the whole repository was zipped. The ZIP must contain the folder `learning-coach` with `SKILL.md` directly inside it.

Menu names in Claude change from time to time. The steps above follow Anthropic's help article "Use skills in Claude" as of November 2026.

### Claude Code

Copy the skill folder into your personal skills folder:

```bash
git clone https://github.com/scotchline/learning-coach.git
```

```bash
mkdir -p ~/.claude/skills && cp -r learning-coach/skills/learning-coach ~/.claude/skills/
```

The skill is then available in every project on that machine. To use it in one project only, copy it to `.claude/skills/` inside that project. Start a new session and ask a learning question, or type `/learning-coach`.

### ChatGPT and other assistants: the paste-in prompt

Assistants without skill support can use [`portable/prompt.md`](portable/prompt.md). It is a short version of the same rules.

- **For one conversation:** copy the whole text of `portable/prompt.md`, paste it as the first message of a new chat, and add your question below it.
- **For every conversation in ChatGPT:** open **Settings > Personalization > Custom instructions** and paste the text into the field that asks how ChatGPT should respond. The prompt is under 1,500 characters so that it fits this field. It also tells the assistant to simply do ordinary tasks, so your other chats keep working as before.
- **For one course:** if your assistant has projects or custom assistants with their own instructions, paste the text there.

The paste-in prompt has no hint examples and no log template, so expect it to be a little less consistent than the skill. The location of custom instructions in ChatGPT has moved before; if you cannot find it, search the settings for "custom instructions".

## Using it

Things you can say:

- "Explain opportunity cost. We had it today and I didn't get it."
- "I have a statistics exam on 24 November. Quiz me on regression."
- "Here is my learning log from last week. Quiz me from it."
- "I want flashcards for chapter 4." (You draft them, the coach corrects them and adds questions you missed.)
- "Just tell me." (Any time.)

**The learning log** is a Markdown file that you keep, for example in your notes app. A template is in [`skills/learning-coach/assets/learning-log.md`](skills/learning-coach/assets/learning-log.md). The coach cannot remember earlier chats or remind you of anything. The log is what connects one session to the next, so the review only happens if you bring it back.

## Limits

- **Not evaluated with students.** The skill applies principles from the learning literature. Whether it improves what students can do has not been measured. It makes no promise about speed or grades.
- **It is a set of instructions, not a guarantee.** The assistant may drift from them, especially in long conversations, and different models follow them differently.
- **The assistant can be wrong about the subject.** Check formulas, definitions and facts against your course material. The coach is told to remind you of this.
- **It cannot enforce anything.** You can always ask for the answer or switch the skill off. That is intended.
- **It does not know your university's rules.** The coach declines to write graded work when it can tell that work is graded. What counts as permitted AI use in your course is for you to check.
- **No memory, no reminders.** Reviews depend on you keeping the log and coming back.
- **Tested with simulated students only,** in English and German, on one assistant. See [Tests](#tests).
- **The paste-in prompt is weaker than the skill.** It is a small fraction of the length and has none of the reference files.
- **The evidence is indirect.** The two studies with measured learning outcomes used purpose-built tutors, one of them with high-school students in mathematics. One source for Socratic questioning (Bereznikova et al., 2026) measured perceived critical thinking after six-minute dialogues and no learning outcome. Several references are still incomplete and marked TODO in the evidence table.

## Where the rules come from

Every rule in the skill traces to one of three principles and to a named source:

1. AI should stimulate thinking, not replace it.
2. AI should promote active learning and long-term retention.
3. AI should support self-regulated learning.

The full table of rule, principle and source is in [`skills/learning-coach/references/evidence.md`](skills/learning-coach/references/evidence.md). It also says which mappings are still proposals and which rules are design decisions with no study behind them. The source list it is built from is in [`docs/`](docs/).

## Tests

[`tests/scenarios.md`](tests/scenarios.md) describes eight conversations with expected behaviour and failure criteria: a normal session, "just give me the answer" three times, a graded assignment, a confident wrong answer, a 40-message session, a non-learning request, a returning student with a log, and a German-speaking student.

[`tests/results.md`](tests/results.md) records the runs, with transcript excerpts, what failed along the way and what was changed. The tests use simulated students. They show whether the assistant follows the rules, and they say nothing about learning outcomes.

## Repository layout

```
learning-coach/
  README.md
  LICENSE
  docs/                         source mapping and reference list
  skills/learning-coach/
    SKILL.md                    the skill
    references/modes.md         learn something new, exam prep (two more planned)
    references/hint-ladder.md   how help is graded
    references/evidence.md      rule -> principle -> source
    assets/learning-log.md      log template
  portable/prompt.md            paste-in version
  tests/scenarios.md            test scenarios
  tests/results.md              test results
```

The skill follows the open [Agent Skills format](https://agentskills.io/specification). It contains no scripts and makes no network calls, so everything it does can be read in the files above.

## For maintainers

`portable/prompt.md` is a copy of the block between the `portable:start` and `portable:end` markers in `SKILL.md`. Edit the block in `SKILL.md`, never the copy. This command prints nothing when the two are identical, followed by the character count (limit 1,500):

```bash
diff <(sed -n '/^<!-- portable:start -->$/,/^<!-- portable:end -->$/p' skills/learning-coach/SKILL.md | sed '1d;$d') portable/prompt.md; wc -m portable/prompt.md
```

After any change to `SKILL.md` or the prompt, rerun the scenarios in `tests/scenarios.md` and update `tests/results.md`.

Planned for later versions: the modes "feedback on my work" and "teach-back", and printable outputs such as test sheets.

## Kurz auf Deutsch

**learning-coach** macht aus einem allgemeinen KI-Assistenten einen Lerncoach. Das Ziel ist, was du nachher **ohne** KI kannst. Der Coach lässt dich deshalb zuerst selbst denken und hilft nur so viel wie nötig.

**So läuft eine Sitzung ab:** kurz planen, zuerst selbst versuchen (Hilfe kommt in kleinen Schritten), in eigenen Worten erklären, kurzer Check ohne KI mit Einschätzung der eigenen Sicherheit, zum Schluss ein Eintrag fürs Lernjournal mit Datum für die nächste Wiederholung. Der Coach antwortet in deiner Sprache.

**Gut zu wissen:** Mit «sag es mir einfach» bekommst du die Antwort, ohne Vortrag. Bei benoteten Arbeiten erklärt der Coach Methoden und gibt Rückmeldung zu deinem Entwurf, schreibt die Arbeit aber nicht. Gewöhnliche Aufträge wie eine E-Mail oder eine Tabelle erledigt er einfach.

**Installation in Claude:** Die Datei `learning-coach.zip` beim [neusten Release](https://github.com/scotchline/learning-coach/releases/latest) herunterladen, nicht entpacken. In Claude unter *Settings > Capabilities* die Code-Ausführung einschalten, dann unter *Customize > Skills* auf *+*, *Create skill*, *Upload a skill* klicken und das ZIP hochladen. Details stehen oben unter [Install](#install).

**ChatGPT und andere:** Den Text aus [`portable/prompt.md`](portable/prompt.md) als erste Nachricht in einen neuen Chat einfügen oder in ChatGPT bei den *Custom instructions* hinterlegen.

**Grenzen:** Der Skill wurde noch nicht mit Studierenden evaluiert. Er verspricht weder schnelleres Lernen noch bessere Noten. Die Forschung, auf die er sich stützt, zeigt, dass Leitplanken Schaden verhindern und das Üben wirksamer machen. Die KI kann sich fachlich irren, also prüfe Formeln und Definitionen im Skript nach. Wiederholungen finden nur statt, wenn du dein Lernjournal führst und wieder mitbringst.

## Licence

[MIT](LICENSE). Copyright (c) 2026 Daniel.
