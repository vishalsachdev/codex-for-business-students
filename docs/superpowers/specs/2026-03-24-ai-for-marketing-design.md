# Augmented Intelligence (AI) for Marketing Teams — Design Spec

**Date**: 2026-03-24
**Status**: Draft
**Author**: Vishal Sachdev
**Based on**: Codex for Business Students (codex-for-business-students repo)

---

## 1. Course Identity

**Name**: Augmented Intelligence (AI) for Marketing Teams

**Tagline**: "If you can write a brief, you can build a tool."

**Core message**: AI isn't a chatbot you visit — it's an intelligent coworker that reads your files, understands your context, and handles the tedious so you can focus on the creative and strategic. This course teaches you to work *with* AI, not just *talk to* it.

**Audience**: Gies College of Business marketing staff (22 people). Marketing professionals comfortable with tools like Google Workspace, Canva, Figma, CMS platforms, social schedulers. Not developers. Not afraid of technology, but haven't used a coding agent before.

**Primary tool**: OpenAI Codex. Course language is written to be tool-agnostic where possible (works with Claude Code, Cursor, or other agent tools with minor adjustments).

**Duration**: ~5 hours total across 4 modules.

**Delivery**: Facilitated workshop (recommended half-day) with a coordinated start. Staff clone the course repo, open it in Codex, and say "let's start." The root AGENTS.md acts as a Course Conductor that routes them through lessons. The coordinated start ensures the team reaches Module 1.8 (Team Sync) roughly together, which is essential for the collaboration and AHA moment. Modules 0-1.7 are self-paced within the workshop; 1.8 and beyond work best when the team is in sync.

---

## 2. The Scenario

**Real, not fictional.** The Gies marketing team is launching the MSBA Online program (Fall 2026). Brad Petersen (CMO) kicks off the course with a challenge brief:

> "Team — we're launching the MSBA Online program this fall. I need everyone up to speed on AI tools so we can move faster. The program materials are in our shared Box folder. I want each of you to spend a few hours with Codex learning what it can do for your specific role. By the end, I want to see what you built."

The materials they explore are the actual MSBA Online documents: strategy docs, competitive analysis, email threads, meeting notes, target profiles, curriculum plans. The training IS the work.

---

## 3. Team Roster

22-person team led by Brad Petersen (CMO), organized across functional areas:

| # | Name | Title | Office | Email |
|---|------|-------|--------|-------|
| 1 | Petersen, Brad | Chief Marketing Officer | 108 Wohlers Hall | bradp@illinois.edu |
| 2 | Bennett, Aaron | Director of Communications | 470 A Wohlers Hall | aaronb5@illinois.edu |
| 3 | Halfar, Lindsey | Director of Marketing | 120 Wohlers Hall | lsavoie@illinois.edu |
| 4 | Bhargava, Priyanka | Director of Insights & Strategy | 126 Wohlers Hall | pxb@illinois.edu |
| 5 | Mechling, Nicole | Creative Director | 470 H Wohlers Hall | nmechli2@illinois.edu |
| 6 | Pauley, Garrett | Director of Digital Media | 85 Wohlers Hall | gpauley2@illinois.edu |
| 7 | Onyejekwe, Kathleen | Director of Brand Engagement | 126 Wohlers Hall | kdj@illinois.edu |
| 8 | McDonald, Tyrone | Senior Director of Websites | — | troym@illinois.edu |
| 9 | Bednarz, Morgan | Asst. to CMO / Sr. Operations Specialist | — | mbednarz@illinois.edu |
| 10 | Campion, Alexandra | Assistant Director of Social Media | — | campiona@illinois.edu |
| 11 | White, Jeremy | Senior Project Manager | 111 Wohlers Hall | jeremyw@illinois.edu |
| 12 | White, Jordan | Associate Director of Brand Engagement | 220 D Wohlers Hall | jbonnell@illinois.edu |
| 13 | Hart, Andy | Brand Designer | 470 K Wohlers Hall | ajhart@illinois.edu |
| 14 | Cox, Jeremiah | Brand Photographer | — | jcox77@illinois.edu |
| 15 | Smith, Ryan | Video Producer | 85 Wohlers Hall | rsmith99@illinois.edu |
| 16 | Moone, Tom | Sr. Marketing Coordinator / Sr. Copywriter | 120 Wohlers Hall | moone@illinois.edu |
| 17 | Swim, Megan | Marketing Specialist | 126 Wohlers Hall | mswim2@illinois.edu |
| 18 | Elliott, Paul | Marketing Coordinator | 126 Wohlers Hall | elliott7@illinois.edu |
| 19 | Thurman, Jackson | Digital Marketing Coordinator | 120 Wohlers Hall | jtthurm2@illinois.edu |
| 20 | Gegg, Tyler | Web Content Specialist | 120 Wohlers Hall | tgegg@illinois.edu |
| 21 | Koon, Michael | Research Communications Coordinator | — | mkoon@illinois.edu |
| 22 | Moist, John | Research Communications Coordinator | — | — |

