---
name: homepage-rewrite-skill
description: Focused skill for rewriting portfolio homepage copy -- headline, subtext, descriptor, CTA, section labels. Produces exact before/after rewrites.
skill: homepage-rewrite-skill
invoke: /homepage-rewrite-skill [homepage URL or content]
---

# Homepage Rewrite Skill

A focused skill for rewriting portfolio homepage copy to maximize hiring signal in the first 10 seconds.

---

## Operating Rules

1. Read the current homepage completely before writing anything
2. Every rewrite must solve a specific problem -- not just "sound better"
3. Rewrites must be specific to this person -- no generic phrases
4. No buzzwords: no "passionate," "innovative," "holistic," "seamless," "best-in-class"
5. Every headline must survive the 10-second test: can a stranger read it and know exactly who this person is?
6. CTAs must tell the reader what they will get, not just what to do

---

## What to Rewrite

### Hero Section

**Headline**
- Must answer: "Who is this person and what do they do?"
- Must be specific enough that it couldn't describe anyone else
- Must include level signal (Staff / Principal / Lead)
- Maximum: 12 words

**Subtext / Descriptor**
- Expands the headline with concrete context
- Should mention: domain, company or product type, distinct capability
- Maximum: 2 sentences

**Label / Eyebrow**
- The small text above the headline
- Should be a role identifier, not a tagline
- Example: "Staff Product Designer · AI Systems · Enterprise"

**Primary CTA**
- Should tell the reader what they will see, not just prompt action
- "View Case Studies" > "Explore the Framework"
- "See my SAP work" > "Let's connect"

---

### About / Bio Section

**Opening Line**
- Must contain a specific claim, not a personality adjective
- "I design AI decision systems for enterprise supply chains" > "I'm a passionate designer who loves solving problems"

**Positioning Statement**
- One sentence that defines what this person does that others do not
- Must be falsifiable (a claim that could be wrong)

---

### Section Labels

For each section on the homepage, evaluate:
- Does the label tell the reader what they will see?
- Or does it just describe a category?

**Weak labels:** Work, Projects, About, Skills
**Strong labels:** Enterprise AI Case Studies, Shipped at SAP, How I Think About Systems

---

### Work / Case Study Titles

For each project card:
- Does the title say what the project achieved, not just what it was?
- Does the description communicate impact (who benefited, what changed)?

Rewrite format:
```
BEFORE: [current title / description]
PROBLEM: [why it fails]
AFTER: [rewritten replacement]
```

---

## Output Format

Produce all rewrites in this structure:

```
## Homepage Rewrite

### Hero
LABEL (before): [text]
LABEL (after): [text]

HEADLINE (before): [text]
HEADLINE (after): [text]

SUBTEXT (before): [text]
SUBTEXT (after): [text]

CTA (before): [text]
CTA (after): [text]

---

### Section Labels
[SECTION NAME]
BEFORE: [text]
AFTER: [text]

---

### Case Study Titles
[PROJECT]
TITLE BEFORE: [text]
TITLE AFTER: [text]
DESC BEFORE: [text]
DESC AFTER: [text]

---

### Bio / About
OPENING BEFORE: [text]
OPENING AFTER: [text]

---

## Why These Changes
[2-3 sentences explaining the strategy behind the rewrites]
```
