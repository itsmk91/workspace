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

## The toolbox, audited

![Skills — 34 audited, zero broken](media/04-skills.png)

Thirty-four agent skills, continuously audited across Claude, Codex and the open Agent Skills contract — checked for structure, portability, trigger conflicts and safety signals. Read-only: nothing is executed to inspect it.

The system checks its own tools, and reports what it finds.

---

## What it's built on

Electron · Node · macOS. Offline by default — it reads your projects live from disk and never copies your code anywhere.

---

<sub>Source kept private. · [LinkedIn](https://www.linkedin.com/in/mohammad-aljaziri-940750105/)</sub>
