---
name: hiring-simulation-skill
description: Simulates a hiring review from four perspectives -- Recruiter, Hiring Manager, Design Leader, AI/Product Leader. Produces an interview decision and specific concerns per role.
skill: hiring-simulation-skill
invoke: /hiring-simulation-skill [portfolio URL or content]
---

# Hiring Simulation Skill

Simulate a real hiring review from four distinct perspectives.

Do not blend perspectives. Each reviewer has a different goal, different time budget, and different definition of "strong candidate."

Be honest. Do not produce false positives. If a portfolio would not get an interview, say so.

---

## Operating Rules

1. Read the portfolio completely before simulating -- do not simulate from partial context
2. Each perspective must be independent -- do not let earlier verdicts influence later ones
3. Name specific things the reviewer would see, not generic observations
4. Every verdict must include a reason -- no verdict without evidence
5. If all verdicts are "Yes," the simulation was not rigorous enough
6. Simulate the reviewer's actual behavior, not their ideal behavior (recruiters do 10-second scans, not careful reads)

---

## PERSPECTIVE 1 -- Recruiter

**Profile:** Non-designer. Scans 50+ portfolios per week. Looking for: clear title, recognizable companies, legible seniority.

**Time budget:** 10 seconds

**What they actually read:**
- Name and title
- Company names (recognizable = good signal)
- Years of experience (implicit)
- One visual that catches attention

**Evaluation questions:**
- Is the title clearly Staff / Principal level?
- Are company names visible and recognizable?
- Is there one clear visual that creates interest?
- Would they know what kind of designer this is (UX / product / systems / AI)?
- Would they pass this to a hiring manager?

**Output:**
- What the recruiter sees in 10 seconds (exact elements, not summary)
- What is unclear
- What would make them skip
- **Decision:** Pass to manager / Skip / Maybe (with condition)

---

## PERSPECTIVE 2 -- Hiring Manager

**Profile:** Senior designer or design manager. Looking for: evidence of impact, ability to work across functions, quality of thinking. Scans portfolio for 3-5 minutes.

**Time budget:** 3-5 minutes

**What they actually read:**
- Project titles and descriptions
- Case study structure (is there a clear problem/outcome?)
- Role and scope (did they lead or execute?)
- Any metrics or outcome statements

**Evaluation questions:**
- Is there evidence of impact, not just delivery?
- Is the work at Staff level (cross-functional, strategic, system-level)?
- Is the candidate's specific contribution visible?
- Are there metrics? Are they credible?
- What would make them hesitate before interviewing?

**Output:**
- What signals are strong
- What is missing or weak
- What questions they would ask in an interview
- **Decision:** Interview / Pass / Conditional (named precondition)

---

## PERSPECTIVE 3 -- Design Leader (Director / VP)

**Profile:** Evaluating for strategic potential and leadership, not craft. Looking for: evidence of system thinking, cross-team influence, judgment under ambiguity.

**Time budget:** 5-7 minutes, focused on 1-2 case studies

**What they actually read:**
- How problems are framed (symptom vs. root cause)
- How solutions are scoped (V1 vs. ideal vs. deferred)
- Evidence of influence beyond the immediate team
- Any mention of org design, workflow, standards, or systems

**Evaluation questions:**
- Does the work show system thinking or just good execution?
- Is there evidence of influence beyond the design team?
- Has this person navigated ambiguity and made judgment calls?
- Would you trust this person to represent design at a leadership table?

**Output:**
- Evidence of system thinking (present / absent / partial)
- Evidence of leadership or influence (present / absent / partial)
- What would make them confident vs. concerned
- **Decision:** Strong yes / Yes / No / Needs more evidence

---

## PERSPECTIVE 4 -- AI / Product Leader

**Profile:** Evaluating for AI capability, future-facing thinking, and ability to define product direction in AI-native products. May or may not be a designer.

**Time budget:** 5 minutes, focused on AI-related work

**What they actually read:**
- Any AI-specific case studies or projects
- How AI is framed (tool? system? capability?)
- Evidence that the candidate understands AI's limitations, not just possibilities
- Any system architecture, workflow design, or AI behavior design

**Evaluation questions:**
- Is AI capability genuinely visible, or just name-dropped?
- Does this person understand how AI changes product behavior (not just UI)?
- Have they worked on AI systems at a product or system level?
- Are they forward-looking, or describing past AI work?

**Output:**
- AI signal strength (Strong / Moderate / Weak / None)
- What AI capability is demonstrated
- What is missing from an AI product perspective
- **Decision:** High interest / Moderate interest / Low interest / Not qualified for AI-focused roles

---

## Final Output Format

```
## Hiring Simulation Report

---

### RECRUITER (10-second scan)

**Sees:** [exact elements in first 10 seconds]
**Unclear:** [what fails to communicate]
**Would skip because:** [if applicable]
**Decision:** [Pass to manager / Skip / Maybe]
**Condition (if Maybe):** [what would change the decision]

---

### HIRING MANAGER (3-5 min review)

**Strong signals:**
- [specific point with evidence]

**Weak or missing:**
- [specific gap]

**Interview questions they'd ask:**
1.
2.
3.

**Decision:** [Interview / Pass / Conditional]
**Condition (if Conditional):** [named precondition]

---

### DESIGN LEADER

**System thinking visible:** [Yes / No / Partial]
**Leadership / influence visible:** [Yes / No / Partial]
**What builds confidence:**
**What creates concern:**
**Decision:** [Strong yes / Yes / No / Needs more evidence]

---

### AI / PRODUCT LEADER

**AI signal strength:** [Strong / Moderate / Weak / None]
**Demonstrated capability:**
**Missing:**
**Decision:** [High / Moderate / Low interest / Not qualified]

---

## Simulation Summary

| Perspective | Decision | Key Concern |
|---|---|---|
| Recruiter | [decision] | [one concern] |
| Hiring Manager | [decision] | [one concern] |
| Design Leader | [decision] | [one concern] |
| AI/Product Leader | [decision] | [one concern] |

**Overall Hiring Signal:** [Strong / Moderate / Weak]
**Single Highest-Impact Fix:** [the one change that would most improve hiring outcomes]
```
