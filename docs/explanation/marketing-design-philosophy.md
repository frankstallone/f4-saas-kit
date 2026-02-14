# AI Marketing Design Guidance 

_Last updated: 2026-02-14_

## Purpose

Use this file to steer AI-generated public marketing pages.

Default target vibe: product-first, restrained, credible, and conversion-oriented.

This guidance supports one default baseline plus optional visual variants.  
Narrative clarity, product proof, accessibility, and conversion clarity are required in all variants.

## Linear-Inspired Synthesis (What We Borrow, Not Copy)

Observed on `linear.app` and linked brand/method pages:
- Fewer, stronger sections where each block has one clear job.
- Concise claims paired with visible product evidence.
- Neutral-first surfaces with disciplined accent usage.
- Editorial precision in spacing, typography, and separators.
- Motion used for orientation and continuity, never spectacle.
- Trust built through concrete operational credibility, not badge overload.

Use these as interaction and information-design principles, not as visual cloning instructions.

## Core Rules for Marketing Surfaces

### 1) Narrative Grammar Before Density
- Lead with a specific value proposition in one sentence.
- Sequence sections intentionally: promise -> proof -> depth -> trust -> CTA.
- Keep content modular, but prioritize story flow over dashboard compactness.
- Give each section one primary point and one clear next action.

### 2) Product-First Proof Density
- Make product UI artifacts (screenshots, short demos, diagrams) primary evidence.
- Pair every major claim with concrete proof.
- Avoid generic stock imagery as core storytelling.
- Use annotations and captions to explain why the artifact matters.

### 3) Copy Compression and Clarity
- Keep headlines direct and specific; avoid abstract brand slogans as primary copy.
- Favor short paragraphs and tight bullets over long marketing prose.
- Reduce repetition across sections; each section should add net-new information.

### 4) Neutral Brand Expression
- Keep base surfaces restrained (mostly neutral tones).
- Use one accent color intentionally for emphasis and actions.
- Let typography and layout carry hierarchy; avoid decorative overload.
- Prefer crisp boundaries (lines, spacing, alignment) over heavy effects.

### 5) Motion for Orientation
- Use subtle reveal/transition patterns to guide reading order.
- Keep common transitions short and unobtrusive.
- Respect `prefers-reduced-motion`.

### 6) Conversion Clarity
- Ensure each section answers: what it is, why it matters, what to do next.
- Keep CTA language explicit and consistent.
- Include trust signals without clutter: customer logos, metrics, compliance/security references.

## Visual Profiles

### Profile A: Product-Credible Precision (Default)
- Use restrained neutral surfaces, disciplined accent color, and typography-led hierarchy.
- Design with editorial precision: strong spacing rhythm, clean separators, and consistent alignment.
- Keep artifacts central: product UI evidence should carry the narrative, not decorative graphics.
- Keep copy compact and concrete; avoid inflated language and repeated claims.
- Optimize for clarity, trust, and conversion speed.

### Profile B: Cinematic Futurist (Optional Variant)
- Use dark-first atmospheric surfaces with controlled luminous accents.
- Build strong hero presence with depth, glow, and high-contrast composition.
- Keep product screenshots/demos central, framed with higher visual drama.
- Use larger typographic moments and tighter copy blocks for punchy storytelling.
- Maintain a clear section arc: hero -> proof -> capabilities -> trust -> CTA.
- Keep effects purposeful; atmosphere must not obscure meaning.

## Variant Selection Rules

- Start with `Profile A` by default.
- Use `Profile B` when brand intent calls for ambitious, high-energy storytelling.
- Keep information architecture, CTA logic, and trust framing consistent across profiles.
- If uncertain, ship `Profile A`.

## Implementation Defaults for Codex

- Decide profile first: `Profile A` (default) or `Profile B` (optional).
- Build sections with clear narrative progression, not isolated feature tiles.
- Assign each section one core message, one proof element, and one action state.
- Keep heading/body/caption scale consistent across the page.
- Prefer crisp separators, spacing rhythm, and restrained elevation.
- Make CTA hierarchy obvious: one primary, optional secondary.
- Keep page performance high; avoid heavy effects that delay content comprehension.

## Anti-Patterns

- Abstract visual treatments with weak product proof.
- Long pages with no narrative arc.
- Accent colors competing across many sections.
- Decorative animation that competes with content.
- Marketing pages that read like dashboard UI clones.
- Generic "feature grid" pages with weak narrative flow.
- Excessive glow/blur stacks that reduce legibility of copy and CTAs.
- Visual spectacle replacing concrete product evidence.
- Cinematic treatment without a clear narrative progression.

## Acceptance Checklist (Per Page)

- Does the page tell a clear story from value proposition to CTA?
- Are product screenshots/artifacts doing real explanatory work?
- Does each section have one clear message, one proof, and one next step?
- Is expression restrained and intentional?
- Are trust signals present and easy to scan?
- Does motion improve comprehension rather than distract?
- Does the page feel premium and credible without feeling loud?
- If using `Profile B`, does the atmospheric styling still preserve readability and conversion clarity?
