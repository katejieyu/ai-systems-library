---
name: portfolio-audit-workflow
description: Full 7-step portfolio audit workflow. Run this as a standalone skill to execute a complete structured portfolio evaluation.
skill: portfolio-audit-workflow
invoke: /portfolio-audit-workflow [portfolio URL or folder]
---

# Portfolio Audit Workflow

A structured 7-step audit system for evaluating portfolios at Staff / Principal hiring level.

Run in order. Do not skip steps.

---

## STEP 1 -- DEFINE INTENT

Establish what the portfolio is trying to communicate before evaluating it.

Extract:
- Target audience (recruiter, hiring manager, design leader, AI/product leader)
- Intended seniority level (Senior / Staff / Principal)
- Core strengths being presented
- Implicit positioning (what the portfolio says even if not stated)

Output:
- **Stated Intent** -- what the owner claims the portfolio does
- **Actual Signal** -- what a first-time viewer actually reads
- **Gap** -- difference between intent and signal

---

## STEP 2 -- DIAGNOSE ISSUES

Evaluate across four dimensions:

### Positioning
- Too abstract? (concepts without proof)
- Too execution-level? (work without strategy)
- Level unclear? (could be any seniority)

### Content
- Low signal density (words without meaning)
- Missing impact metrics (outcomes not stated)
- Repetition (same point across multiple sections)
- Fluff (language that sounds good but communicates nothing)

### Structure
- Unclear hierarchy (what matters most is not visible first)
- Confusing navigation (unclear where to go)
- Poor section order (backstory before proof)

### Storytelling
- No narrative arc (list of projects, not a career story)
- Weak differentiation (could be anyone's portfolio)
- Strengths not explicit (reader has to infer)

Output:
- Diagnosis table: Issue | Dimension | Severity (High/Med/Low) | Example

---

## STEP 3 -- GOAL ALIGNMENT

Define what the portfolio MUST communicate in 10 seconds.

Output:
- **10-Second Test** -- what a recruiter sees in one fast scroll
- **Required Messages** -- 3 non-negotiable things that must land
- **Differentiators** -- what makes this portfolio distinct vs. peers
- **Positioning Statement** -- the single sentence that should define this person

---

## STEP 4 -- HIRING SIMULATION

Simulate a review from four hiring perspectives. Be honest. Do not soften findings.

### Recruiter (10-second scan)
- What do they see?
- What is unclear?
- Would they pass it to a manager?

### Hiring Manager
- Would they request an interview?
- What would make them hesitate?
- What questions would they ask?

### Design Leader
- Is system thinking visible?
- Is the work strategic or only executional?
- Does the portfolio demonstrate leadership?

### AI / Product Leader
- Is AI capability visible and credible?
- Is the person future-facing or status-quo?
- Would they trust this person to define AI-native product direction?

Output per perspective:
- Strengths
- Concerns
- Interview decision (Yes / No / Maybe with condition)

---

## STEP 5 -- UX / QA / RESPONSIVE CHECK

### Scanning
- Can a reader extract the top 3 messages in 10 seconds?
- Is hierarchy clear (size, weight, color)?
- Are section labels informative or decorative?

### Cognitive Load
- How many distinct messages compete for attention on the homepage?
- Are there sections that require prior context to understand?

### Navigation
- Can a user find case studies from the homepage?
- Are there dead ends (pages with no next action)?
- Are CTAs specific or vague?

### Links
- Are all links functional?
- Do external links open in new tabs?
- Are any CTAs pointing to wrong targets?

### Mobile
- Does layout break below 375px?
- Is any text clipped or overflowing?
- Are tap targets minimum 44x44px?
- Does horizontal scroll occur?
- Is font size readable without pinching?

Output:
- Issue table: Issue | Location | Severity | Fix

---

## STEP 6 -- REWRITE & IMPROVEMENT

For each section that has issues, provide:
- Current copy (exact text)
- Problem (why it fails)
- Rewritten copy (exact replacement)

Minimum required rewrites:
- Homepage headline
- Homepage subtext / descriptor
- Primary CTA
- 1 case study title/description
- 1 weak section label

Format all rewrites as:
```
BEFORE: [exact current text]
PROBLEM: [why it fails]
AFTER: [rewritten replacement]
```

---

## STEP 7 -- EXECUTION PLAN

### Immediate Fixes (under 30 min, high impact)
Items that can be changed with a single text or link edit.

### Short-Term Improvements (1-3 hours)
Items that require restructuring copy or reordering sections.

### Structural Changes (1+ day)
Items that require rethinking layout, navigation, or positioning.

Format:
- Fix | Section | Effort | Impact (High/Med/Low) | Done?

---

## Output Format

Run all 7 steps in sequence. Produce a final summary at the end:

```
## Audit Summary

### Overall Score
[1-10 -- how competitive is this portfolio at Staff/Principal level]

### Top 3 Critical Issues
1.
2.
3.

### Single Most Important Fix
[the one change that would have the highest hiring impact]

### Would You Interview This Person?
[Yes / No / Maybe -- with a one-sentence reason]
```
