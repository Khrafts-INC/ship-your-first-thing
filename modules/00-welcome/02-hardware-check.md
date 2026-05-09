---
title: "Hardware check"
module: "00-welcome"
lesson_number: 02
est_minutes: 10
prereqs: ["01-welcome"]
updated: "2026-05-08"
deviations: []
---

# Hardware check

## Learning objective

By the end of this lesson, you will know whether you're using GitHub Codespaces (recommended for V1) or a local install, and what either choice costs you in time and money.

## Why this matters

This is the cheapest decision you'll make in the course, and getting it wrong is the most expensive way to start. Codespaces removes a category of "my computer is set up wrong" problems that cost beginners days. Local installs are faster once they work, but the working part is itself a learning project. Pick once, in this lesson, before you create any accounts.

## Core read

Two paths.

**Path A: GitHub Codespaces (recommended for V1).**
A Codespace is a development environment that runs in the cloud. You open it from your browser, edit code in an editor that looks and feels like VS Code, and run commands in a terminal — but everything actually runs on a machine GitHub manages, not on your laptop. Your laptop just needs a modern browser.

What this gets you:

- No local install for Module 0 / Module 1 (which are pure markdown). Open the repo in your browser; you're done.
- For Module 2 onward (toolchain, AI agents, the thread project), the Codespace already has Node, git, and the AI agent installed and configured.
- A consistent environment. The course is verified against the Codespace image listed in `VERSIONS.md`. If it works for one learner, it works for all.

What it costs:

- The GitHub free tier includes **120 core-hours per month** on a 2-core machine, which is **60 clock-hours per month**. Enough for a focused learner doing a few hours per week. Not enough for binge-watching every weekend.
- Default auto-stop is **30 minutes idle** — leave a tab open and walk away, the Codespace pauses on its own.
- Storage cap is **15 GB**. Delete unused Codespaces to free space.
- If you blow past 120 core-hours, GitHub bills $0.18 per core-hour. Most learners don't hit this.

**Path B: Local install (appendix path).**
If you already have Node.js, git, and a code editor you prefer (and you're comfortable troubleshooting your own environment), see the local install appendix in [`SETUP.md`](../../SETUP.md). The course will not walk you through installing these tools; that's the appendix's job. Use this path if your free Codespace hours run out, or if you really prefer your own editor.

What it costs:

- Time. Setting up Node, git, and your editor on Windows is the rabbit hole this course's primary path was designed to avoid.
- Self-troubleshooting. If your local install hits a "can't find this binary" error, that's your problem to solve, not the course's.

**Which to pick:**

- If you've never written production code: **Codespaces**. No exceptions.
- If you've already got Node, git, and a code editor working and you read code well enough to debug environment issues: either is fine.

If you pick Codespaces and later want to switch to local, you can — the course works the same way on both surfaces, and `SETUP.md` covers the switch. If you start on local and hit an environment issue you can't solve in 30 minutes, switch to Codespaces.

## Exercise

This is a 5-minute decision exercise. Answer these out loud or on paper:

1. Do I have a modern browser on a computer I'll be using consistently? *(If yes, Codespaces will work. If no, this course has a hard prerequisite you're missing.)*
2. Do I already have Node.js, git, and a code editor installed? *(If no, pick Codespaces. If yes, you can pick either.)*
3. Have I ever spent more than 30 minutes troubleshooting why a development tool wouldn't run on my computer? *(If you don't know, pick Codespaces. If yes and the experience was frustrating, pick Codespaces. If yes and you enjoyed it, you can pick either.)*

Your answer to question 2 or 3 picks your path.

## Checkpoint

You've got this if you can:

- State your chosen path in one sentence.
- Name the free-tier cap on Codespaces (120 core-hours, 60 clock-hours on a 2-core machine).
- Find the local install appendix in `SETUP.md` without re-reading this lesson.

## What you just did

You picked your environment based on a 5-question triage instead of installing things and discovering the cost later. The next lesson does the same triage for AI tooling cost. The pattern — triage before install — is the most expensive bug-prevention you'll do all course.

## Navigation

[← Previous: Welcome](./01-welcome.md)
[Next: Cost-path triage →](./03-cost-path-triage.md)
