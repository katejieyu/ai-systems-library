---
name: portfolio-site-scan-workflow
description: Full-site portfolio audit workflow. Creates a page inventory, runs the same audit loop on each page, detects cross-page inconsistency, aggregates hiring signal findings, and produces system-level improvements with prioritized fixes.
skill: portfolio-site-scan-workflow
invoke: /portfolio-site-scan-workflow [site]
---

# Workflow — Portfolio Site Scan

## Purpose

Run a full-site audit using a structured loop. Detect cross-page inconsistencies, evaluate hiring signal at a system level, and produce prioritized fixes with canonical decisions.

---

## When to Use

Use when:
- auditing an entire portfolio site
- checking consistency across pages
- validating navigation, CTA, and naming systems
- preparing for a hiring-facing polish pass

Do not use when:
- reviewing only one page
- building a new portfolio from scratch

---

## Execution Flow

### Step 1 — Page Inventory

Discover all pages. Create a complete inventory.

Classify each page as:
- homepage
- sitemap
- case study
- founder project
- resume / about
- utility

Output:
- page name
- file path
- page type
- audit status

---

### Step 2 — Page Loop

For EACH page, run the PAGE LOOP:

1. Identify page type
2. Evaluate positioning
3. Check content clarity and signal density
4. Check navigation and CTA logic
5. Check UX and readability
6. Check mobile risks
7. Identify missing signals

Per-page output:

**[Page Name]**
- Issues:
- Strengths:
- Missing Signals:
- Recommended Fixes:

---

### Step 3 — Cross-Page Consistency

Compare all audited pages for:

- role title / level signal
- product naming
- CTA wording
- footer tagline
- breadcrumb / back-nav pattern
- tone and abstraction level
- section naming

Output:
- consistency table
- contradictions found
- one canonical version per contradiction

---

### Step 4 — Hiring Signal Assessment

Evaluate the site as a whole.

Answer:
- what level does the site signal?
- where does signal weaken or contradict?
- what would a recruiter / hiring manager notice first?
- what is the strongest proof point on the site?

Output:
- overall level signal
- biggest hiring risks
- strongest proof points

---

### Step 5 — Prioritized Fixes

Rank issues across the site by:
- hiring impact
- visibility
- effort

Output: Top 10 prioritized fixes
Table: # | Fix | Pages Affected | Impact | Effort

---

### Step 6 — Execution Preparation

Convert findings into action.

Output:
- canonical naming decisions
- exact text replacements
- navigation fixes
- consistency propagation list

---

### Step 7 — Optional Execution Loop

If execution mode is requested (`scan-site + execution`), generate page-by-page instructions.

For each page requiring updates:
- what to change
- exact replacement copy
- consistency rules applied

---

## PAGE LOOP

Use this loop for every page in Step 2:

1. Identify page type
2. Evaluate positioning — does it match the intended level?
3. Check content clarity — specific, high-signal, or vague and generic?
4. Check navigation and CTA — correct targets, consistent wording, no dead links?
5. Check UX and readability — scan pattern, cognitive load, hierarchy
6. Check mobile risk — overflow, tap targets, layout break
7. Identify missing signals — what is absent that should be there?

---

## Rules

- MUST run Page Loop before cross-page analysis
- MUST audit all pages unless explicitly excluded
- MUST identify every contradiction across pages
- MUST define one canonical version for every inconsistency
- MUST prioritize hiring impact over completeness
- No generic findings — every issue must reference a specific page and element
- No vague recommendations — every fix must be actionable with exact copy

---

## Output Format

### Page Inventory
Table: page name | file path | page type | audit status

---

### Per-Page Findings
Per page: Issues | Strengths | Missing Signals | Recommended Fixes

---

### Cross-Page Consistency Report
Table: Dimension | Consistent | Issues Found | Recommended Canonical

---

### Hiring Signal Assessment
- Overall level signaled:
- Biggest hiring risks:
- Strongest proof points:

---

### Top 10 Prioritized Fixes
Table: # | Fix | Pages Affected | Impact | Effort

---

### Execution Suggestions
- Canonical decisions:
- Exact text replacements per page:
- Navigation fixes:
- Consistency propagation list:
