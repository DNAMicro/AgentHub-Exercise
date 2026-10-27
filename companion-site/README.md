# AgentHub, step by step — companion site

A standalone teaching site that explains how the AgentHub app was built in Steps 1–9: what each step changed and why, and how it works, on one architecture diagram that evolves from step to step. The site was made from the original project, AgentHub-POC, so it says that name in places. The finished code is not in this repository: you build it yourself with the step prompts.

## Start it

```bash
cd companion-site && npm start
```

Open **http://localhost:4440**. The site binds to 127.0.0.1 only. If port 4440 is taken, it stops with a message rather than choosing another port. It needs no API key, no model calls, no login and no part of the application running: it is static files plus a 40-line Node server, with no dependencies.

## What is in it

- **19 pages:** an introduction, then for each step **A** (what changed and why) and **B** (how to build it and how it works). The recap is in Step 9.
- **One architecture diagram** (`public/js/diagram.js`). Every component and connection has a fixed position, name and colour. Each step is an absolute snapshot (`ARCH` in `public/js/content.js`). The site computes what was added and removed and marks it with a tag, a border style and a colour: **+ NEW**, **~ CHANGED**, **✕ REMOVED**. Connections are labelled with what they carry. Line style shows the kind: A2A (solid), HTTP, SSE (dotted), HTTPS model call (dashed), file (dash-dot).
- **Comparison (page A):** *Previous step / This step / Animate the change*. Step 9 also offers *Step 1 → Step 9*.
- **Walkthrough (page B):** one concrete user action, hop by hop. It has Play, Pause, Replay, Prev and Next event controls and a caption per event. The numbered list beside it is the same walkthrough without motion. It is labelled **Simulated**: nothing is sent to any agent or model.
- **Screenshots:** real screenshots of the running app, taken on a separate test stack with fictional data. They show today's UI, and each caption says which step's idea it illustrates.
- **Keys:** ← → (PageUp / PageDown) change pages, Home / End jump, F starts presentation mode (full screen, no top navigation) and Esc leaves it. Swipe works on touch screens.
- **Theme:** the ◐ button in the header (or **T**) cycles **Auto → Light → Dark**. Auto follows the computer's setting. The choice is remembered in this browser (`localStorage`) and applied before the page draws, so it never flashes the wrong theme. If storage is blocked, it still works for the open page.
- **Reduced motion:** no animation; tokens jump to their destination and changes appear at once.

## Where the content comes from

The pages were written from the original project's step prompts (the `Steps/` folder next to this one), its git history, its tests and its documentation. Each page's "Sources" list names the files and commits of that original project: they are the files you will create yourself when you run the steps. Commit ids refer to the original AgentHub-POC history, not to this repository.

Known limits:
- **Screenshots show the finished app's UI.** Each caption says which step's idea it illustrates; the Step 2 monitor looked different when it was first built.
- **Some early examples changed later.** Step 3's first form was replaced by the tutoring-request form in Step 6, and Step 4's model call later moved to `src/llm.js`. The pages say so where it matters.
