# WHAT-CHANGED.md — Freshness log

Reverse-chronological log of what shifted between course revisions. The first place to check when reality drifts from a lesson.

Each entry has the format:

> ## YYYY-MM-DD — {one-line summary}
> **What changed:** ...
> **Affected lessons / artifacts:** ...
> **What learners should do:** ...

---

## 2026-05-08 — V1 baseline

**What changed:** Initial release of the course's v1 baseline. Module 0 (Welcome) and Module 1 (Mental models) ship with the locked nine-element lesson anatomy. Cross-cutting artifacts (README, SETUP, BUDGET, GLOSSARY, CHEATSHEET, COMMON-ISSUES, CONTRIBUTING, VERSIONS) ship with seed content sufficient for Phase 1 + linkable from Phase 2 onward. Dual MIT (code) + CC BY 4.0 (prose) licensing committed.

**Affected lessons / artifacts:** All v1 baseline. Lesson template locked at `lesson-template.md`; M0-variant locked at `lesson-template-m0.md`. Three named cost paths in `BUDGET.md`: Claude Code Pro / Gemini CLI free tier / Anthropic API token-careful.

**What learners should do:** Start with Module 0. If you came back to this entry because something seems off, check `VERSIONS.md` first — every tool the course is verified against has a `Last verified` date there.

**Decision-change context:** This release reflects the 2026-05-08 swap of the free OSS AI agent from Aider to Gemini CLI. The Aider/OpenRouter cost path that appeared in earlier research (`./.planning/research/SUMMARY.md`) is superseded by `BUDGET.md` Path 2 (Gemini CLI free tier).
