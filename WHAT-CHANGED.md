# WHAT-CHANGED.md — Freshness log

Reverse-chronological log of what shifted between course revisions. The first place to check when reality drifts from a lesson.

Each entry has the format:

> ## YYYY-MM-DD — {one-line summary}
> **What changed:** ...
> **Affected lessons / artifacts:** ...
> **What learners should do:** ...

---

## 2026-05-10 — Phase 1 gap closure (M0/M1 audience pass, M1 bundle 3 split, voice-lint upgrade)

**What changed:** After the 01-HUMAN-UAT.md walkthrough surfaced three editorial gaps in the original Phase 1 close, plans 01-6 / 01-7 / 01-8 shipped to close them.

1. **Audience-aware vocabulary contract.** `docs/audience-vocabulary.md` now classifies every technical noun for M0 and M1 into three categories: Safe (use freely), Requires-callout (D-04 pattern on first use), Forbidden (deferred to a later module). All five M0 lessons and the four M1 lessons were rewritten against the contract. Nine new GLOSSARY anchors added (markdown, Codespace, code-editor, ai-coding-agent, terminal, api-key, free-tier, rate-limit, token-discipline).

2. **M1 expanded from three bundles to four.** The original bundle 3 (`03-who-can-do-what.md`) mixed authentication and deployment as if they were one concept. It now splits cleanly: `03-who-can-do-what.md` is auth-only (door-staff / VIP-list / hand-stamp analogy); a new `04-how-it-goes-live.md` covers deployment (private kitchen → public restaurant analogy). The M1 README, prev/next nav chain (02 → 03 → 04 → course README), and 01-CONTEXT.md D-06 amendment block all reflect the four-bundle shape. The original D-06 wording is preserved above the amendment for traceability.

3. **Simple-first / bridge-second Mermaid convention.** Every M1 Mermaid now teaches the concept twice: an analogy-only diagram first (using only the locked D-07 nouns — restaurant / filing-cabinet / door-staff / opening-night family), then the technical Mermaid with `= browser`, SQL/HTTP shorthand, and CI/CD labels preceded by a `> *Bridge to the real terms:*` blockquote. `lesson-template.md` encodes the pattern with a worked example. New `diagrams/how-it-goes-live.md` standalone source mirrors bundle 4's lesson.

4. **`scripts/voice-lint.sh` near-total rewrite.** Grew 92 → 645 lines. WR-01..WR-05 + IN-04 shell-hygiene fixes from `01-REVIEW.md` are all resolved (quoted variables, `--` end-of-options sentinels, per-line VIOLATIONS counter, case-insensitive GLOSSARY anchor resolution, missing-GLOSSARY emits violation). Two new checks: broken-relative-path (catches the GLOSSARY 404 bug shape fixed in `fe2450b`) and jargon-density (parses `docs/audience-vocabulary.md` and flags Forbidden bare uses + missing D-04 callouts for Requires-callout terms). New `--self-test` mode runs the lint against `scripts/voice-lint-fixtures/*.md`; each fixture intentionally trips one check.

**Affected lessons / artifacts:** All Module 0 lessons, all Module 1 lessons (including the new bundle 4), `lesson-template.md` + `lesson-template-m0.md`, GLOSSARY.md, `scripts/voice-lint.sh`, CONTRIBUTING.md (pre-push checklist references new checks). New files: `docs/audience-vocabulary.md`, `modules/01-mental-models/04-how-it-goes-live.md`, `diagrams/how-it-goes-live.md`, `scripts/voice-lint-fixtures/{01..06}.md` + README. Phase 1's ROADMAP entry now shows 8/8 Complete.

**What learners should do:** No action. The bundle-3 split adds bundle 4 (deployment) — a learner who finished the original three-bundle M1 can now read the new bundle 4 lesson to complete the four-bundle mental model.

**What contributors should do:** `scripts/voice-lint.sh --self-test` is now part of the lint surface — run it from a clean checkout if you modify the lint. The default `scripts/voice-lint.sh` still passes (0 violations) but emits ~50 `WARN (jargon-density …)` lines covering the audience-vocabulary editorial backlog. The WARNs are not blocking; they document remaining tightening opportunities the editorial team will close incrementally. If you author a new lesson, classify every new technical noun in `docs/audience-vocabulary.md` AND add a `GLOSSARY.md#anchor` entry in the same PR.

---

## 2026-05-08 — Phase 1 close

**What changed:** Phase 1 (Foundation & Front Door) closed. Module 0 (5 lessons) and Module 1 (3 bundles) ship with the locked nine-element lesson anatomy and M0-variant baseline. All eight cross-cutting artifacts (README, SETUP, GLOSSARY, CHEATSHEET, COMMON-ISSUES, BUDGET, CONTRIBUTING, WHAT-CHANGED, plus standalone VERSIONS) shipped at Phase-1 depth. Editorial pass via `scripts/voice-lint.sh` returned clean on first run (zero violations across the full Phase 1 surface). Phase 1 success criteria #1–#5 satisfied.

**Affected lessons / artifacts:** All Phase 1 deliverables. The following invariants are now enforceable on every future PR via `scripts/voice-lint.sh`:
- No tutorial fiction (LESSON-12)
- No filler prose (LESSON-12)
- No GitHub-specific admonitions (D-18 SSG-portability)
- Every `GLOSSARY.md#anchor` used in any lesson resolves to a `### anchor` entry

**What learners should do:** No action. Phase 2 (Toolchain & The Loop) is the next phase to land; until then, Module 0 and Module 1 are the available content.

**What contributors should do:** Run `./scripts/voice-lint.sh` before opening a PR that touches course markdown. The lint step is documented in `CONTRIBUTING.md` as part of this same plan.

---

## 2026-05-08 — V1 baseline

**What changed:** Initial release of the course's v1 baseline. Module 0 (Welcome) and Module 1 (Mental models) ship with the locked nine-element lesson anatomy. Cross-cutting artifacts (README, SETUP, BUDGET, GLOSSARY, CHEATSHEET, COMMON-ISSUES, CONTRIBUTING, VERSIONS) ship with seed content sufficient for Phase 1 + linkable from Phase 2 onward. Dual MIT (code) + CC BY 4.0 (prose) licensing committed.

**Affected lessons / artifacts:** All v1 baseline. Lesson template locked at `lesson-template.md`; M0-variant locked at `lesson-template-m0.md`. Three named cost paths in `BUDGET.md`: Claude Code Pro / Gemini CLI free tier / Anthropic API token-careful.

**What learners should do:** Start with Module 0. If you came back to this entry because something seems off, check `VERSIONS.md` first — every tool the course is verified against has a `Last verified` date there.

**Decision-change context:** This release reflects the 2026-05-08 swap of the free OSS AI agent from Aider to Gemini CLI. The Aider/OpenRouter cost path that appeared in earlier research (`./.planning/research/SUMMARY.md`) is superseded by `BUDGET.md` Path 2 (Gemini CLI free tier).