**Functional areas for team folders:**

| Folder | Team Members | Focus |
|--------|-------------|-------|
| competitive/ | Priyanka Bhargava | Insights & Strategy |
| messaging/ | Aaron Bennett | Communications |
| brand/ | Kathleen Onyejekwe, Jordan White, Andy Hart | Brand Engagement + Design |
| digital/ | Garrett Pauley, Alexandra Campion, Jackson Thurman | Digital/Social Media |
| web/ | Tyrone McDonald, Tyler Gegg | Websites |
| content/ | Nicole Mechling, Tom Moone | Creative/Copy |
| research-comms/ | Michael Koon, John Moist | Research Communications |
| media/ | Ryan Smith, Jeremiah Cox | Video/Photography |

Supporting roles (Brad, Morgan, Jeremy, Lindsey, Megan, Paul, Elliott) participate across areas based on their current projects.

---

## 4. Module Structure

### Module 0: Getting Started (15 min)

**0.1 Welcome & Setup**
- Install Codex, meet the Course Conductor
- Brad's brief: the MSBA Online launch challenge
- Verify Box Drive is synced and the shared folder is accessible
- Create local workspace: `~/marketing-workspace/`
- First-run init creates progress file at `~/.ai-for-marketing/progress.json`

### Module 1: Fundamentals — "The Brief" (2.5-3 hours)

**1.1 Your First Prompt**
- Open the MSBA Online materials via Box Drive
- Ask Codex to summarize the competitive landscape from strategy docs
- Key insight: Codex reads YOUR files, not the internet

**1.2 Exploring Context**
- Navigate the real materials: strategy docs, email threads, meeting notes
- Codex finds patterns across messy files that would take hours manually
- Staff see familiar names (their own colleagues!) in the email threads

**1.3 Working with Files**
- Create marketing deliverables from the source materials
- Competitive brief, audience persona, messaging matrix
- Uses templates from course repo's `templates/` directory
- "AI as associate, you as creative director"

**1.4 Parallel Agents**
- Launch simultaneous agents: one on competitive analysis, one on target profiles, one on pricing
- Everything runs simultaneously — "your team just got bigger"

**1.5 Custom Agents**
- Build role-specific agents: Brand Voice Checker, Campaign Brief Generator, Research Summarizer
- Pre-built agents in course repo's `agents/` directory as starting points
- Introduction to AGENTS.md as "giving AI your playbook"

**1.6 Project Memory**
- Write an AGENTS.md for the MSBA Online launch project
- Brand guidelines, target audience, key messages, team conventions
- AI remembers your context across sessions

**1.7 Connecting to Your Team's AI**
- Set up MCP connection to the MSBAi bot (verify with test query)
- Set up Box MCP connection (verify by searching knowledge-base folder)
- Exercise: use bot for target audience → Box for competitive analysis → write positioning brief combining both
- Key insight: "Your AI isn't one tool — it's connected to your team's entire knowledge network"

**1.8 Team Sync**
- Review what teammates produced in their functional areas (via Box)
- Co-create the shared AGENTS.md in `shared/` — team aligns on voice, audience, positioning
- **AHA moment**: each person's individual analysis reveals a different facet of the positioning challenge. When they see each other's work, the pieces click into a unified go-to-market narrative no single person could have produced alone.
- The MSBAi bot can now answer questions about everyone's work

**Sequencing note**: This lesson depends on teammates having completed Modules 1.1–1.7 and pushed artifacts to Box. **This course should be run as a facilitated session** (e.g., a half-day workshop) with a coordinated start so the team reaches 1.8 roughly together. The admin checklist includes pre-seeding 2-3 team folders with example outputs as a fallback for anyone who arrives at 1.8 early. The lesson script should also check whether team folders have content and, if sparse, prompt the learner to explore what's available and return to 1.8 after more teammates have finished.

### Module 2: Build — Split Track (1.5-2 hours)

