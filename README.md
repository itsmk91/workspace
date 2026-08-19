# 🌌 Workspace

**A local-first macOS control room for building software with AI — without surrendering the final decision.**

> A showcase of a private project. Screenshots and design, not source.

![Overview — every project, agent, skill and rule as one live map](media/01-overview.png)

---

## The idea

AI agents are fast, confident, and occasionally wrong in ways you only discover later. Workspace exists to keep the speed and take back the last word.

Agents read an idea, ask questions until they actually understand it, write a plan, and do the work. What they never do is decide the work is finished.

**Every gate belongs to a person.**

---

## The board

![Backloop — the human-gated pipeline](media/02-backloop.png)

Work moves through five stages: **idea → plan → active → review → complete**.

An agent makes exactly two of those moves — drafting the plan, and delivering the finished work for review. The three in between are pressed by a human:

- **Commit** — you've read the plan and you're authorising the build
- **Accept** — you've reviewed the result and it lands
- **Reject** — it goes back, with your reason attached

An agent cannot advance its own work. Not by asking nicely, not by editing a file — the tooling refuses.

**Every delivery arrives with proof:** a before-and-after picture and a plain-language note explaining what changed. You review the card, not the codebase.

---

## Three agents, one human gate

Each agent has a fixed job, and no agent may change its own:

- **Grok** — asks the questions, writes the plan, owns the design
- **Claude** — builds
- **Codex** — reads the code another agent wrote and reports the bugs in plain language
- **You** — decide

**No agent reviews its own work.** The reviewer exists for a specific reason: the person holding the gate may not read code. So a second agent reads it for them and writes what's wrong in words they can act on. You still press Accept — but you press it informed.

Swapping who builds and who reviews is a human button, and it lasts exactly one task.

---

## The law

![Knowledge — the rules that govern the AI, live-mirrored and read-only](media/03-rules.png)

Twenty-four standing rules the agents load at the start of every session. **Each one is written together with the failure that produced it** — the wrong build, the lost afternoon, the thing that nearly shipped.

A few of them:

- **Prove it before you call it done.** Run it, screenshot it, show the output. Not "should work."
- **Study before you guess.** Every fix ever made is searchable. Read it before theorising.
- **Build only what was asked.** An unrequested addition is a defect, not a bonus.
- **Ask until you understand.** The stop condition isn't a question count — it's replaying the task back in your own words and hearing *"yes, that's it."*
- **Design comes first.** The look is decided deliberately, before a line of interface is written.

And the rules aren't advice. Four guards sit between the agent and your machine and **refuse**: destructive commands, edits outside an agent's assigned lane, a font that isn't in the project's design law, a stray API key or network call slipping into a build. Each one fails closed — unreadable input is a denial, not a pass.

---

## The memory

Every bug this system has ever hit is written down — not in someone's head, but in a folder the agents are required to read *before* they touch anything.

It holds three kinds of note:

- **A diary.** What broke, what fixed it, which project, what date. Specific, not wise. **176 entries so far.**
- **A textbook.** The lesson *behind* a fix, once it turns out to be bigger than the bug that caused it. Not *"the button was the wrong colour"* but *"a disabled button with custom colours looks enabled and dies silently."* **145 of them.**
- **A map.** How a piece of the machinery actually works, written down so nobody has to re-derive it.

One rule keeps the textbook honest: **every** fix goes in the diary, but only a fix a future agent would hit again — different project, different month — gets promoted to a lesson. One-offs stay one-offs, so the textbook never fills with noise.

### Why it exists

**An agent's memory ends when the session does.** Whatever it works out today, it has forgotten by tomorrow. Without somewhere to put what it learned, every session starts from zero and the same ground gets covered forever.

**The same bugs were being solved twice** — and sometimes solved *differently* the second time, so the new fix quietly undid the old one. A fix costs an hour once. Re-guessing it costs an hour every time it comes back.

**Writing it down is only half of it.** The other half is a search that runs *before* anyone theorises about a cause. Record without recall is a diary nobody reads.

**And it compounds.** The rules in this system weren't designed in the abstract. The guards, the agent lanes, the scope check — each one exists because the diary showed the same shape of mistake twice. Every rule was a scar somebody wrote down first.

176 things went wrong in four weeks. That isn't a failure record. It's **176 traps that are now mapped**, and the next agent walks past all of them.

### The problems didn't just make rules — they made tools

Some of the agents' own skills exist only because something went wrong first. Each of these was written here, for this system, after a specific failure:

- **A skills auditor.** Two skills quietly ended up competing for the same job. Because agents pick a skill by reading its description, two overlapping descriptions make the choice unpredictable — so it didn't present as a duplicate, it presented as a *random bug*. Whole work sessions went into unpicking it. The answer was a read-only auditor that checks every installed skill for duplicate names, clashing triggers, broken structure and safety signals, so a clash surfaces the same day instead of three weeks later as a mystery.

- **A repair workflow.** Once the auditor started finding things, it turned out the ecosystem was full of tools that *diagnose* a broken skill and none that safely *fix* one. So one got built: back up first, apply the smallest change that works, re-audit, and show before-and-after proof.

- **A front-door guard.** One briefing was rejected five times in a row. Every rejection traced back to the same root cause — a question nobody asked before building. So the asking became a tool: clarifying questions, click-to-answer, before a plan exists, ending with the task replayed back in the person's own words for a yes.

- **A peer reviewer.** *"I'm not a developer — even if I read the code I won't understand it."* That sentence became a skill: a second agent reads the code the first one wrote and reports the bugs in plain language, on the card, before anything is approved.

The pattern is the whole point. A bug gets fixed, then written down. If it keeps happening, it becomes a rule. If the rule needs enforcing, it becomes a guard. And if the work itself keeps repeating, **it becomes a tool** — so nobody has to remember to do it right.

---

## The toolbox, audited

![Skills — 34 audited, zero broken](media/04-skills.png)

Thirty-four agent skills, continuously audited across Claude, Codex and the open Agent Skills contract — checked for structure, portability, trigger conflicts and safety signals. Read-only: nothing is executed to inspect it.

The system checks its own tools, and reports what it finds.

---

## What it's built on

Electron · Node · macOS. Offline by default — it reads your projects live from disk and never copies your code anywhere.

---

<sub>Source kept private. · [LinkedIn](https://www.linkedin.com/in/mohammad-aljaziri-940750105/)</sub>
