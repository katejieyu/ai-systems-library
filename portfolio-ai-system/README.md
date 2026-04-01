# Portfolio AI System

A portfolio strategy, audit, and rewrite system for Claude Code.

Evaluates portfolios as products competing for hiring decisions — not "looks good," but a structured pass across positioning, content signal density, UX, mobile, and copy quality. Produces exact before/after rewrites and a hiring verdict from four perspectives.

---

## Files

| File | Description |
|---|---|
| `portfolio-ai-system.md` | Main skill file — install this |
| `portfolio-audit-workflow.md` | Full 7-step audit workflow (standalone) |
| `workflows/portfolio-site-scan-workflow.md` | Full-site scan — cross-page consistency, system-level issues, top 10 fixes |
| `skills/hiring-simulation-skill.md` | 4-perspective hiring simulation with interview verdicts |
| `skills/homepage-rewrite-skill.md` | Headline, subtext, CTA, and section label rewrites |
| `skills/mobile-qa-skill.md` | 375px mobile responsiveness and overflow QA checklist |
| `skills/portfolio-consistency-skill.md` | Extracts positioning, tone, and structure patterns for cross-page consistency |
| `skills/portfolio-content-strategy-skill.md` | Defines content strategy — what to say, what to remove, signal hierarchy, tone |
| `skills/portfolio-execution-skill.md` | Applies audit findings and rewrites directly to portfolio files — produces a change log |
| `skills/site-execution-skill.md` | Applies scan-site findings page-by-page — canonical decisions first, then exact fixes |

---

## Install

```bash
# Main skill only
cp portfolio-ai-system.md ~/.claude/commands/portfolio-ai-system.md

# Full install — all modular skills and workflows
cp portfolio-ai-system.md ~/.claude/commands/portfolio-ai-system.md && \
cp portfolio-audit-workflow.md ~/.claude/commands/portfolio-audit-workflow.md && \
cp skills/*.md ~/.claude/commands/ && \
cp workflows/*.md ~/.claude/commands/
```

---

## Usage

```
/portfolio-ai-system audit [portfolio URL or folder]
```

| Command | Use |
|---|---|
| `/portfolio-ai-system audit [portfolio]` | Full 7-step audit |
| `/portfolio-ai-system scan-site [site]` | Full cross-page audit — consistency, system-level issues, top 10 fixes |
| `/portfolio-ai-system scan-site + execution [site]` | Cross-page audit + apply all fixes page-by-page |
| `/portfolio-ai-system content-strategy [portfolio]` | Define content strategy — pillars, signal hierarchy, tone, what to remove |
| `/portfolio-ai-system strategy-check [site]` | Validate site against its content strategy — alignment score, drift, gaps, top fixes |
| `/portfolio-ai-system learn-site [existing pages]` | Extract consistency baseline — positioning, tone, structure, CTA patterns |
| `/portfolio-ai-system consistency-check [new page]` | Check a new or changed page against established site patterns |
| `/portfolio-ai-system rewrite [section]` | Rewrite a specific section — headline, CTA, copy block |
| `/portfolio-ai-system mobile [page]` | Responsive and overflow check |
| `/portfolio-ai-system hiring [portfolio]` | Hiring simulation only |

**Modular skills (install and invoke independently):**

| Command | Use |
|---|---|
| `/hiring-simulation-skill [portfolio]` | 4-perspective hiring simulation with verdicts |
| `/homepage-rewrite-skill [page]` | Headline, subtext, CTA, and section label rewrites |
| `/mobile-qa-skill [page]` | 375px mobile QA checklist |
| `/portfolio-consistency-skill [portfolio]` | Extract consistency guide for new pages |
| `/portfolio-content-strategy-skill [portfolio]` | Define content strategy |
| `/portfolio-execution-skill [audit output]` | Apply fixes directly to portfolio files |
| `/site-execution-skill [scan-site report]` | Apply scan-site findings page-by-page |

---

## The 7-Step Workflow

| # | Step | What It Does |
|---|---|---|
| 1 | Define Intent | Establish what the portfolio is trying to communicate and who it's competing for |
| 2 | Diagnose Issues | Evaluate positioning (too abstract? too execution-level?), content, structure, and storytelling |
| 3 | Goal Alignment | Define what must be understood in 10 seconds, required messages, and differentiators |
| 4 | Hiring Simulation | Simulate review from Recruiter, Hiring Manager, Design Leader, AI/Product Leader — verdict per role |
| 5 | UX / QA / Mobile Check | Cognitive load, navigation, broken links, 375px mobile layout |
| 6 | Rewrite & Improvement | Exact before/after rewrites for every weak section |
| 7 | Execution Plan | Immediate fixes (under 30 min), short-term (1–3 hrs), structural (1+ day) |

**Extended commands (run after the 7-step audit):**
- `content-strategy` — define what to say, what to remove, signal hierarchy
- `strategy-check` — validate site execution against the defined strategy
- `scan-site` — full cross-page audit with consistency detection

---

## Portfolio Drift Protocol

The system's internal logic doesn't drift — what drifts is its knowledge of the portfolio it's evaluating. When the portfolio changes significantly (new case studies, role change, major redesign), run this sequence:

```
Step 0 — Pre-check: identify what changed, flag stale outputs, re-run only what's affected
Step 1 — /portfolio-ai-system learn-site [updated pages]
Step 2 — /portfolio-ai-system content-strategy [portfolio]   (skip if positioning unchanged)
Step 3 — /portfolio-ai-system consistency-check [changed pages]
Step 4 — /portfolio-ai-system audit [portfolio]
```

---

## End Deliverable

- Hiring verdict per role (Yes / No / Conditional)
- Exact before/after copy rewrites
- Mobile issue list with fixes
- Prioritized execution plan (immediate / short-term / structural)
- Overall score: how competitive at Staff / Principal level
