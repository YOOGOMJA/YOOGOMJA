# Profile README Redesign Design

## Goal

Redesign the GitHub profile README to present KyeongSoo Yoo as a product-minded mobile engineer who also improves the platforms, workflows, and team systems used to ship products.

The README should feel hiring-friendly without reading like a job-seeking landing page. It should work as a public profile first, while still helping domestic hiring managers and engineers quickly understand strengths, scope, and impact.

## Audience

- Hiring managers and interviewers evaluating senior frontend/mobile candidates
- Engineers who may collaborate, hire, or refer
- Public visitors who need a fast overview plus links to deeper Korean materials

## Positioning

Primary positioning:

> I build mobile products and improve the platforms teams use to ship them.

Supporting framing:

- Product delivery
- Performance optimization
- Release/platform improvement
- AI-assisted engineering workflows

This positioning intentionally avoids leading with `architect`, `full-stack`, or `frontend` as the main headline. Those are supporting capabilities, not the first impression.

## Language Strategy

- `README.md`: English-first public profile
- `README.ko.md`: Korean detailed profile/resume companion
- Both documents should cross-link each other

Top-level language switch:

```md
[EN](./README.md) | [KR](./README.ko.md)
```

Design decision:

- Place language links above the main name heading
- Keep them visually light because they are navigation, not headline content

## Information Architecture

Recommended README structure:

1. Language switch
2. Name
3. Hero statement
4. Quick links
5. Impact
6. Selected Work
7. How I Work
8. Focused Stack
9. GitHub at a Glance

### 1. Header

Name remains the strongest visual anchor.

Hero copy:

```md
I build mobile products and improve the platforms teams use to ship them.
```

Supporting intro:

```md
Frontend engineer with 9+ years of experience across React Native, TypeScript, and Node.js.
I focus on product delivery, performance, and developer platforms that help teams ship faster with less friction.
```

### 2. Quick Links

Quick links should be separate from language links.

Recommended links:

- LinkedIn
- Blog
- Email

Rationale:

- `EN | KR` is document navigation
- Quick links are external profile/contact navigation

### 3. Impact

Lead with quantified outcomes, not tool names.

Initial candidate bullets:

- Improved polygon rendering time by `58.19%`
- Reduced release time by `76.6%`
- Shortened onboarding time by `40%`
- Reduced asset size by `83.51%`
- Cut new project setup time from `2 weeks` to `3 days`

### 4. Selected Work

Keep this section to three entries.

Recommended entries:

#### GCOO

- Large-scale mobility app used by 1.5M monthly active users
- Performance, release automation, and delivery improvements

#### AI Delivery Pipeline at Dable

- AI-assisted ad widget implementation pipeline
- Reduced implementation time by more than 90%
- Reduced issue investigation/code understanding time by 90%
- Standardized frontend AI collaboration practices

#### Mobile Platform Template

- Shared Turborepo + Expo + FSD template
- Reduced setup time from 2 weeks to 3 days
- Standardized reusable delivery conventions and libraries

`Haffn` remains valuable, but should move to Korean detailed profile or a secondary section if space becomes tight. The selected trio better reinforces the current public positioning.

### 5. How I Work

Approved copy:

```md
## How I Work

- I build products with a strong focus on delivery, reliability, and performance.
- I design systems that make repeated work easier to ship and easier to maintain.
- I value shared conventions, automation, and tools that improve team throughput.
- I use AI where it meaningfully reduces implementation time, investigation cost, and coordination overhead.
```

### 6. Focused Stack

This section should be grouped by capability rather than dumped as a long icon wall.

Proposed grouping:

- Product Engineering
- Platform & Delivery
- Backend & System Design
- Ways of Working

## Inline Tooling Research And Decision

The README should use common GitHub profile widgets only where they strengthen navigation or credibility. Decorative or noisy widgets should be avoided.

### Selected

#### 1. Shields.io

Use for small, consistent badges in quick links only if plain text links feel too flat.

Good uses:

- LinkedIn
- Blog
- Email

Why selected:

- Very common in profile READMEs
- Lightweight and easy to maintain
- Fits a professional tone when colors and count are restrained

Source:

- https://shields.io/

#### 2. GitHub Readme Stats

Use at the bottom as supporting material, not as a hero element.

Good uses:

- Overall stats card
- Top languages card

Why selected:

- Familiar and widely adopted
- Easy to place in a low-priority supporting section
- Adds activity context without changing the main narrative

Sources:

- https://github.com/anuraghazra/github-readme-stats

#### 3. Skill Icons or a very compact icon row

Use only if the final stack section feels too text-heavy. Keep to a narrow, curated set of core technologies.

Good uses:

- React Native
- TypeScript
- React
- Node.js
- Playwright
- GitLab

Why conditionally selected:

- Can improve scanability
- Becomes noisy quickly if overused
- Should support the grouped stack section, not replace substance

Sources:

- https://github.com/tandpfun/skill-icons
- https://skillicons.dev/

### Rejected Or Deprioritized

#### 1. Typing animation headers

Rejected for the main design because they feel more decorative than informative for a senior professional profile.

Source:

- https://github.com/DenverCoder1/readme-typing-svg

#### 2. Trophy/achievement walls

Rejected because they overweight gamified profile signals over real product/platform evidence.

#### 3. Visitor counters as major elements

Rejected because they add little signal for the target audience.

#### 4. Summary-card dashboards requiring extra automation

Deprioritized because they add setup/maintenance overhead and visual density without materially improving the core story.

Source:

- https://github.com/vn7n24fzkq/github-profile-summary-cards

## Visual Tone

Target tone:

- Restrained professional
- Slight maker energy
- Low decoration, high evidence

Design rules:

- Avoid large tech icon walls
- Avoid excessive badges
- Use stats only at the bottom
- Prefer concise copy over visual gimmicks

## Success Criteria

- A first-time visitor understands the profile positioning within a few seconds
- The README shows both product impact and platform improvement ability
- The profile feels credible in a 2026 hiring context without looking like a resume dump
- Korean readers can quickly jump to a more detailed Korean document
- Widgets support navigation and credibility without dominating the page

## Implementation Notes

- Keep the English README concise
- Move longer narrative and historical experience to `README.ko.md`
- Use a small number of carefully selected badges/widgets
- Keep the page robust without depending on too many third-party renderers
