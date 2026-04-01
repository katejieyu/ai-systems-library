---
name: site-execution-skill
description: Converts site-level audit findings into page-by-page implementation-ready changes. Canonical decisions first, then exact replacements per page. No analysis.
skill: site-execution-skill
invoke: /site-execution-skill [scan-site report or site folder]
---

# Skill — Site Execution

## Purpose

Convert site-level audit into **page-by-page implementation-ready changes**.

This is the final step:
Analysis → Decision → Execution

---

## When to Use

Use when:
- site scan is complete
- inconsistencies are identified
- canonical wording is decided
- final output is needed

Do NOT use:
- before audit
- when positioning is unclear

---

## Instructions

### Step 1 — Apply Canonical Decisions

Use site scan results to define:

- role title
- product naming
- CTA wording
- footer label
- navigation labels

These become the source of truth.

---

### Step 2 — Page Priority Order

Execute in this order:
1. Homepage (`index.html`) — highest visibility
2. Sitemap — navigational source of truth
3. Case studies — recruiter reads these after homepage
4. Founder pages — secondary depth signal
5. Utility pages (resume, about) — lower traffic but visible

---

### Step 3 — Page-by-Page Execution

For EACH affected page:

- identify required changes
- replace inconsistent content
- apply canonical wording
- improve clarity if needed

Rules:
- Read the file before editing — do not work from memory
- Replace only what was specified in the audit
- Do not add new content not listed in the fixes
- Do not remove content not specified for removal

---

### Step 4 — Rewrite Where Needed

If content is weak:

- rewrite sections
- improve clarity
- strengthen hiring signal

---

### Step 5 — Ensure Consistency

Check:

- tone alignment
- structure alignment
- no contradictions
- no duplication

---

### Step 6 — Mirror

If a secondary site exists (e.g. a staging or mirror domain), mirror changes after applying to the primary site:

```
cp [primary-site]/[path] [secondary-site]/[path]
```

Confirm mirror for each file or note as skipped with reason. If no secondary site exists, mark this step as N/A.

---

### Step 7 — Change Log

Produce a complete change log:

| # | Change | File | Section | Status |
|---|---|---|---|---|
| 1 | [what changed] | [file path] | [section] | Done |

---

## Output Format

### Canonical Decisions

- Role title:
- SyncoPro naming:
- CTA wording:
- Footer tagline:
- Navigation labels:

---

### Page-by-Page Changes

#### index.html
- change:
- replace:
- new copy:

#### sitemap.html
- change:
- replace:
- new copy:

#### [page name]
- change:
- replace:
- new copy:

---

### Execution Summary
- Files edited: [list]
- Total changes applied: [n]
- Mirrored to: [newkatejieyu.com or N/A]

### Change Log
Table: # | Change | File | Section | Status

### Skipped Changes
List any changes that could not be applied, with reason.

### Post-Execution Check
- New inconsistencies introduced: [Yes / No]
- Recommended next step: [consistency-check / publish / none]

---

## Rules

- No analysis
- No alternatives
- No explanations
- Only actionable output
- Must be copy-paste ready
- Canonical decisions before any page changes
- Every change must be logged
- Mirror must be confirmed or explicitly skipped
- No silent changes — every edit is traceable
