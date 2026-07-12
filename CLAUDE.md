# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

An interactive course ("Codex for Business") delivered through AI agent scripts. Students open this repo in OpenAI's ChatGPT desktop app (Codex mode) and say "let's start" — the root `AGENTS.md` acts as a course conductor that routes them through lessons. Not a traditional code project; no build step, no package.json, no tests.

## Architecture

- **`AGENTS.md`** (root) — Course conductor. Manages lesson routing, progress tracking (`~/.codex-for-business/progress.json`), and workspace init (`~/novabrew-workspace/`).
- **`lesson-modules/`** — 16 lessons across 4 modules (0-3), each an `AGENTS.md` file. There are 14 required lessons plus 2 optional bonus lessons. Modules: Getting Started → Fundamentals → Vibe Coding → Capstone.
- **`business-scenario/`** — NovaBrew Coffee Co. case study data (read-only). Students discover these files during Module 1.
- **`templates/`** — Reusable business frameworks (BMC, competitive analysis, pitch deck, case study).
- **`docs/`** — Landing page (static HTML + CSS). Deployed via GitHub Actions to GitHub Pages.
- **`course-structure.json`** — Machine-readable lesson index with paths, descriptions, and timing estimates.

## Deployment

**Landing page**: GitHub Pages serves `docs/` from the `main` branch. Pushes to `main` update the public site after Pages rebuilds.

**Student apps** (built during lessons 2.5 and 3.1) deploy to GitHub Pages via static export (`output: 'export'` in next.config) published to a `gh-pages` branch.

## Lesson Script Conventions

Each `AGENTS.md` follows this pattern:
- **Say:** blocks — dialogue spoken to the student (warm, business-focused, never developer jargon)
- **STOP:** blocks — pause and wait for student response
- **ACTION:** blocks — instructions for Codex to execute (run commands, create files, etc.)
- **Important Notes for Codex** — tone, pacing, recovery guidance
- **Success Criteria** — checklist before moving to next lesson

Key rules: never break character, never use CS jargon without a business analogy, never spoil NovaBrew discoveries (let students find patterns themselves).

## Common Edits

**Updating lesson content**: Edit the `AGENTS.md` in the relevant `lesson-modules/X.Y-slug/` directory. Keep timing estimates in `course-structure.json` in sync.

**Updating landing page**: Edit `docs/index.html` and `docs/styles.css`. No build step — just push to main and GitHub Pages auto-deploys.

**Adding a new lesson**: Create a new directory under the appropriate module, add an `AGENTS.md` following the existing pattern, and add the entry to `course-structure.json`. Update the root `AGENTS.md` lesson routing table.

## Gotchas

- Student deploy instructions use GitHub Pages with static export. Lessons publish the generated `out/` folder to a dedicated `gh-pages` branch using `npx gh-pages -d out -b gh-pages --dotfiles`, instead of committing `out/` to `main`.
- `basePath` in student next.config must match their GitHub repo name exactly, or the deployed site 404s.
- The `.nojekyll` file in `out/` is critical — without it GitHub Pages ignores `_next/` directories (site loads unstyled, buttons dead). `npx gh-pages` drops dotfiles unless you pass `--dotfiles`, so `touch out/.nojekyll` alone is NOT enough — the flag is mandatory. Verified end-to-end 2026-06-23.

## Current Focus

Preparing for in-class use. The class-blocking deploy path (Lessons 2.4→2.5) is verified end-to-end, and setup copy is updated for OpenAI's July 2026 Codex→ChatGPT-desktop-app merger (Codex is now a mode inside the ChatGPT app). Remaining before class is optional: a GitHub Actions workflow for student projects (deferred), then collecting first-round student feedback.

## Roadmap

- [x] Replace Vercel with GitHub Pages as student deployment target
- [x] Fix UX issues in deploy flow (gitignore, basePath verification, messaging)
- [x] Refresh course materials for current Codex docs and make workspace separation explicit on the site
- [x] End-to-end test: run a fresh student through Lessons 2.4 → 2.5 to verify GitHub Pages deploy works (found + fixed missing `--dotfiles` deploy bug)
- [x] Update setup copy for the July 2026 Codex→ChatGPT-desktop-app merger (Codex is now a mode inside the ChatGPT app)
- [ ] Add GitHub Actions workflow for student projects (eliminate local `npm run build` requirement)
- [ ] Collect first round of student feedback and iterate on pain points

## Session Log

### 2026-07-12
- Completed: Researched OpenAI's 2026-07-09 Codex→ChatGPT-desktop-app merger (Codex is now a mode alongside Chat and Work; existing Codex users just update; still free-plan-included). Updated student-facing setup copy across the welcome lesson, README, landing page (`docs/index.html`), SPEC, and file-exploration lesson to point at the ChatGPT desktop app + Codex mode and tell students to select the Codex tab. Kept the "this conversation IS Codex" hook and free-plan claims. Committed + pushed to `main`; GitHub Pages redeployed successfully.
- Cross-project: Applied the same terminology fix to the `ai-for-marketing` course (README + landing page) and saved a reusable "Codex→ChatGPT-app terminology" checklist to auto-memory (`reference_codex_chatgpt_app_merger.md`).
- Next: Optional pre-class item still deferred — decide manual-vs-GitHub-Actions deploy for student projects, then build the workflow.

*Older entries archived to `docs/session-archive.md`.*