Staff choose a track based on their role (guided by `reference/track-guide.md`).

**TRACK A: "Build a Tool"** (recommended for: web, digital, data-oriented roles)

- 2A.1 Project Setup — choose: campaign landing page, analytics dashboard, or social content calendar
- 2A.2 Planning Interview — Codex runs a Socratic planning session (goal, audience, MVP)
- 2A.3 Build & Iterate — describe what you want, Codex builds it, iterate on design and functionality. Codex reads from Box (via Box Drive or MCP) during the build to pull in real content (copy, data, brand assets) produced by the team.
- 2A.4 Ship It — deploy via Netlify Drop (drag build folder to app.netlify.com/drop), get a live URL. No account required for a one-off deploy; free Netlify account for a permanent URL.

**Important**: Track A tools are **static sites** (HTML/CSS/JS). They do not require a running agent or MCP connection at runtime. All content from Box is baked into the build at development time. Once deployed, the site stands alone.

**TRACK B: "Build a Workflow"** (recommended for: content, comms, research, creative roles)

- 2B.1 Workflow Setup — choose: content production pipeline, research digest automation, or campaign brief system
- 2B.2 Design the Workflow — map inputs → processing → outputs with Codex
- 2B.3 Build & Iterate — create the scripts, templates, and AGENTS.md that power it
- 2B.4 Demo It — run the workflow end-to-end, save output to Box builds/ folder

Workflow pulls from Box knowledge-base/ as input — real materials, real output.

### Module 3: Capstone — "Show Brad" (30-45 min)

**3.1 Your Deliverable**
- Build something for your actual role using what you learned
- Codex reads the full shared Box folder — everything the team produced
- Short write-up: what you built, how it helps, what you'd do next

**3.2 Team Showcase**
- MSBAi bot synthesizes the team's combined output
- "Here's what 22 people built in 5 hours with AI"
- Brad gets a real go-to-market package, not a training exercise

---

## 5. Architecture

### Course Repo (GitHub)

```
ai-for-marketing/
├── AGENTS.md                              # Course Conductor
├── course-structure.json                  # Machine-readable lesson index
├── README.md                              # Setup instructions
│
├── lesson-modules/
│   ├── 0-getting-started/
│   │   └── 0.1-welcome/AGENTS.md
│   ├── 1-fundamentals/
│   │   ├── 1.1-first-prompt/AGENTS.md
│   │   ├── 1.2-exploring-context/AGENTS.md
│   │   ├── 1.3-working-with-files/AGENTS.md
│   │   ├── 1.4-parallel-agents/AGENTS.md
│   │   ├── 1.5-custom-agents/AGENTS.md
│   │   ├── 1.6-project-memory/AGENTS.md
│   │   ├── 1.7-team-ai/AGENTS.md
│   │   └── 1.8-team-sync/AGENTS.md
│   ├── 2-build/
│   │   ├── track-a-tool/
│   │   │   ├── 2a.1-setup/AGENTS.md
│   │   │   ├── 2a.2-planning/AGENTS.md
│   │   │   ├── 2a.3-build/AGENTS.md
│   │   │   └── 2a.4-ship/AGENTS.md
│   │   └── track-b-workflow/
│   │       ├── 2b.1-setup/AGENTS.md
│   │       ├── 2b.2-design/AGENTS.md
│   │       ├── 2b.3-build/AGENTS.md
│   │       └── 2b.4-demo/AGENTS.md
│   └── 3-capstone/
│       ├── 3.1-your-deliverable/AGENTS.md
│       └── 3.2-team-showcase/AGENTS.md
│
├── reference/
│   ├── team-roster.md                     # Full team with titles, emails
│   ├── mcp-setup.md                       # MSBAi bot + Box MCP connection guide
│   └── track-guide.md                     # "Which track is right for me?" by role
│
├── templates/
│   ├── competitive-brief.md
│   ├── audience-persona.md
│   ├── messaging-matrix.md
│   ├── campaign-brief.md
│   └── workflow-template.md
│
├── agents/                                # Pre-built custom agents for Module 1.5
│   ├── brand-voice-checker.md
│   ├── campaign-strategist.md
│   └── research-summarizer.md
│
└── docs/                                  # Landing page (GitHub Pages, optional)
    ├── index.html
    └── styles.css
```

### Box Shared Folder (pre-provisioned by admin)

