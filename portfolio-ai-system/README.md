# Portfolio AI System

A portfolio strategy, audit, and rewrite system for job applications at Staff / Principal level.

Evaluates portfolios as products competing for hiring decisions. Runs a 7-step workflow: intent definition, issue diagnosis, goal alignment, hiring simulation, UX/QA check, rewrite, and execution plan.

---

## Files

| File | Description |
|---|---|
| `portfolio-ai-system.md` | Main skill file -- install this |
| `portfolio-audit-workflow.md` | Full 7-step audit workflow (standalone) |
| `skills/hiring-simulation-skill.md` | 4-perspective hiring simulation with interview verdicts |
| `skills/homepage-rewrite-skill.md` | Headline, subtext, CTA, and section label rewrites |
| `skills/mobile-qa-skill.md` | 375px mobile responsiveness and overflow QA checklist |
| `skills/portfolio-consistency-skill.md` | Extracts positioning, tone, and structure patterns for cross-page consistency |
| `skills/portfolio-execution-skill.md` | Executes audit findings and rewrites directly to portfolio files — produces a change log |

---

## Install

```bash
cp portfolio-ai-system.md ~/.claude/commands/portfolio-ai-system.md
```

Individual skills can be copied separately and invoked independently:

```bash
cp skills/hiring-simulation-skill.md ~/.claude/commands/hiring-simulation-skill.md
cp skills/homepage-rewrite-skill.md ~/.claude/commands/homepage-rewrite-skill.md
cp skills/mobile-qa-skill.md ~/.claude/commands/mobile-qa-skill.md
cp skills/portfolio-consistency-skill.md ~/.claude/commands/portfolio-consistency-skill.md
cp skills/portfolio-execution-skill.md ~/.claude/commands/portfolio-execution-skill.md
```

---

## Usage

```
/portfolio-ai-system audit [portfolio URL or folder]
```

| Command | Use |
|---|---|
| `/portfolio-ai-system audit [portfolio]` | Full 7-step audit |
| `/portfolio-ai-system rewrite [section]` | Rewrite a specific section |
| `/portfolio-ai-system qa [site/folder]` | Links, logic, structure check |
| `/portfolio-ai-system mobile [page]` | Responsive and overflow check |
| `/portfolio-ai-system hiring [portfolio]` | Hiring simulation only |
| `/portfolio-ai-system learn-site [existing pages]` | Extract consistency guide from current site |
| `/portfolio-ai-system consistency-check [new page]` | Check a new page against the site's established patterns |

Individual skills:

| Command | Use |
|---|---|
| `/hiring-simulation-skill [portfolio]` | 4-perspective hiring simulation |
| `/homepage-rewrite-skill [page]` | Homepage copy rewrite |
| `/mobile-qa-skill [page]` | Mobile QA checklist |
| `/portfolio-consistency-skill [portfolio]` | Extract consistency guide for new pages |
| `/portfolio-execution-skill [audit output or page]` | Execute fixes directly to portfolio files |

---

## The 7-Step Workflow

| # | Step | What It Does |
|---|---|---|
| 1 | Define Intent | Establish what the portfolio is trying to communicate |
| 2 | Diagnose Issues | Evaluate positioning, content, structure, and storytelling |
| 3 | Goal Alignment | Define what must be communicated in 10 seconds |
| 4 | Hiring Simulation | Simulate review from Recruiter, Manager, Design Leader, AI Leader |
| 5 | UX / QA / Mobile Check | Scanning, navigation, links, mobile responsiveness |
| 6 | Rewrite & Improvement | Exact before/after rewrites for homepage, CTAs, copy |
| 7 | Execution Plan | Immediate fixes, short-term improvements, structural changes |

---

## End Deliverable

Full audit report including:

- Hiring verdict per role (Yes / No / Conditional)
- Exact before/after copy rewrites
- Mobile issue list with fixes
- Prioritized execution plan (immediate / short-term / structural)
- Overall score: how competitive at Staff/Principal level
