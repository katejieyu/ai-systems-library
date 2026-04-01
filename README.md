# AI Systems

A collection of structured, skill-based reasoning systems built for Claude Code. Each system runs your input through a defined chain of skills and produces specific, decision-quality outputs.

Built by Kate Jie Yu.

---

## Structure

```
ai-systems/
  README.md

  portfolio-ai-system/
    README.md
    portfolio-ai-system.md
    portfolio-audit-workflow.md
    skills/
      hiring-simulation-skill.md
      homepage-rewrite-skill.md
      mobile-qa-skill.md
      portfolio-consistency-skill.md

  product-ai-system/
    README.md
    ai-system.md
```

---

## Systems

### 1. Product AI System (`/product-ai-system`)

A structured product reasoning engine for designers, PMs, and engineers.

Moves product work from raw problem to execution-ready output through a 9-skill chain. Does not agree with your framing. Surfaces contradictions, flags assumptions, and forces decisions before they become blockers in engineering.

**Skill file:** `product-ai-system/ai-system.md`
**Install:** `cp product-ai-system/ai-system.md ~/.claude/commands/ai-system.md`
**Invoke:** `/ai-system [problem or idea]`

**The 9-Skill Chain:**

| # | Skill | What It Does |
|---|---|---|
| 1 | Define Issue | Finds the real problem behind the request |
| 2 | Diagnose | Identifies root causes at a system level |
| 3 | Define Goal | Turns the problem into measurable outcomes |
| 4 | Generate Solution | Creates a grounded V1 solution |
| 5 | Challenge Solution | Critiques the solution before moving forward |
| 6 | Refine Solution | Improves it using challenge findings |
| 7 | Self Study | Reviews the full body of work for patterns |
| 8 | Self Test | Simulates review from User, PM, Designer, Engineer perspectives |
| 9 | Execution Readiness | Breaks into epics, tasks, acceptance criteria, and a readiness score |

**Modes:**

| Command | Use |
|---|---|
| `/ai-system [problem]` | Full 9-skill cycle |
| `/ai-system fast [problem]` | Compressed 5-skill cycle |
| `/ai-system skill [1-9] [input]` | Single skill in isolation |
| `/ai-system brief [problem]` | Problem brief only (Skills 1-2) |
| `/ai-system prd [problem]` | Full PRD (Skills 1-6) |

---

### 2. Portfolio AI System (`/portfolio-ai-system`)

A portfolio strategy, audit, and rewrite system for job applications at Staff / Principal level.

Evaluates portfolios as products competing for hiring decisions. Runs a 7-step workflow: intent definition, issue diagnosis, goal alignment, hiring simulation, UX/QA check, rewrite, and execution plan. Includes consistency tools for keeping new pages aligned with the existing site.

**Skill file:** `portfolio-ai-system/portfolio-ai-system.md`
**Install:** `cp portfolio-ai-system/portfolio-ai-system.md ~/.claude/commands/portfolio-ai-system.md`
**Invoke:** `/portfolio-ai-system audit [portfolio]`

**Modes:**

| Command | Use |
|---|---|
| `/portfolio-ai-system audit [portfolio]` | Full 7-step audit |
| `/portfolio-ai-system rewrite [section]` | Rewrite a specific section |
| `/portfolio-ai-system qa [site/folder]` | Links, logic, structure check |
| `/portfolio-ai-system mobile [page]` | Responsive and overflow check |
| `/portfolio-ai-system hiring [portfolio]` | Hiring simulation only |
| `/portfolio-ai-system learn-site [existing pages]` | Extract consistency guide from current site |
| `/portfolio-ai-system consistency-check [new page]` | Check a new page against the site's established patterns |

**Modular Skills** (install and invoke independently):

| File | Command | What It Does |
|---|---|---|
| `portfolio-audit-workflow.md` | -- | Full 7-step structured audit (standalone workflow) |
| `skills/hiring-simulation-skill.md` | `/hiring-simulation-skill` | 4-perspective hiring simulation with interview verdicts |
| `skills/homepage-rewrite-skill.md` | `/homepage-rewrite-skill` | Headline, subtext, CTA, and section label rewrites |
| `skills/mobile-qa-skill.md` | `/mobile-qa-skill` | 375px mobile QA checklist |
| `skills/portfolio-consistency-skill.md` | `/portfolio-consistency-skill` | Extract positioning, tone, and structure patterns for cross-page consistency |

---

## Installation

Copy any skill file to your Claude commands folder and invoke it with `/skill-name`:

```bash
# Product AI System
cp product-ai-system/ai-system.md ~/.claude/commands/ai-system.md

# Portfolio AI System (main)
cp portfolio-ai-system/portfolio-ai-system.md ~/.claude/commands/portfolio-ai-system.md

# Portfolio AI System (individual skills)
cp portfolio-ai-system/skills/hiring-simulation-skill.md ~/.claude/commands/hiring-simulation-skill.md
cp portfolio-ai-system/skills/homepage-rewrite-skill.md ~/.claude/commands/homepage-rewrite-skill.md
cp portfolio-ai-system/skills/mobile-qa-skill.md ~/.claude/commands/mobile-qa-skill.md
cp portfolio-ai-system/skills/portfolio-consistency-skill.md ~/.claude/commands/portfolio-consistency-skill.md
```

Then invoke in any Claude Code session:

```
/ai-system [your problem]
/portfolio-ai-system audit [your portfolio]
/portfolio-ai-system learn-site [existing pages]
/portfolio-ai-system consistency-check [new page]
```

---

## Output Quality Rules (Both Systems)

- No generic language -- no "seamless," "intuitive," "holistic," "best-in-class"
- Every metric has a number and a measurement method
- Every task and open decision has exactly one named owner
- Assumptions are labeled as assumptions, never stated as facts
- Every output ends with: Confidence level + Unresolved Gaps + Next Recommendation
