# Design Tokens

_Last updated: 2026-02-08_

## Token Files

- Raw tonal palette source of truth: `design/tokens/f4-tonal-palette.css`
- Semantic mapping layer: `design/tokens/semantic-theme.css`

Use both files in a starter app `app/globals.css`:

```css
@import '@/design/tokens/f4-tonal-palette.css';
@import '@/design/tokens/semantic-theme.css';
```

## Token Workflow

- Keep `f4-tonal-palette.css` machine-generated from F4 Tonal Factory.
- Do not hand-edit raw scale weights.
- Tune product and marketing appearance through semantic mappings only.
- Validate contrast for each semantic foreground/background pairing.

## Mise en Mode <-> Tonal Categories Mapping

Purpose category mapping (recommended):

- Surface (containers, overlays): Highlights in light mode (`000/025/050`) -> Shadows in dark mode (`900/950/999`)
- Action (interactive buttons): Mid Tones for fills (`400-600`), with highlight text on dark fills
- Control (inputs/selects): surface treatment + 1/4 Tone borders + Mid Tone focus rings
- Text and icons: 3/4 Tones + Shadows in light mode (`650-900`), Highlights in dark mode (`025-050`)
- Borders and dividers: 1/4 Tones only (`100-350`) in light mode; nearest step above base surface in dark mode (`800-850`)

## Starter Token Matrix

### Light mode

- `surface.page`: `075`
- `surface.content`: `050`
- `surface.raised`: `025`
- `surface.overlay`: `000`
- `control.border`: `150-200`
- `control.focusRing`: `450-550`
- `action.primary.bg`: `550` (`hover: 600`, `pressed: 650`)
- `text.primary`: `900`
- `text.secondary`: `650-700`
- `border.default`: `150`

### Dark mode

- `surface.page`: `950`
- `surface.content`: `800`
- `surface.raised`: `900`
- `surface.overlay`: `999`
- `control.border`: `850-800`
- `control.focusRing`: `450-550`
- `action.primary.bg`: `550` (`hover: 600`, `pressed: 650`)
- `text.primary`: `050`
- `text.secondary`: `300`
- `border.default`: `850`

## Agent Reasoning Rules

Source abstracted from:

- `/Users/starlord/Downloads/The universal color palette. Supporting a global design system at… _ by Kevin Muldoon _ UX Collective.pdf`

Rules:

- Model every token as `variant + weight` (example: `primary-550`, `neutral-200`).
- Use only the fixed 22-step weights:
- `000, 025, 050, 100, 150, 200, 250, 300, 350, 400, 450, 500, 550, 600, 650, 700, 750, 800, 850, 900, 950, 999`
- Route decisions by tonal category first:
- Highlights: `000, 025, 050`
- 1/4 tones: `100-350`
- Mid tones: `400-600`
- 3/4 tones: `650-900`
- Shadows: `950, 999`
- Map role to category before choosing exact weight.
- Accessibility defaults:
- `500` is a practical baseline against `000` and `999`
- `550` is a safer baseline for text on Highlight surfaces
- Convert brand colors to nearest existing L* target; never invent new weights.
- Reserve `000` and `999` for neutral by default.
- Curate a subset of weights per product; do not force all 22 weights.
