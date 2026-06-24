# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

An interactive course ("Codex for Business") delivered through AI agent scripts. Students open this repo in OpenAI's Codex desktop app and say "let's start" — the root `AGENTS.md` acts as a course conductor that routes them through lessons. Not a traditional code project; no build step, no package.json, no tests.

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

Preparing for in-class use. The class-blocking deploy path (Lessons 2.4→2.5) is now verified end-to-end. Remaining before class is optional: a GitHub Actions workflow for student projects (deferred), then collecting first-round student feedback.

## Roadmap

- [x] Replace Vercel with GitHub Pages as student deployment target
- [x] Fix UX issues in deploy flow (gitignore, basePath verification, messaging)
- [x] Refresh course materials for current Codex docs and make workspace separation explicit on the site
- [x] End-to-end test: run a fresh student through Lessons 2.4 → 2.5 to verify GitHub Pages deploy works (found + fixed missing `--dotfiles` deploy bug)
- [ ] Add GitHub Actions workflow for student projects (eliminate local `npm run build` requirement)
- [ ] Collect first round of student feedback and iterate on pain points

## Session Log

### 2026-06-23
- Completed: Committed in-Codex refinements to Module 0–1 lesson scripts (Course Conductor deference + progress.json tracking, "use real files / label samples" guidance, nuanced campaign narrative, Module 2 decoupled from the hardcoded quiz). Replaced the dead Carl Vellotti course links (`carlvellotti/claude-code-for-everyone` 404, `yourfirstcursor.com` unreachable) with `https://ccforeveryone.com/` across the landing page, README, and launch article after a full link check of the public site.
- Verified + fixed: Ran the Lessons 2.4→2.5 end-to-end walkthrough with a real throwaway Next.js quiz and public repo (`novabrew-quiz-deploytest`, deployed live, confirmed fully interactive in-browser, then cleaned up locally). Caught a ship-blocking deploy bug — `npx gh-pages` drops `.nojekyll` without `--dotfiles`, so Jekyll stripped `_next/` and every deployed student site loaded unstyled with dead buttons. Added `--dotfiles` to both 2.5 commands and the capstone 3.1, documented the symptom/verification, and updated the CLAUDE.md gotcha.
- Next: Optional pre-class item deferred — decide manual-vs-GitHub-Actions deploy for student projects, then build the workflow. (Throwaway test repo `novabrew-quiz-deploytest` has been deleted.)

*Older entries archived to `docs/session-archive.md`.*
