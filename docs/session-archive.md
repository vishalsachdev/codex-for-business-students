# Session Archive

Older session-log entries moved out of `CLAUDE.md` to keep it concise. claude-mem stores the full session history; this file is a human-readable backup of past entries.

### 2026-06-23
- Completed: Committed in-Codex refinements to Module 0–1 lesson scripts (Course Conductor deference + progress.json tracking, "use real files / label samples" guidance, nuanced campaign narrative, Module 2 decoupled from the hardcoded quiz). Replaced the dead Carl Vellotti course links (`carlvellotti/claude-code-for-everyone` 404, `yourfirstcursor.com` unreachable) with `https://ccforeveryone.com/` across the landing page, README, and launch article after a full link check of the public site.
- Verified + fixed: Ran the Lessons 2.4→2.5 end-to-end walkthrough with a real throwaway Next.js quiz and public repo (`novabrew-quiz-deploytest`, deployed live, confirmed fully interactive in-browser, then cleaned up locally). Caught a ship-blocking deploy bug — `npx gh-pages` drops `.nojekyll` without `--dotfiles`, so Jekyll stripped `_next/` and every deployed student site loaded unstyled with dead buttons. Added `--dotfiles` to both 2.5 commands and the capstone 3.1, documented the symptom/verification, and updated the CLAUDE.md gotcha.
- Next: Optional pre-class item deferred — decide manual-vs-GitHub-Actions deploy for student projects, then build the workflow. (Throwaway test repo `novabrew-quiz-deploytest` has been deleted.)

### 2026-06-18
- Completed: Refreshed Codex for Business course materials for current Codex docs and pushed/deployed the public site. Updated language around Free plan inclusion, skills/plugins/subagents, AGENTS.md behavior, explicit approval before external actions, and student GitHub Pages deployment via `gh-pages`. Added optional 3.3 innermost-loop lesson, bumped course version to 1.1.0, and made clear that student artifacts live in `~/novabrew-workspace/` outside the course repo.
- Verified: Course structure is valid (16 lessons, 265 core minutes + 28 optional), landing page renders on desktop/mobile, GitHub Pages rebuilt from `main:/docs`, and live site includes the workspace-separation message.
- Next: Run a fresh end-to-end student walkthrough through Lessons 2.4 → 2.5 to confirm the new deployment flow works in student conditions.

### 2026-04-05
- Reviewed roadmap for in-class readiness. Deleted stale `.claude/plans/cloudflare-migration.md` (referenced MkDocs, no longer relevant). Identified 3 pre-class priorities: end-to-end walkthrough (2.4→2.5), smoke test of Lesson 0→1.1, and verify Mar 27 curriculum changes in Codex.
- Next: Run the end-to-end student walkthrough. Decide on GitHub Actions workflow for student projects (nice-to-have vs must-have for class).

### 2026-03-27
- Completed: Curriculum update for Codex changes. Four changes across 6 files:
  1. **Fixed 1.6** — Students now create `~/novabrew-workspace/AGENTS.md` (not `novabrew-agents.md`). Removed false claim about automatic reading of non-AGENTS.md files. Clear framing: AGENTS.md at workspace root = auto-read.
  2. **Rewrote 1.5** — New title "Advisors, Skills & Plugins." Step 1 teaches the three-role model. Step 5 explains all three with cheat sheet table. Advisory team review + AHA moment unchanged.
  3. **Refreshed 2.4** — GitHub framed as "back up and share." Built-in GitHub connection is easy path; `gh` CLI is fallback.
  4. **Added 3.2 Canva bonus** — Optional lesson for turning finished project into case study, deck, or LinkedIn asset. Not part of main build path.
- Also updated: course-structure.json (titles, descriptions, new 3.2 entry), root AGENTS.md (course map, workspace paths, timing).
- Propagated: Added roadmap note in ai-for-marketing CLAUDE.md to consider advisors/skills/plugins update for 1.5 during pilot run.

### 2026-03-24
- Completed: Designed and built "Augmented Intelligence (AI) for Marketing Teams" — a new course for Brad Petersen's 22-person marketing team at Gies. Full brainstorm → spec → council review (4 agents: copywriter, learning designer, tech architect, CMO) → parallel implementation (7 agents). Course repo at `/Users/vishal/teaching/ai-for-marketing/` with 38 files, 7K lines. Uses real MSBA Online materials, Box for collaboration, MSBAi bot MCP, split build tracks, Netlify Drop for deploys. Design spec saved at `docs/superpowers/specs/2026-03-24-ai-for-marketing-design.md`.
- Next: Box folder provisioning (via MCP), knowledge-base curation from msba-online, test setup-connections.sh, pilot run simulating a staff member, push ai-for-marketing to GitHub.

### 2026-03-23
- Completed: Maintenance pass for public visitors. Added Windows support across all files (6 files). Removed Vercel deployment (deleted both projects), consolidated to GitHub Pages only. Redesigned landing page with Canvas MCP color theme (Clash Display + DM Sans, teal accent, glass cards, grid backgrounds, entry animations).
- Next: End-to-end test of the deploy flow with a fresh student walkthrough

### 2026-02-26
- Completed: Replaced Vercel with GitHub Pages across 8 files, fixed 6 UX issues (gitignore, auto-deploy messaging, capstone ordering, basePath verification, README template, landing page copy), deployed landing page to Vercel
- Next: End-to-end test of the deploy flow with a fresh student walkthrough