```
Box / Gies Marketing / MSBA Online Launch/
├── knowledge-base/                        # Curated MSBA Online materials (read-only)
│   ├── strategy/                          #   AI_FIRST_STRATEGY, COMPETITIVE_ANALYSIS
│   ├── program/                           #   CURRICULUM, TARGET_PROFILE, DESIGN_PRINCIPLES
│   ├── discussions/                       #   Key email threads, meeting notes
│   └── README.md                          #   "What's in here and how to use it"
│
├── shared/                                # Team-wide assets
│   ├── AGENTS.md                          #   Shared project memory (co-created in 1.8)
│   ├── brand-guidelines.md
│   └── messaging-pillars.md
│
├── team/                                  # One folder per functional area
│   ├── competitive/
│   ├── messaging/
│   ├── brand/
│   ├── digital/
│   ├── web/
│   ├── content/
│   ├── research-comms/
│   └── media/
│
└── builds/                                # Module 2 + 3 outputs
    ├── tools/                             #   Track A builds
    └── workflows/                         #   Track B outputs
```

### Local Workspace (created on first run)

```
~/marketing-workspace/
├── box-sync → <Box Drive mount path>/Gies Marketing/MSBA Online Launch/
└── project/                               # Module 2 build workspace (local)
```

**Box Drive path detection**: Box Drive mounts at different paths depending on OS and version:
- macOS (modern): `~/Library/CloudStorage/Box-Box/`
- macOS (legacy Box Sync): `~/Box/`
- Windows: `C:\Users\<name>\Box\`

The first-run init script in Module 0.1 must detect the correct path before creating the symlink. If Box Drive is not installed, fall back to using Box MCP exclusively for file access (no symlink needed — Codex reads/writes via MCP tools instead of filesystem).

### Progress Tracking

`~/.ai-for-marketing/progress.json` — stored in home directory, survives repo re-clones.

### Course Structure (course-structure.json)

The `course-structure.json` must include all 19 lessons across both tracks:

| ID | Title | Est. Minutes |
|----|-------|-------------|
| 0.1 | Welcome & Setup | 15 |
| 1.1 | Your First Prompt | 20 |
| 1.2 | Exploring Context | 25 |
| 1.3 | Working with Files | 30 |
| 1.4 | Parallel Agents | 25 |
| 1.5 | Custom Agents | 30 |
| 1.6 | Project Memory | 20 |
| 1.7 | Connecting to Your Team's AI | 25 |
| 1.8 | Team Sync | 20 |
| 2a.1 | Project Setup (Track A) | 20 |
| 2a.2 | Planning Interview (Track A) | 25 |
| 2a.3 | Build & Iterate (Track A) | 30 |
| 2a.4 | Ship It (Track A) | 15 |
| 2b.1 | Workflow Setup (Track B) | 20 |
| 2b.2 | Design the Workflow (Track B) | 25 |
| 2b.3 | Build & Iterate (Track B) | 30 |
| 2b.4 | Demo It (Track B) | 15 |
| 3.1 | Your Deliverable | 30 |
| 3.2 | Team Showcase | 15 |

Progress tracking only records lessons from the chosen track (A or B), not both. The Course Conductor asks which track at the start of Module 2 and records the choice in progress.json.

---

## 6. MCP Integration

### Connection 1: MSBAi Bot

The nanoclaw-msbai bot has a web chat endpoint (`POST /chat`). Wrapped as an MCP server so Codex can query the MSBA Online knowledge base conversationally.

**Use cases:**
- "What decisions have been made about pricing?"
- "What does the competitive analysis say about Georgia Tech?"
- "Summarize the target audience profile"

**Setup:** Pre-configured endpoint URL + auth token, distributed with API keys. Lesson 1.7 walks through verifying the connection.

### Connection 2: Box MCP

Box MCP tools (`mcp__claude_ai_Box__*`) provide direct file access: search, read, write, upload.

**Use cases:**
- "Find the latest competitive brief in the team folder"
- "Read what Aaron posted in messaging/"
- "Save my analysis to team/digital/"

**Setup:** Staff authenticate with Illinois credentials. Lesson 1.7 walks through setup.

### How the two MCPs complement each other

| Need | Use | Why |
|------|-----|-----|
| Conversational knowledge query | MSBAi bot | Searches full knowledge base, returns citations |
| Direct file access | Box MCP | Read/write specific team artifacts |
| Save work for team visibility | Box MCP or Box Drive sync | Artifacts appear in shared folder |
| Cross-team synthesis | MSBAi bot or Codex via Box Drive | Combine outputs from multiple team folders |

---

## 7. Admin Setup Checklist

Pre-training provisioning (done by Vishal):

```
□ Box shared folder
  └── Create full folder structure via Box MCP
  └── Populate knowledge-base/ with curated MSBA Online materials
  └── Set permissions: read-write on team/ and builds/, read-only on knowledge-base/
  └── Add starter AGENTS.md in shared/

