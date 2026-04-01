---
name: portfolio-execution-skill
description: Converts audit findings into production-ready portfolio output. Makes final structural decisions, rewrites content, and applies all changes directly to portfolio files. Produces a change log of every edit made.
skill: portfolio-execution-skill
invoke: /portfolio-execution-skill [audit output or page]
---

# Skill -- Portfolio Execution

## Purpose

Convert audit and analysis into **final, production-ready portfolio output** applied directly to the files.

This skill:
- makes final structural decisions
- resolves ambiguity
- rewrites content
- applies all changes to the actual files
- produces a change log of every edit

It eliminates the gap between "feedback" and "implementation".

This skill does not analyze. It does not suggest alternatives. It executes.

---

## When to Use

Use this skill when:

- audit is complete and findings need to be applied
- major issues are identified and improvements are clear
- a rewrite has been written and needs to replace existing copy
- a new page needs to be brought into alignment before publishing
- final production-ready output is needed

Do NOT use when:
- no audit or rewrite output exists yet (run `/portfolio-ai-system audit` first)
- positioning is still unclear

---

## Instructions

### Step 1 -- Read the Target

Read the full file to be edited. Do not make changes based on memory. Always read first.

---

### Step 2 -- Make Final Decisions

Do NOT list options.

Decide:

- final homepage structure
- section order
- what to remove
- what to emphasize

Load the fix list from one of:
- prior audit output in the session
- the consistency-check Required Fixes list
- the rewrite output section of a prior skill run

If no fix list exists in the session, generate one now based on the audit findings before proceeding.

Resolve all ambiguity before writing a single line.

---

### Step 3 -- Rewrite Homepage

Generate complete homepage content:

- Hero (title + subtitle + description)
- Section titles
- Section descriptions
- CTA text

Requirements:

- clear role positioning (Staff / Principal)
- strong hiring signal
- SAP / experience visibility
- AI + system thinking clarity
- reduce abstraction
- increase credibility

A hiring manager must understand who you are, what level you are, and why you are strong within 10 seconds.

---

### Step 4 -- Rewrite Key Sections

Rewrite:

- Founder section (SyncoPro elevated)
- AI / system section
- Navigation labels
- CTA text

---

### Step 5 -- Execute All Fixes to Files

Apply every fix in order:

- Copy fixes: replace old text with new text exactly as written
- Structural fixes: reorder, add, or remove sections as specified
- CTA fixes: replace button labels and href targets
- Meta fixes: update title, description, meta grid fields
- Consistency fixes: align tone, label, and section pattern to site standard

Rules:
- Apply the fix exactly as written in the rewrite output
- Do not rewrite beyond the scope of each fix
- Do not add new content not specified in the fix list
- Do not remove content not specified for removal

---

### Step 6 -- Apply Consistency Rules

Ensure:

- tone matches site
- structure is consistent
- no conflicting messaging
- no duplicate ideas

---

### Step 7 -- Mirror

After all fixes are applied to the primary file, mirror to the secondary site if one exists.

Standard mirror path:
```
cp katejieyu.com/[path] newkatejieyu.com/[path]
```

---

### Step 8 -- Produce Change Log

List every change made:

| # | Fix | File | Section | Status |
|---|---|---|---|---|
| 1 | [what changed] | [file] | [section] | Done |

---

## Output Format

### Final Homepage Structure

1.
2.
3.

---

### Full Homepage Copy (Ready to Use)

(Hero)
...

(Section 1)
...

(Section 2)
...

---

### Key Section Rewrites

- Founder
- AI System
- Navigation

---

### Final CTA Set

- ...
- ...

---

### Execution Summary
- Files edited: [list]
- Total fixes applied: [n]
- Mirrored to: [secondary site path or "N/A"]

### Change Log
Table: # | Fix | File | Section | Status

### Skipped Fixes
List any fixes that could not be applied, with reason.

### Post-Execution Check
- Any new inconsistencies introduced: [Yes / No — detail if Yes]
- Recommended next step: [consistency-check / publish / none]

---

## Output Rules

- No analysis
- No explanation
- No alternatives
- No hedging
- Be decisive
- Optimize for hiring impact
- Every fix must be logged
- Skipped fixes must be explained
- No silent changes — every edit is traceable
- Mirror must be confirmed or explicitly noted as skipped

---

## Success Criteria

A hiring manager understands:
- who you are
- what level you are
- why you are strong

within 10 seconds.

---

## Failure Conditions

- still abstract
- still reads like a framework, not a person
- unclear role / level
- not directly usable
