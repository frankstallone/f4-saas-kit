# AI Marketing Design Guidance 

_Last updated: 2026-02-07_

## Purpose

Use this file to steer AI-generated public marketing pages.

Default target vibe: product-first, restrained, credible, and conversion-oriented.

This guidance supports one default baseline plus optional visual variants.  
Narrative clarity, product proof, accessibility, and conversion clarity are required in all variants.

## Linear-Inspired Synthesis (What We Borrow, Not Copy)

Observed on `linear.app` and linked brand/method pages:
- Tight, minimal hero with immediate product context and clear CTA.
- Neutral palette with disciplined accent use.
- Strong typographic hierarchy and concise copy blocks.
- Section rhythm that moves from value to proof to capability to action.
- Motion used to orient users and reinforce clarity, not for spectacle.
- Trust framing through customers, security posture, and engineering rigor.

Use these as interaction and information-design principles, not as visual cloning instructions.

## Core Rules for Marketing Surfaces

### 1) Narrative Before Density
- Lead with a specific value proposition in one sentence.
- Sequence sections intentionally: hero -> proof -> feature depth -> trust -> CTA.
- Keep content modular, but prioritize story flow over dashboard compactness.
- Use whitespace to improve reading pace.

### 2) Product-First Visual Proof
- Make product UI artifacts (screenshots, short demos, diagrams) primary evidence.
- Pair every claim with concrete proof.
- Avoid generic stock imagery as core storytelling.

### 3) Neutral Brand Expression
- Keep base surfaces restrained (mostly neutral tones).
- Use one accent color intentionally for emphasis and actions.
- Let typography and layout carry hierarchy; avoid decorative overload.

### 4) Motion for Orientation
- Use subtle reveal/transition patterns to guide reading order.
- Keep common transitions short and unobtrusive.
- Respect `prefers-reduced-motion`.

### 5) Conversion Clarity
- Ensure each section answers: what it is, why it matters, what to do next.
- Keep CTA language explicit and consistent.
- Include trust signals without clutter: customer logos, metrics, compliance/security references.

## Visual Profiles

### Profile A: Product-Credible Minimal (Default)
- Use restrained surfaces, disciplined accent color, and concise typography-led hierarchy.
- Keep visual identity understated and product-proof first.
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
- Build sections with a clear narrative progression, not isolated feature tiles.
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
- Excessive glow/blur stacks that reduce legibility of copy and CTAs.
- Visual spectacle replacing concrete product evidence.
- Cinematic treatment without a clear narrative progression.

## Acceptance Checklist (Per Page)

- Does the page tell a clear story from value proposition to CTA?
- Are product screenshots/artifacts doing real explanatory work?
- Is expression restrained and intentional?
- Are trust signals present and easy to scan?
- Does motion improve comprehension rather than distract?
- Does the page feel premium and credible without feeling loud?
- If using `Profile B`, does the atmospheric styling still preserve readability and conversion clarity?