□ MSBAi bot
  └── Endpoint accessible to team
  └── Auth tokens generated (per-person or shared team token)
  └── Web chat endpoint tested

□ Course repo
  └── ai-for-marketing/ on GitHub
  └── MCP config templates in reference/mcp-setup.md
  └── Team roster in reference/team-roster.md
  └── Pre-built agents in agents/
  └── Templates in templates/

□ API keys
  └── OpenAI API keys (one per person or shared pool)
  └── Distributed separately from course materials

□ Netlify
  └── Instructions for free accounts (Track A participants only)
  └── URL: app.netlify.com/drop (no account needed for one-off deploys)

□ Pre-seed team folders
  └── Populate 2-3 team/ subfolders with example outputs (e.g., a sample competitive brief,
      a draft audience persona) so early finishers at Lesson 1.8 see content

□ Verify Box Drive mount paths
  └── Test on macOS (~/Library/CloudStorage/Box-Box/) and Windows (C:\Users\<name>\Box\)
  └── Confirm the course init script detects the correct path

□ Brad's brief
  └── Written and placed in Box shared folder
  └── Optional: Brad records a 2-min video or sends email to team
```

---

## 8. Key Design Decisions

1. **Real scenario, not fictional.** The MSBA Online launch provides authentic materials and a real challenge. The training produces real deliverables.

2. **Box over GitHub for collaboration.** Marketing teams live in Box. Eliminates git friction. Box Drive provides local filesystem access that Codex reads natively.

3. **Split track in Module 2.** Web/digital folks build tools (Track A). Content/comms folks build workflows (Track B). Everyone gets value from their role's perspective.

4. **Two MCP connections.** MSBAi bot for conversational knowledge queries. Box MCP for direct file access. Together they form a "team AI network."

5. **Netlify Drop for deploys.** Drag-and-drop deployment for Track A. No git required.

6. **Tool-agnostic language.** Primary target is OpenAI Codex. Scripts avoid Codex-specific terminology where possible so the course works with Claude Code, Cursor, or other agent tools.

7. **Markdown for deliverables.** AI works best with plain text. Staff draft in markdown with Codex, convert to polished formats as needed. CSV for spreadsheet use cases.

8. **The training IS the work.** Brad gets real go-to-market artifacts at the end, not throwaway exercises. The AHA moment in Module 1.8 is when the team sees how individual analyses combine into a unified narrative.

---

## 9. Differences from Student Course

| Aspect | Student Course | Marketing Course |
|--------|---------------|-----------------|
| Scenario | Fictional (NovaBrew Coffee Co.) | Real (MSBA Online launch) |
| Audience | Business students, zero experience | Marketing professionals, tool-savvy |
| Collaboration | Individual only | Team-based with shared Box folder |
| File storage | Local filesystem + GitHub | Box Drive + local workspace |
| MCP integrations | None | MSBAi bot + Box |
| Build module | Single track (build an app) | Split: Build a Tool vs. Build a Workflow |
| Deploy target | GitHub Pages | Netlify Drop (Track A only) |
| Version control | Git taught as a module | Not required |
| Capstone | Portfolio piece + case study | Team deliverable for Brad |
| AHA moment | Individual insight (Coffee Quiz) | Team synthesis (unified go-to-market) |
| Course Conductor tone | "Smart friend, never condescending" | Same, but uses marketing language natively |

---

## 10. Lesson Script Conventions

Same pattern as student course:

- **Say:** blocks — dialogue spoken to the learner (warm, marketing-savvy, never developer jargon)
- **STOP:** blocks — pause and wait for learner response
- **ACTION:** blocks — instructions for Codex to execute (run commands, create files, etc.)
- **Important Notes for Codex** — tone, pacing, recovery guidance
- **Success Criteria** — checklist before moving to next lesson

Additional conventions for this course:
- Reference team members by name where relevant ("Let's see what Priyanka's team found...")
- Use marketing language naturally (campaigns, briefs, assets, deliverables — not repos, commits, endpoints)
- Frame technical concepts with marketing analogies ("AGENTS.md is like a brand book for your AI")
- Never break character. The Course Conductor is a marketing-savvy AI trainer.
