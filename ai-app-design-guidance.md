# AI App Design Guidance (F4 SaaS Kit)

_Last updated: 2026-02-07_

## Purpose

Use this file to steer AI-generated product UI inside authenticated app surfaces.

Target vibe: dense, high-signal, neutral, precise, and premium without visual excess.

## Core Rules

### 1) Density Without Clutter
- Keep substantial information visible above the fold.
- Use strict hierarchy: headers, tabs, sub-panels, and section labels should make scan paths obvious.
- Prefer compact spacing and deliberate alignment over large empty gutters.
- Increase information density with structure, not decoration.

### 2) Neutral, Typography-Led UI
- Use type scale, weight, rhythm, and spacing as the primary visual language.
- Keep color restrained and functional; avoid accent-heavy palettes by default.
- Prefer borders and dividers over heavy card stacks and deep shadows.
- Use crisp, simple iconography with consistent stroke and sizing.

### 3) Motion as Feedback
- Animate state transitions that improve comprehension: hover, focus, selection, loading, completion.
- Keep transitions short and subtle; avoid ornamental motion.
- Use motion to preserve continuity between states so the app feels fast.
- Respect `prefers-reduced-motion`.

### 4) Power-User Ergonomics
- Treat keyboard shortcuts as a first-class UX surface.
- Include discoverability: shortcut hinting and searchable shortcut help.
- Prioritize fast navigation and low-friction data entry.
- Ensure core actions can be completed efficiently without pointer-only flows.

### 5) System Feel
- Design interfaces to feel like polished utilities, not marketing pages.
- Favor predictable layouts, consistent controls, and strong interaction patterns.
- Keep chrome light and purposeful so workflow remains central.

## Implementation Defaults for Codex

- Use accessible primitives and App Router-friendly patterns.
- Prefer split views, tabs, and collapsible sections for dense workflows.
- Keep component states explicit: `default`, `hover`, `focus`, `active`, `loading`, `error`, `success`, `disabled`.
- Add keyboard support and visible focus styles for all interactive elements.
- Avoid novelty patterns unless explicitly requested.

## Anti-Patterns

- Large decorative gradients as primary identity for product screens.
- Oversized cards with excessive padding that reduce information throughput.
- Animation used for style instead of interaction clarity.
- Hidden shortcut systems with no discoverability.
- Inconsistent visual language across panels and controls.

## Acceptance Checklist (Per Screen)

- Is the screen information-dense but still easy to scan?
- Is hierarchy driven by type and spacing rather than color noise?
- Are borders/dividers doing more work than heavy containers?
- Do transitions explain state changes in under ~200ms for common interactions?
- Can a power user navigate core actions primarily via keyboard?
- Does the result feel like a focused system tool?
