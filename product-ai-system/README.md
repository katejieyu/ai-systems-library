# Product AI System

A structured product reasoning engine for designers, PMs, and engineers.

Moves product work from raw problem to execution-ready output through a 9-skill chain. Does not agree with your framing. Surfaces contradictions, flags assumptions, and forces decisions before they become blockers in engineering.

---

## Files

| File | Description |
|---|---|
| `ai-system.md` | Main skill file — install this |

---

## Install

```bash
cp ai-system.md ~/.claude/commands/ai-system.md
```

---

## Usage

```
/ai-system [problem or idea]
```

| Command | Use |
|---|---|
| `/ai-system [problem]` | Full 9-skill cycle |
| `/ai-system fast [problem]` | Compressed 5-skill cycle |
| `/ai-system skill [1-9] [input]` | Single skill in isolation |
| `/ai-system brief [problem]` | Problem brief only (Skills 1-2) |
| `/ai-system prd [problem]` | Full PRD (Skills 1-6) |

---

## The 9-Skill Chain

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

---

## End Deliverable

Every cycle ends with a Cycle Summary:

- **Final Problem Definition** -- one sentence
- **Final Goal** -- user outcome + business outcome
- **Final V1 Solution** -- one paragraph
- **Top Risks** -- with likelihood and owner
- **Readiness Score** -- 0-100 with reason
- **Recommended Next Step** -- the single most important action before build begins
