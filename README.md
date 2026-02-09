# F4 SaaS Kit

Documentation-first foundation for a reusable SaaS starter kit derived from learnings.

## What This Repo Contains

- `saas-starter-kit.md`: technical stack baseline, architecture defaults, and starter strategy.
- `ai-app-design-guidance.md`: design rules for authenticated product UI.
- `ai-marketing-design-guidance.md`: design rules for public marketing surfaces.
- `design/tokens/f4-tonal-palette.css`: raw F4 Tonal Factory palette (`@theme`) source of truth.
- `design/tokens/semantic-theme.css`: semantic token mappings for app usage (light/dark).
- `AGENTS.md`: repository workflow and documentation conventions.

## Purpose

Use this repo as the source of truth for:

- SaaS starter architecture decisions.
- Agent-facing UI/UX guidance for app and marketing surfaces.
- Tailwind v4 token strategy based on fixed tonal weights and categories.

## Design Token Model

The token approach is intentionally split:

1. Keep `f4-tonal-palette.css` machine-generated and stable.
2. Map product semantics in `semantic-theme.css`.
3. Import both in a starter app `app/globals.css`.

```css
@import '@/design/tokens/f4-tonal-palette.css';
@import '@/design/tokens/semantic-theme.css';
```

## Workflow

1. Update architecture decisions in `saas-starter-kit.md`.
2. Update app or marketing guidance in the dedicated AI guidance files.
3. Evolve palette/scales in `design/tokens/*`.
4. Commit docs and token changes together when they affect shared behavior.

## Notes

- This repository currently focuses on standards and guidance docs.
- It does not yet include executable starter app code.
