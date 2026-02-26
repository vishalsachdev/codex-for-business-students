# Codex for Business

**If you can pitch it, you can build it.**

[![Works on FREE ChatGPT plan](https://img.shields.io/badge/Works%20on-FREE%20ChatGPT%20plan-00A67E?style=for-the-badge&logo=openai&logoColor=white)](https://chatgpt.com)

A hands-on course that teaches business students, PMs, and aspiring founders how to use OpenAI's Codex CLI to turn ideas into working prototypes — without writing a single line of code.

---

## Quick Start

```bash
# 1. Install Codex CLI
npm install -g @openai/codex

# 2. Clone this course
git clone https://github.com/YOUR_USERNAME/codex-for-business-students.git
cd codex-for-business-students

# 3. Start the first lesson
codex
# Then just say: "let's start"
```

---

## What You'll Build

You play a **strategy consultant** for NovaBrew Coffee Co., a real-feeling startup with messy data, board pressure, and 8 months of runway. Every lesson uses NovaBrew as your sandbox. By the end, you'll have:

- Synthesized chaotic meeting notes into an actionable brief
- Run parallel market research, financial modeling, and competitive analysis
- Built custom AI agents (VC Pitch Coach, Competitor Intel, Go-to-Market Strategist)
- Shipped a working web app — deployed with a live URL
- A portfolio-ready case study for your resume or LinkedIn

---

## Course Modules

| # | Module | Time | What You'll Do |
|---|--------|------|----------------|
| **0** | **Getting Started** | 10 min | Install Codex, meet NovaBrew, run your first prompt |
| **1.1** | Your First Business Prompt | 20 min | Process inherited PM notes, learn how Codex reads/writes files |
| **1.2** | File Exploration & Context | 25 min | Parse meeting notes, earnings transcripts, survey data |
| **1.3** | Working with Business Files | 30 min | Create financial models, customer analyses, strategy docs |
| **1.4** | Parallel Agents | 25 min | Launch 3 agents simultaneously on NovaBrew's retention problem |
| **1.5** | Custom Agents & Skills | 30 min | Build reusable business agents with AGENTS.md and Skills |
| **1.6** | Project Memory | 20 min | Give Codex persistent context about your business |
| **1.7** | What's Next | 10 min | Review fundamentals, prepare for vibe coding |
| **2.1** | Project Setup | 20 min | Choose your project and scaffold it |
| **2.2** | The Planning Interview | 25 min | Codex runs a Socratic planning session like a senior PM |
| **2.3** | Build & Iterate | 30 min | Describe features in plain English, watch them appear |
| **2.4** | GitHub & Version Control | 15 min | Push to GitHub with a professional README |
| **2.5** | Deploy & Go Live | 15 min | Ship to Vercel — get a live URL for your portfolio |
| **3.1** | Capstone Project | 45 min | Build your own project, write a case study, export portfolio assets |
| | **Total** | **~5.5 hrs** | |

---

## Prerequisites

- A computer (Mac, Windows, or Linux)
- [Node.js](https://nodejs.org/) installed (v18 or later)
- A free [OpenAI account](https://platform.openai.com/) (or ChatGPT Plus for faster responses)
- A free [GitHub account](https://github.com/) (for deploying your project)
- **Zero coding experience required** — just business thinking

---

## Who This Is For

- MBA and undergrad business students
- Product managers and aspiring PMs
- Finance, marketing, and ops analysts
- Non-technical founders and side-hustlers
- Anyone who wants to prototype MVPs without waiting for engineers

---

## Project Structure

```
codex-for-business-students/
├── lesson-modules/          # All course lessons (AGENTS.md in each folder)
│   ├── 0-getting-started/
│   ├── 1-fundamentals/
│   ├── 2-vibe-coding/
│   └── 3-capstone/
├── business-scenario/       # NovaBrew company files (the "inherited chaos")
├── templates/               # Reusable business templates
├── docs/                    # Course website (GitHub Pages)
├── course-structure.json    # Machine-readable course outline
└── SPEC.md                  # Course design specification
```

---

## Templates Included

The `templates/` folder contains ready-to-use frameworks:

- **Business Model Canvas** — Standard 9-block format with guided prompts
- **Competitive Analysis** — 5-competitor comparison matrix
- **Pitch Deck Outline** — 10-slide investor deck structure
- **One-Page Case Study** — Portfolio-ready project writeup

Each template includes instructions for how to use it with Codex.

---

## Credits

Inspired by [Claude Code for Everyone](https://www.yourfirstcursor.com/) by Carl Vellotti — the original (and excellent) course that teaches AI-assisted development inside the tool itself. This version adapts the concept for business students using OpenAI's Codex CLI.

---

## License

MIT License. See [LICENSE](LICENSE) for details.

Use this course, remix it, teach it. Just build something.
