---
name: mobile-qa-skill
description: Mobile responsiveness and overflow QA checklist for portfolio sites. Tests layout, readability, tap targets, scroll behavior, and visual integrity on small screens.
skill: mobile-qa-skill
invoke: /mobile-qa-skill [URL or page path]
---

# Mobile QA Skill

A structured QA checklist for testing portfolio mobile responsiveness.

Simulate a real user on a 375px-wide iPhone SE screen. Be critical. Flag anything that requires effort to use.

---

## Test Environment

- Primary viewport: 375px wide (iPhone SE)
- Secondary viewport: 390px wide (iPhone 14)
- Secondary viewport: 414px wide (iPhone Plus)
- Tablet check: 768px wide (iPad portrait)

---

## Checklist

### Layout Integrity
- [ ] No horizontal scroll at 375px
- [ ] No content overflows container bounds
- [ ] No text extends beyond screen edge
- [ ] No elements overlap unintentionally
- [ ] Grid/flex containers collapse correctly (not breaking to unexpected layouts)
- [ ] Images scale and don't bleed outside their containers

### Typography
- [ ] Body text minimum 14px (readable without pinching)
- [ ] Headings scale down appropriately (not too large on small screen)
- [ ] Line length not too wide or too narrow (45-75 chars optimal)
- [ ] No text wraps in an unintended way that creates orphan words
- [ ] No text that requires zooming to read

### Navigation
- [ ] Hamburger menu (or alternative) visible and functional
- [ ] Nav links are accessible and not behind overflow
- [ ] Back button / breadcrumb visible where expected
- [ ] No nav element hides critical links on mobile

### Tap Targets
- [ ] All buttons minimum 44x44px (Apple HIG standard)
- [ ] All links have enough space between them (minimum 8px gap)
- [ ] No small inline links (e.g., single-word links in paragraphs)
- [ ] CTAs large enough to tap without precision

### Images & Media
- [ ] Images don't overflow container
- [ ] Images maintain correct aspect ratio (no squash/stretch)
- [ ] Any diagrams or charts are readable at mobile size (not just scaled down)
- [ ] No images requiring horizontal scroll to view fully

### Case Study Pages
- [ ] Diagrams scale or have a scroll affordance if wide
- [ ] Tables scroll horizontally with visual indicator (not hidden)
- [ ] Timeline or flow diagrams readable without zooming
- [ ] Access bar / buttons accessible and not clipped

### Performance Signals
- [ ] No visible layout shift on load
- [ ] Images don't cause reflow after load

---

## How to Test

### Browser DevTools
1. Open browser DevTools (F12 / Cmd+Option+I)
2. Toggle device toolbar (Cmd+Shift+M in Chrome)
3. Set width to 375px
4. Scroll through every page section
5. Check each item in the checklist

### Playwright (automated)
```javascript
// Quick overflow check at 375px
const { chromium } = require('playwright');
(async () => {
  const browser = await chromium.launch();
  const page = await browser.newPage();
  await page.setViewportSize({ width: 375, height: 812 });
  await page.goto('YOUR_URL');
  const overflow = await page.evaluate(() => {
    const els = document.querySelectorAll('*');
    const overflows = [];
    els.forEach(el => {
      if (el.scrollWidth > document.body.offsetWidth) {
        overflows.push(el.tagName + ' ' + el.className);
      }
    });
    return overflows;
  });
  console.log('Overflow elements:', overflow);
  await browser.close();
})();
```

---

## Output Format

```
## Mobile QA Report

### Test Date: [date]
### URL: [url]
### Viewport: 375px

---

### Issues Found

| # | Issue | Location | Severity | Fix |
|---|---|---|---|---|
| 1 | [describe issue] | [section/page] | High/Med/Low | [specific fix] |

---

### Passed Checks
[list what is working correctly]

---

### Priority Fix List
1. [highest severity issue + exact fix]
2.
3.

---

### Notes
[anything that works but could be improved]
```

---

## Severity Definitions

- **High** -- Breaks usability. User cannot accomplish a task or read content.
- **Medium** -- Degrades experience. Requires extra effort but task is completable.
- **Low** -- Minor polish issue. Noticeable but does not block anything.
