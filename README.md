# Contribution 1: Fix broken "2D prefix sums" link in Silver Custom Comparators module

**Contribution Number:** 1
**Student:** [Your Name]
**Issue:** [cpinitiative/usaco-guide#6196 — Contact Form Submission - Mistake (Silver - Custom Comparators and Coordinate Compression)](https://github.com/cpinitiative/usaco-guide/issues/6196)
**Status:** Phase II Complete

---

## Why I Chose This Issue

This is a tightly scoped content fix: a contact-form report flagged that in Example 1 of the Silver "Custom Comparators and Coordinate Compression" module, the link labeled "2D prefix sums" points to the wrong destination. The fix is to correct a single hyperlink in one MDX file — easy to verify, low-risk to submit, with an obvious definition of done.

As a TF I deliberately picked something smaller than what students will take on, so I can run the full contribution loop — claim, fork, fix, PR, maintainer review — end to end and quickly, and speak to each phase from direct experience during standups. USACO Guide is actively maintained, it's the same project a fellow TF contributed to successfully, and the project is a standard Next.js app, so setup is predictable.

**Feasibility check:** scope tiny (one link, one file); verifiable by eye and by CI; unclaimed (no assignee, no PR, reporter declined); maintainer responsive.

---

## Understanding the Issue

### Problem Description
On the Silver "Custom Comparators and Coordinate Compression" page (https://usaco.guide/silver/sorting-custom), the link in Example 1 labeled "2D-prefix" points to `/silver/prefix-sums-2`, which is not a real module slug, so it 404s.

### Expected Behavior
The "2D prefix sums" link should navigate the reader to the module that teaches 2D prefix sums.

### Current Behavior
The link resolves to `/silver/prefix-sums-2`, a page that does not exist (404).

### Affected Components
`content/3_Silver/Sorting_Custom.mdx` — a single MDX link in the Example 1 section (~line 631).

---

## Reproduction Process

### Environment Setup
- Stack: Next.js / React / TypeScript / MDX, package manager **yarn 4.9.2** (via `packageManager` field).
- Steps: install Node (LTS) → `corepack enable` → `yarn install` → `yarn dev` (first boot runs a content-load script, so it's slower than a normal `next dev`) → site serves at `http://localhost:3000`.
- Notes/challenges: [record any setup friction you hit and how you resolved it — e.g. Corepack/yarn version, install time.]

### Steps to Reproduce
1. Run the site locally with `yarn dev` and open `http://localhost:3000/silver/sorting-custom` (the live site at usaco.guide/silver/sorting-custom shows the same bug).
2. Scroll to **Example 1**.
3. Click the **"2D-prefix"** link.
4. Observe the browser navigates to `/silver/prefix-sums-2` and renders a 404 / page-not-found.
5. Confirm in source: `content/3_Silver/Sorting_Custom.mdx` (~line 631) contains `[2D-prefix](/silver/prefix-sums-2)`.

### Reproduction Evidence
- **Branch:** https://github.com/Edd1es/usaco-guide/tree/fix-issue-6196
- **Screenshot:** [link/attach the 404 screenshot]
- **Findings:** The slug `prefix-sums-2` does not exist anywhere in `content/`. The guide's prefix-sums modules are `prefix-sums` ("Introduction to Prefix Sums") and `more-prefix-sums` ("More on Prefix Sums"); 2D prefix sums are taught in the latter (it has a `## 2D Prefix Sums` section).

---

## Solution Approach

### Analysis (Root Cause)
The MDX author linked to a slug (`/silver/prefix-sums-2`) that was never a valid module id. The content on 2D prefix sums actually lives in the `more-prefix-sums` module, so the intended internal link target is `/silver/more-prefix-sums`.

### Proposed Solution
In `content/3_Silver/Sorting_Custom.mdx`, change the Example 1 link target from `/silver/prefix-sums-2` to `/silver/more-prefix-sums` (optionally with the `#2d-prefix-sums` anchor to land directly on that section). One-line change.

### Implementation Plan (UMPIRE)
**Understand:** The Example 1 "2D-prefix" link points to a non-existent slug and 404s; it should point to the module that teaches 2D prefix sums.

**Match:** Other internal links in this same file already use the correct pattern, e.g. `[prefix sums](/silver/prefix-sums)`. I'll mirror that exact link style.

**Plan:**
1. Edit line ~631 of `content/3_Silver/Sorting_Custom.mdx`.
2. Replace `/silver/prefix-sums-2` with `/silver/more-prefix-sums`.
3. Leave link text and surrounding prose unchanged.

**Implement:** *(Phase III)* — commits on branch `fix-issue-6196`: [link]

**Review:** Self-review against `CONTRIBUTING.md` and the contributing module (usaco.guide/general/contributing); match the repo's commit-message style; run `yarn format`/lint if applicable.

**Evaluate:** Run `yarn dev`, navigate to Example 1, click the link, confirm it now loads "More on Prefix Sums." The repo's CI also runs an internal-link check, which should pass once the slug is valid.

---

## Testing Strategy
*(Phase III)*

### Manual Testing
Build/run locally, open the Custom Comparators module, click the corrected link, confirm it resolves to the More on Prefix Sums module. Confirm no other links in the file changed.

---

## Implementation Notes
*(Phase III — update as you build)*

### Week [X] Progress
[…]

### Code Changes
- **Files modified:** content/3_Silver/Sorting_Custom.mdx
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
- Correct target module: https://usaco.guide/silver/more-prefix-sums
- Setup docs: usaco-guide `docs/Front End Documentation.md`; CONTRIBUTING.md