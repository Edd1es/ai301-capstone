# Contribution 1: Fix incorrect "2D prefix sums" link in Silver Custom Comparators module

**Contribution Number:** 1
**Student:** Eddie Olvera
**Issue:** [cpinitiative/usaco-guide#6196 — Contact Form Submission - Mistake (Silver - Custom Comparators and Coordinate Compression)](https://github.com/cpinitiative/usaco-guide/issues/6196)
**Status:** Phase I Complete

---

## Why I Chose This Issue

This is a tightly scoped content fix: a contact-form report flagged that in Example 1 of the Silver "Custom Comparators and Coordinate Compression" module, the in-text link labeled "2D prefix sums" points to the wrong destination. The fix is to correct a single hyperlink in one MDX file — easy to verify, low-risk to submit, with an obvious definition of done.

As a TF I deliberately picked something smaller than what students will take on, so I can run the full contribution loop — claim, fork, fix, PR, maintainer review — end to end and quickly, and speak to each phase from direct experience during standups. USACO Guide is actively maintained (contact-form issues are triaged within days), it's the same project a fellow TF contributed to successfully, and MDX needs almost no local setup, so Phase II won't bottleneck me.

**Feasibility check:** scope tiny (one link, one file); verifiable by eye; unclaimed (no assignee, no PR, reporter declined); maintainer responsive. Weakest point: I still need to confirm in Phase II exactly which guide page the link *should* target (the 2D prefix sums section) — a quick lookup, not a design decision.

---

## Understanding the Issue

### Problem Description
On the Silver "Custom Comparators and Coordinate Compression" page (https://usaco.guide/silver/sorting-custom), the link in Example 1 labeled "2D prefix sums" points to an incorrect URL.

### Expected Behavior
The "2D prefix sums" link should navigate the reader to the guide's 2D prefix sums section/module.

### Current Behavior
The link resolves to the wrong destination (exact wrong target to be pinned down during reproduction).

### Affected Components
A single MDX module file in the usaco-guide content directory for the Silver "Sorting with Custom Comparators" module (confirm exact path in the repo during Phase II — likely under `content/3_Silver/`).

---

## Reproduction Process
*(Phase II — fill in Week 2)*

### Environment Setup
[Notes on setting up the local dev environment — challenges and how you solved them.]

### Steps to Reproduce
1. Open the live page: https://usaco.guide/silver/sorting-custom
2. Find Example 1 and click the "2D prefix sums" link.
3. Observe it lands on the wrong page; identify the correct target page in the guide.

### Reproduction Evidence
- **Commit showing reproduction:** [link to commit in your fork]
- **Screenshots/logs:** [before/after of the link target]
- **My findings:** [the wrong URL currently used vs. the correct one]

---

## Solution Approach
*(Phase II/III)*

### Analysis
[Root cause — likely a wrong/relative MDX link path in Example 1.]

### Proposed Solution
[Replace the incorrect link target with the correct guide page URL/path.]

### Implementation Plan (UMPIRE)
**Understand:** The "2D prefix sums" link in Example 1 points to the wrong page.
**Match:** Find how other MDX pages link internally to the 2D prefix sums section; mirror that exact link style.
**Plan:**
1. Locate the module's MDX file in `content/`.
2. Find the "2D prefix sums" link in Example 1.
3. Replace the target with the correct internal link, matching existing link conventions.

**Implement:** [Links to your branch/commits.]
**Review:** [Self-review against CONTRIBUTING + check the rendered page locally.]
**Evaluate:** [Confirm the link resolves correctly in local preview.]

---

## Testing Strategy
*(Phase III)*

### Manual Testing
[Build the site locally, open the module, click the corrected link, confirm it lands on the right page.]

---

## Implementation Notes
*(Phase III — update as you build)*

### Week [X] Progress
[What you did, challenges, decisions.]

### Code Changes
- **Files modified:** [list]
- **Key commits:** [links]

---

## Pull Request
*(Phase IV)*

**PR Link:** [URL when submitted]
**PR Description:** [adapt from the sections above]

**Maintainer Feedback:**
- [Date]: [summary]
- [Date]: [how you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections
*(fill in as you go)*

### Technical Skills Gained
[…]

### Challenges Overcome
[…]

### What I'd Do Differently Next Time
[…]

---

## Resources Used
- Issue: https://github.com/cpinitiative/usaco-guide/issues/6196
- Affected page: https://usaco.guide/silver/sorting-custom
- usaco-guide CONTRIBUTING.md