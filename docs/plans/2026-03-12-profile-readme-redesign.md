# Profile README Redesign Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Replace the current profile README with an English-first, product-and-platform-focused profile and add a Korean companion README that cross-links cleanly.

**Architecture:** Keep the public profile concise in `README.md` and move richer Korean context to `README.ko.md`. Use a restrained set of common GitHub README widgets: language switch links, optional shields-style quick-link badges, and low-priority stats at the bottom.

**Tech Stack:** Markdown, GitHub profile README, shields.io, github-readme-stats, optional skillicons.dev

---

### Task 1: Replace The English README Header And Navigation

**Files:**
- Modify: `README.md`

**Step 1: Rewrite the top of `README.md`**

Replace the current greeting/profile-generator content with:

- language switch line: `EN | KR`
- main heading: `# KyeongSoo Yoo`
- hero line: `I build mobile products and improve the platforms teams use to ship them.`
- 2-line supporting intro
- quick links block for LinkedIn, Blog, and Email

Do not add stats or stack icons yet.

**Step 2: Verify the new header structure is present**

Run:

```bash
rg -n '^\[EN\]|^# KyeongSoo Yoo|^I build mobile products' README.md
```

Expected:

- One line for the language switch
- One line for `# KyeongSoo Yoo`
- One line for the hero statement

**Step 3: Check for markdown formatting issues**

Run:

```bash
git diff --check -- README.md
```

Expected: no output

**Step 4: Commit**

```bash
git add README.md
git commit -m "feat: rewrite english profile header"
```

### Task 2: Add Impact And Selected Work To The English README

**Files:**
- Modify: `README.md`

**Step 1: Add the `Impact` section**

Add five short bullets covering:

- polygon rendering improvement
- release automation improvement
- onboarding improvement
- asset compression improvement
- project setup reduction

Use metrics exactly where already validated in the design doc.

**Step 2: Add the `Selected Work` section**

Add three entries only:

- `GCOO`
- `AI Delivery Pipeline at Dable`
- `Mobile Platform Template`

Each entry should have:

- one-sentence context line
- two to four result-focused bullets

**Step 3: Verify the key sections exist**

Run:

```bash
rg -n '^## Impact|^## Selected Work|^### GCOO|^### AI Delivery Pipeline at Dable|^### Mobile Platform Template' README.md
```

Expected: one match for each heading

**Step 4: Review the diff for density and readability**

Run:

```bash
git diff -- README.md
```

Expected:

- no leftover HTML blocks from the old generated README
- no oversized icon wall
- no empty sections

**Step 5: Commit**

```bash
git add README.md
git commit -m "feat: add profile impact and selected work"
```

### Task 3: Add Working Style, Focused Stack, And Supporting Widgets

**Files:**
- Modify: `README.md`

**Step 1: Add the approved `How I Work` section**

Use the approved four bullets from the design doc exactly unless a final wording tweak improves readability without changing meaning.

**Step 2: Add a compact `Focused Stack` section**

Group technologies by capability:

- Product Engineering
- Platform & Delivery
- Backend & System Design
- Ways of Working

Prefer plain markdown text. Add a very compact skill icon row only if the section feels too text-heavy after review.

**Step 3: Add `GitHub at a Glance`**

Add one or two `github-readme-stats` cards at the bottom only.

Constraints:

- stats must remain visually subordinate to the main content
- do not add trophy walls
- do not add visitor counters as major elements
- do not add typing animation headers

**Step 4: Verify the final English README structure**

Run:

```bash
rg -n '^## How I Work|^## Focused Stack|^## GitHub at a Glance' README.md
```

Expected: one match for each heading

**Step 5: Check formatting**

Run:

```bash
git diff --check -- README.md
```

Expected: no output

**Step 6: Commit**

```bash
git add README.md
git commit -m "feat: finish english profile content"
```

### Task 4: Create The Korean Companion README

**Files:**
- Create: `README.ko.md`
- Modify: `README.md`

**Step 1: Create `README.ko.md`**

Structure the Korean companion around:

- language switch
- Korean profile summary
- career overview
- detailed achievements
- selected projects
- stack summary
- links back to English README, LinkedIn, Blog, Email

The Korean document can carry more narrative and context than the English profile.

**Step 2: Add reciprocal linking**

Ensure:

- `README.md` links to `README.ko.md`
- `README.ko.md` links back to `README.md`

**Step 3: Verify the cross-links**

Run:

```bash
rg -n 'README\\.ko\\.md|README\\.md' README.md README.ko.md
```

Expected:

- English README references `README.ko.md`
- Korean README references `README.md`

**Step 4: Check formatting**

Run:

```bash
git diff --check -- README.md README.ko.md
```

Expected: no output

**Step 5: Commit**

```bash
git add README.md README.ko.md
git commit -m "feat: add korean companion profile"
```

### Task 5: Final Verification And Cleanup

**Files:**
- Verify: `README.md`
- Verify: `README.ko.md`

**Step 1: Check final section order**

Run:

```bash
rg -n '^# |^## ' README.md README.ko.md
```

Expected:

- English README includes the approved section order
- Korean README has a readable top-to-bottom flow without empty headings

**Step 2: Confirm removed legacy content**

Run:

```bash
rg -n 'Hi 👋|Languages and Tools|Connect with me|komarev|github-readme-stats.vercel.app/api/top-langs\\?username=yoogomja&show_icons=true&locale=en&layout=compact' README.md
```

Expected:

- no old profile-generator text remains
- only the intentionally selected stats card URLs remain

**Step 3: Inspect the final diff**

Run:

```bash
git diff -- README.md README.ko.md
```

Expected:

- concise English profile
- richer Korean companion document
- restrained widget usage
- no accidental leftover HTML snippets

**Step 4: Manual rendering check**

Review both files in GitHub-flavored markdown preview locally or after push.

Expected:

- language switch is visible
- quick links are easy to scan
- sections are not overly long
- stats stay visually secondary

**Step 5: Commit final polish if needed**

```bash
git add README.md README.ko.md
git commit -m "chore: polish profile readme presentation"
```
