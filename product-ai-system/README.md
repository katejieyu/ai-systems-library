# Product AI System

A structured product reasoning engine for Claude Code.

Takes a product problem — vague idea, named feature, or draft PRD — and moves it through a 9-skill chain to execution-ready output. Does not agree with your framing. Surfaces contradictions, flags assumptions, and forces decisions before they become blockers in engineering.

Also includes a **self-evolution mode** — the system can turn inward, detect its own drift, regenerate assumptions, and heal gaps without a full rebuild.

---

## Files

| File | Description |
|---|---|
| `product-ai-system.md` | Main skill file — install this |
| `skills/self-inquiry-skill.md` | Challenge current assumptions before generating anything |
| `skills/self-hypothesis-skill.md` | Generate testable hypotheses from gaps |
| `skills/self-test-loop-skill.md` | Simulate usage to find real failure points |
| `skills/gap-detection-skill.md` | Find missing logic and undefined states |
| `skills/self-healing-execution-skill.md` | Fix gaps directly — no analysis, only action |
| `skills/persona-journey-refresh-skill.md` | Update persona and journey after context changes |
| `skills/readme-sync-skill.md` | Align documentation with current system state |
| `workflows/product-full-cycle-workflow.md` | Full 9-skill cycle reference |
| `workflows/product-self-evolution-workflow.md` | Self-evolution loop reference |
| `workflows/feature-change-loop-workflow.md` | Feature change re-alignment workflow |

---

## Install

```bash
cp product-ai-system.md ~/.claude/commands/product-ai-system.md
```

---

## Usage

```
/product-ai-system [problem or idea]
```

### Product Problem Mode

| Command | Use |
|---|---|
| `/product-ai-system [problem]` | Full 9-skill cycle — problem to execution plan |
| `/product-ai-system fast [problem]` | Compressed 5-skill pass — faster, less depth |
| `/product-ai-system brief [problem]` | Problem definition only (Skills 1–2) |
| `/product-ai-system prd [problem]` | Full PRD output (Skills 1–6) |
| `/product-ai-system skill [1-9] [input]` | Run a single skill in isolation |

### Self-Evolution Mode

| Command | Use |
|---|---|
| `/product-ai-system evolve` | Run self-evolution loop — detect drift, fix gaps, re-test |
| `/product-ai-system feature-update [feature]` | Re-align system after a feature changes |
| `/product-ai-system refresh-persona` | Update persona and journey definitions |
| `/product-ai-system sync-readme` | Sync documentation to current system state |

---

## The 9-Skill Chain

| # | Skill | What It Does |
|---|---|---|
| 1 | Define Issue | Finds the real problem behind the request — separates symptoms from root causes, flags assumptions |
| 2 | Diagnose | Identifies structural causes, workflow gaps, and dependency issues — asks "why?" at each layer |
| 3 | Define Goal | Turns the problem into measurable outcomes — every goal gets a metric, vague goals get rewritten |
| 4 | Generate Solution | Builds a grounded V1 solution scoped to defined goals — no invented requirements |
| 5 | Challenge Solution | Assumes the solution has problems — finds weak points, hidden risks, undefined states, edge cases |
| 6 | Refine Solution | Resolves every issue from the challenge — logs every decision made and why |
| 7 | Self Study | Reviews the full body of work for recurring weaknesses and drift between goals and solution |
| 8 | Self Test | Simulates review from User, PM, Designer, and Engineer perspectives — each gives a verdict |
| 9 | Execution Readiness | Breaks into epics, tasks, acceptance criteria, and a readiness score 0–100 |

---

## Self-Evolution Sub-Skills

The self-evolution loop runs these skills in sequence on the system itself:

| Skill | What It Does |
|---|---|
| Self Inquiry | Challenges the system's current assumptions — asks "Is this still true? What would prove it false?" |
| Self Hypothesis | Generates testable hypotheses from each gap or contradiction found in inquiry |
| Self Test Loop | Simulates 3 inputs through the system to find real failure points |
| Gap Detection | Reads the full skill chain to find missing logic, undefined states, and contradictions |
| Self-Healing Execution | Fixes every critical and moderate gap directly — no analysis, only action |
| Persona & Journey Refresh | Updates persona and journey definitions after a feature or context change |
| README Sync | Rewrites documentation to accurately reflect current system state |

---

## End Deliverable

From a full cycle run:

- Epics, tasks, and acceptance criteria
- Readiness score 0–100 with reason
- Cycle Summary: final problem definition, goal, V1 solution, and top risks
- Every output ends with: Confidence level + Unresolved Gaps + Next Recommendation
