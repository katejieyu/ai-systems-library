# AI Systems Library

A collection of structured reasoning systems built for Claude Code.

Each system replaces ad-hoc AI prompting with a defined workflow — a chain of skills that runs your input through specific reasoning stages and produces consistent, decision-quality outputs. Every time, regardless of how the session started.

Built by [Kate Jie Yu](https://katejieyu.com).

---

## What these are

Most AI usage works like this: you write a prompt, you get output, the quality depends on how well you wrote the prompt that day. There is no structure, no enforced reasoning, no accumulated knowledge.

These systems work differently. Instead of prompting, you invoke a system. The system runs a defined workflow — it can't skip steps, it enforces its own operating rules, and it produces output in a consistent format. You get the same reasoning quality whether it's your first session or your fiftieth.

Each system is a `.md` file you drop into `~/.claude/commands/`. One install step. Available in every Claude Code session from that point. Invoke with a single command.

---

## Systems

### [Product AI System](./product-ai-system/)

**What it does:** Moves a product problem from raw input to execution-ready output through a structured 9-skill chain.

**Who it's for:** Product designers, PMs, and engineers who use AI for product work — feature definition, problem framing, solution design, PRD writing, challenge and critique.

**The problem it solves:** Most AI-assisted product work is shallow. You describe a problem, AI generates a solution that sounds plausible, you edit it, done. The hard thinking — root cause analysis, goal alignment, challenge, edge case detection, execution breakdown — gets skipped. This system makes it impossible to skip that thinking.

**How it works:**

The system runs two modes:

*Product Problem Mode* — run on any product idea, problem, or feature:

| Step | Skill | What happens |
|---|---|---|
| 1 | Define Issue | Extracts the real problem behind your request. Separates symptoms from root causes. Flags assumptions. |
| 2 | Diagnose | Identifies structural causes, workflow gaps, and dependency issues. Asks "why?" at each layer. |
| 3 | Define Goal | Turns the problem into measurable outcomes. Every goal gets a metric. Vague goals get rewritten. |
| 4 | Generate Solution | Builds a grounded V1 solution scoped to the defined goals. No invented requirements. |
| 5 | Challenge Solution | Assumes the solution has problems. Finds weak points, hidden risks, undefined states, edge cases. |
| 6 | Refine Solution | Resolves every issue from the challenge. Logs every decision made and why. |
| 7 | Self Study | Reviews the full body of work for recurring weaknesses and drift between goals and solution. |
| 8 | Self Test | Simulates review from User, PM, Designer, and Engineer perspectives. Each gives a verdict. |
| 9 | Execution Readiness | Breaks the solution into epics, tasks, acceptance criteria, and a readiness score 0–100. |

*Self-Evolution Mode* — run on the system itself when its own logic needs updating:

The system can turn inward. When prior outputs have been consistently wrong, when a feature changed and the system's assumptions are stale, or when you call `/product-ai-system evolve` — the system runs a self-examination loop: challenges its own assumptions, generates hypotheses, simulates itself to find failure points, detects gaps, and fixes them directly.

**Install:**
```bash
cp product-ai-system/product-ai-system.md ~/.claude/commands/product-ai-system.md
```

**Invoke:**
```
/product-ai-system [your problem or idea]
/product-ai-system fast [problem]          # compressed 5-skill pass
/product-ai-system brief [problem]         # problem definition only
/product-ai-system prd [problem]           # full PRD (skills 1–6)
/product-ai-system skill [1-9] [input]     # single skill in isolation
/product-ai-system evolve                  # run self-evolution loop
```

**End deliverable:** Epics, tasks, acceptance criteria, a readiness score 0–100, and a Cycle Summary with final problem definition, goal, solution, and top risks.

---

### [Portfolio AI System](./portfolio-ai-system/)

**What it does:** Evaluates and improves a portfolio website as if it were a product competing for hiring decisions.

**Who it's for:** Designers and PMs applying for Staff or Principal roles who want to evaluate their portfolio with the same rigor a hiring manager would — not a "looks good" pass, but a structured audit that finds what's weak, what's missing, and what would cost you an interview.

**The problem it solves:** Portfolio feedback is usually vague ("make the case studies more impactful") or based on taste ("I'd move this section up"). This system evaluates portfolios on the dimensions that actually drive hiring decisions: positioning clarity, content signal density, hiring simulation per audience, UX and mobile issues, and copy quality. It produces exact before/after rewrites, not suggestions.

**How it works:**

The system runs a 7-step audit workflow:

| Step | What happens |
|---|---|
| 1. Define Intent | Establishes what the portfolio is trying to communicate and who it's competing for. Identifies the gap between stated intent and actual signal. |
| 2. Diagnose Issues | Evaluates positioning (too abstract? too execution-level?), content (fluff, repetition, missing impact), structure (hierarchy, navigation), and storytelling (differentiation, narrative arc). |
| 3. Goal Alignment | Defines what a recruiter must understand in 10 seconds, what messages cannot be missing, and what makes this portfolio distinct. |
| 4. Hiring Simulation | Simulates a review from four perspectives: Recruiter (10-second scan), Hiring Manager (would they interview?), Design Leader (system thinking visible?), AI/Product Leader (future-facing?). Each gives a verdict. |
| 5. UX / QA / Mobile Check | Scans for cognitive load, navigation issues, broken links, and mobile layout failures at 375px. |
| 6. Rewrite & Improvement | Produces exact before/after rewrites for every weak section — homepage headline, subtext, CTAs, section labels, case study descriptions. |
| 7. Execution Plan | Prioritizes fixes by hiring impact: immediate (under 30 min), short-term (1–3 hours), structural (1+ day). |

The system also includes modular skills you can run independently — hiring simulation only, mobile QA only, homepage rewrite only, full-site cross-page consistency scan, or execution (applies all fixes directly to files).

**Portfolio Drift Protocol:** When the portfolio changes significantly — new case studies, role change, major redesign — run the re-alignment sequence: `learn-site → content-strategy → consistency-check → audit`. The system's internal logic doesn't drift; what drifts is its knowledge of the portfolio it's evaluating.

**Install:**
```bash
# Main skill only
cp portfolio-ai-system/portfolio-ai-system.md ~/.claude/commands/portfolio-ai-system.md

# Full install — all modular skills and workflows
cp portfolio-ai-system/portfolio-ai-system.md ~/.claude/commands/portfolio-ai-system.md && \
cp portfolio-ai-system/portfolio-audit-workflow.md ~/.claude/commands/portfolio-audit-workflow.md && \
cp portfolio-ai-system/skills/*.md ~/.claude/commands/ && \
cp portfolio-ai-system/workflows/*.md ~/.claude/commands/
```

**Invoke:**
```
/portfolio-ai-system audit [portfolio URL or folder]
/portfolio-ai-system scan-site [site folder]          # full cross-page audit
/portfolio-ai-system scan-site + execution [site]     # audit + apply fixes
/portfolio-ai-system content-strategy [portfolio]     # define what to say / remove
/portfolio-ai-system strategy-check [site]            # validate against strategy
/portfolio-ai-system learn-site [existing pages]      # extract consistency baseline
/portfolio-ai-system consistency-check [new page]     # check new page against site
/portfolio-ai-system rewrite [section]                # rewrite a specific section
```

**Modular skills (run independently):**
```
/hiring-simulation-skill [portfolio]        # 4-perspective hiring review
/homepage-rewrite-skill [page]              # headline, CTA, section label rewrites
/mobile-qa-skill [page]                     # 375px mobile checklist
/portfolio-consistency-skill [portfolio]    # extract consistency guide
/portfolio-execution-skill [audit output]   # apply fixes to files
/site-execution-skill [scan-site report]    # page-by-page fix application
```

**End deliverable:** Full audit report with hiring verdict per role, exact before/after rewrites, mobile issue list with fixes, and a prioritized execution plan ordered by hiring impact.

---

## Quick install (both systems)

```bash
# Clone or download this repo, then:

# Product AI System
cp product-ai-system/product-ai-system.md ~/.claude/commands/product-ai-system.md

# Portfolio AI System (full)
cp portfolio-ai-system/portfolio-ai-system.md ~/.claude/commands/portfolio-ai-system.md && \
cp portfolio-ai-system/portfolio-audit-workflow.md ~/.claude/commands/portfolio-audit-workflow.md && \
cp portfolio-ai-system/skills/*.md ~/.claude/commands/ && \
cp portfolio-ai-system/workflows/*.md ~/.claude/commands/
```

Then open Claude Code and invoke:

```
/product-ai-system [your problem]
/portfolio-ai-system audit [your portfolio]
```

---

## Design principles (both systems)

- **No generic output.** Every output is specific to the input. Generic language ("seamless," "intuitive," "holistic") is prohibited by operating rules.
- **No skipping.** Skills run in sequence. Handoff conditions must be met before the next stage runs.
- **No unnamed owners.** Every task and open decision has exactly one owner.
- **Assumptions are labeled.** Nothing is stated as a fact unless it is a fact.
- **Every output ends with:** Confidence level (High / Medium / Low) + Unresolved Gaps + Next Recommendation.

---

## Adding more systems

This library is designed to grow. Each new system follows the same structure:

```
system-name/
  README.md                  # what it does, install, usage, end deliverable
  system-name.md             # main skill file — the one you install
  skills/                    # modular sub-skills (optional)
  workflows/                 # named workflow files (optional)
```

Add it to this index with the same format: what it does, who it's for, what problem it solves, how it works, install, invoke, end deliverable.

---

## License

MIT — use, modify, and share freely.
