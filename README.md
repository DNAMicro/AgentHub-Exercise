# AgentHub Exercise

Build **AgentHub** yourself, one step at a time, with Claude Code.

AgentHub is a small, local, fictional university. Agents talk over the real **A2A** (Agent-to-Agent) protocol, through a University Hub: a Student agent, a Tutor, a Library and a Marketing 101 Professor. Agents can send interfaces (**A2UI** forms) inside their messages, and some of them think with **Claude Haiku 5.5**.

This repository has **no app code**. It holds what you need to build the app:

| Folder | What it is |
| --- | --- |
| [`Steps-classroom/`](Steps-classroom/README.md) | **The prompts to follow.** Steps 0–9c, written for class: a Sonnet lead session plus cheap Haiku subagents working in parallel. |
| [`Steps/`](Steps/README.md) | The original build record: Steps 1–9 in the long form they were first written in. Read it to see how each step came about. |
| [`companion-site/`](companion-site/README.md) | A teaching site that explains each step: what it changes, why, and how it works, on one evolving architecture diagram. |

## Before you start

- Node.js 20 or newer, and git.
- [Claude Code](https://claude.com/claude-code). Use **Sonnet** as the main model (`/model`).
- An Anthropic API key, only for the optional "live" checks. Every step's required checks pass without one. Never commit the key: it goes in a `.env` file, which Step 0 tells git to ignore.

## 1. Open the teaching site

```bash
cd companion-site
npm start
```

Then open **http://localhost:4440**. It has no dependencies and needs no API key. Keep it open beside Claude Code: for each step, read what it is about, then build it.

## 2. Build the app, one step at a time

1. Open Claude Code in **this folder** (the repository root). Build here, not in a subfolder.
2. Paste the whole of [`Steps-classroom/00-setup-and-contracts.md`](Steps-classroom/00-setup-and-contracts.md) as your message. Claude sets up the project and commits `Step 0`.
3. Then paste `01-…`, `02-…`, and so on up to `09c-…`, **one step at a time and in order**. Each step ends when its **Done when** checks pass and Claude has committed `Step N: …`.
4. Between steps, look at what was built: run it, read the code, and compare it with that step's pages on the teaching site.

[`Steps-classroom/README.md`](Steps-classroom/README.md) explains how each step runs: contracts first, then parallel subagents, then join and check. Each step file starts with its time. Its "Cost" line is about the app's own model calls, which the required checks never make.

**Claude Code usage is what costs money.** In a trial run, Steps 0–3 used about $2 of Sonnet and Haiku together. The later steps are bigger.

Follow one edition. The classroom edition is the one to build with. The original `Steps/` files describe the same app in a different order and are not meant to be mixed with it.

## Notes

- Everything runs on your own computer, on `127.0.0.1`. All people, books and courses are fictional.
- Some steps ask Claude to add a section to "the README". It adds its notes about your app below this line.

---
