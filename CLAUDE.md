# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

An interactive course ("Codex for Business") delivered through AI agent scripts. Students open this repo in OpenAI's Codex desktop app and say "let's start" — the root `AGENTS.md` acts as a course conductor that routes them through lessons. Not a traditional code project; no build step, no package.json, no tests.

## Architecture

- **`AGENTS.md`** (root) — Course conductor. Manages lesson routing, progress tracking (`~/.codex-for-business/progress.json`), and workspace init (`~/novabrew-workspace/`).
- **`lesson-modules/`** — 14 lessons across 4 modules (0-3), each an `AGENTS.md` file. Modules: Getting Started → Fundamentals → Vibe Coding → Capstone.
- **`business-scenario/`** — NovaBrew Coffee Co. case study data (read-only). Students discover these files during Module 1.
- **`templates/`** — Reusable business frameworks (BMC, competitive analysis, pitch deck, case study).
- **`docs/`** — Landing page (static HTML + CSS). Deployed via GitHub Actions to GitHub Pages AND manually to Vercel at `codex-for-business.vercel.app`.
- **`course-structure.json`** — Machine-readable lesson index with paths, descriptions, and timing estimates.

## Deployment

**Landing page** has two deploy targets:
- **GitHub Pages**: Auto-deploys from `docs/` on push to main (`.github/workflows/pages.yml`)
- **Vercel**: Manual deploy — `cd docs && vercel --prod`, then alias to `codex-for-business.vercel.app`

**Student apps** (built during lessons 2.5 and 3.1) deploy to GitHub Pages via static export (`output: 'export'` in next.config).

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

**Updating landing page**: Edit `docs/index.html` and `docs/styles.css`. No build step — just push to main (GitHub Pages auto-deploys) and run `cd docs && vercel --prod` for Vercel.

**Adding a new lesson**: Create a new directory under the appropriate module, add an `AGENTS.md` following the existing pattern, and add the entry to `course-structure.json`. Update the root `AGENTS.md` lesson routing table.

## Gotchas

- The `docs/.vercel/` directory is gitignored — it holds local Vercel project config. If deleted, re-link with `cd docs && vercel link --yes`.
- Student deploy instructions use GitHub Pages with static export. The default `create-next-app` `.gitignore` excludes `/out/` — lessons explicitly remove that line before committing.
- `basePath` in student next.config must match their GitHub repo name exactly, or the deployed site 404s.
- The `.nojekyll` file in `out/` is critical — without it GitHub Pages ignores `_next/` directories.

## Current Focus

Replace Vercel with GitHub Pages for student deployments — completed.

## Roadmap

- [x] Replace Vercel with GitHub Pages as student deployment target
- [x] Fix UX issues in deploy flow (gitignore, basePath verification, messaging)
- [ ] End-to-end test: run a fresh student through Lessons 2.4 → 2.5 to verify GitHub Pages deploy works
- [ ] Add GitHub Actions workflow for student projects (eliminate local `npm run build` requirement)
- [ ] Collect first round of student feedback and iterate on pain points

## Session Log

### 2026-02-26
- Completed: Replaced Vercel with GitHub Pages across 8 files, fixed 6 UX issues (gitignore, auto-deploy messaging, capstone ordering, basePath verification, README template, landing page copy), deployed landing page to Vercel
- Next: End-to-end test of the deploy flow with a fresh student walkthrough
