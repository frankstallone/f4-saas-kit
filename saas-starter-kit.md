# SaaS Starter Kit

_Last updated: 2026-02-08_

## 1) Technical Profile of the Current App

### Core stack
- **Framework:** Next.js `16.1.1` (App Router, React Server Components, Server Actions, Route Handlers)
- **Runtime:** Node.js `>=24 <25`
- **Language:** TypeScript `5.9.3` (strict mode)
- **React:** `19.2.3`
- **React Compiler:** Enabled in Next.js config (`reactCompiler: true`)

### UI and styling
- **CSS framework:** Tailwind CSS v4 (`tailwindcss`, `@tailwindcss/postcss`)
- **Component system:** shadcn CLI with Base UI (`@base-ui/react`, style `base-maia`)
- **Icons:** `lucide-react`
- **Toasts:** `sonner`
- **Animation helpers:** `tw-animate-css`
- **Typography:** `next/font` with DM Sans
- **Theme engine:** `next-themes`
- **Theming:** CSS variables + OKLCH tokens in `app/globals.css`; dark mode via `.dark` class

### Auth and access control
- **Auth library:** Better Auth (`better-auth`)
- **Provider:** Google OAuth
- **Session integration:** `better-auth/next-js` with `nextCookies()` plugin
- **Access control:** Optional email allowlist via `ALLOWED_EMAILS`
- **Auth routes:** `app/api/auth/[...all]/route.ts`

### Data layer
- **Database:** PostgreSQL (Neon-compatible)
- **Query layer:** Kysely `0.28.x`
- **DB driver/runtime:** `@neondatabase/serverless` (app queries), `pg` (Better Auth pool + scripts)
- **Schema/migrations:** SQL-first in `db/migrations/` + reference schema in `db/schema.sql`
- **Data access pattern:** `lib/data/*` modules + typed DB schema in `lib/db-types.ts`

### Storage and uploads
- **Storage abstraction:** Provider-based adapter in `lib/storage`
- **Supported providers:** S3-compatible (default), Vercel Blob, local disk
- **Upload pattern:** App issues upload targets from `/api/storage/upload-target`, client uploads directly
- **Guards:** MIME allowlist + max upload size checks

### External integrations
- **Unsplash integration:** Search + download tracking APIs under `app/api/unsplash/*`
- **Rate limiting:** In-memory limiter (`lib/rate-limit.ts`) for Unsplash endpoints

### Product/runtime features
- **PWA:** `next-pwa` + `public/manifest.webmanifest`
- **Image handling:** `next/image` remote patterns for Unsplash, Google avatars, and storage endpoints

### Quality and delivery
- **Linting:** ESLint 9 + Next core-web-vitals config
- **Formatting:** Prettier 3
- **Tests:** Vitest `4.x`
- **Git hooks:** Husky + lint-staged
- **CI:** GitHub Actions (lint/test/build)
- **Release automation:** release-please workflows on `main`
- **Deploy target:** Vercel (`vercel.json` present)

### License
- **Current license:** `O'Saasy License`
- **Important note:** It includes a restriction against using derivatives to compete as a hosted/SaaS product.

## 2) Reusable Patterns We Should Keep in the Starter

- App Router + Server Actions for most product CRUD flows.
- SQL migrations committed to git and run via a simple script.
- Typed data layer (`lib/data/*`) separated from UI components.
- Auth wrapper helpers (`getServerSession`, `requireServerSession`, allowlist logic).
- Storage provider abstraction so app code is cloud-vendor-neutral.
- Environment validation via Zod before app startup.
- TanStack recommendation: use TanStack primitives as defaults for complex UI/data workflows (`@tanstack/react-table` now; evaluate other TanStack packages per feature needs).
- CI + release automation wired from day one.

## 3) What to Add Next to This Document

### A. Starter product definition
- Define **which starter variants** you want:
  - Private SaaS app starter
  - Public marketing site starter
  - Combined mono-repo starter (recommended)
- Define your default assumptions: auth required or not, billing required or not, multi-tenant or single-tenant.

### B. Repo/template strategy (so you stop duplicating private repos)
- Create one **GitHub template repo** for this stack.
- Add a **post-clone bootstrap script** that renames app title, env keys, and metadata.
- Keep app-specific business logic in `features/*` so new products can replace features, not infra.

### C. Licensing strategy for public repos
- Pick an explicit default for template usage:
  - `MIT` (max adoption)
  - `Apache-2.0` (patent grant)
  - Source-available (if you want anti-competition restrictions)
- If marketing sites are public, decide whether starter code and product code share the same license.

### D. Marketing-site baseline
- Document a default route structure (example):
  - `/` landing
  - `/pricing`
  - `/docs`
  - `/blog`
  - `/legal/*`
- Add default SEO package: metadata, OG image generation, sitemap, robots, analytics, cookie consent.

### E. SaaS baseline modules
- Org/account model (single-user vs team/org).
- Billing stub (Stripe/Lemon/etc.) with webhooks and entitlements table.
- Email provider and transactional templates.
- Audit log table and admin events.
- Feature flags and plan gating.

### F. Production hardening checklist
- Replace in-memory rate limit with Redis/Upstash in production.
- Add idempotency keys for mutation endpoints.
- Add background job queue for slow workflows.
- Add observability: structured logs, error tracking, uptime alerts.
- Add backup/restore and migration rollback strategy.

### G. Developer experience checklist
- `make bootstrap` or `npm run setup` command.
- `.env` validation script that fails fast with clear messages.
- Seed data profiles (`demo`, `staging`, `test`).
- One-command local infra (db + redis) via Docker Compose.

## 4) Immediate Next Moves

1. Convert this repo into a **template-oriented core** (infra + auth + data + storage only).
2. Extract F4 domain logic into a feature package (`features/goals`).
3. Publish a new `starter-saas-next` repo as public template.
4. Add a second template mode for marketing-only builds.
5. Decide final template license before publishing.

## 5) AI Design Steering

- Keep AI-facing design rules split by surface.
- Use `ai-app-design-guidance.md` for authenticated product UI.
- Use `ai-marketing-design-guidance.md` for public marketing pages.
- Use `saas-starter-kit.md` for stack, architecture, and template decisions.

## 6) Design Tokens (Tailwind v4)

- Raw tonal palette source of truth: `design/tokens/f4-tonal-palette.css`
- Semantic mapping layer: `design/tokens/semantic-theme.css`

Use both files in the starter app `app/globals.css`:

```css
@import '@/design/tokens/f4-tonal-palette.css';
@import '@/design/tokens/semantic-theme.css';
```

Token workflow:

- Keep `f4-tonal-palette.css` machine-generated from F4 Tonal Factory.
- Do not hand-edit raw scale weights.
- Tune product/marketing appearance by adjusting only semantic mappings.
- Validate contrast for each semantic foreground/background pairing before release.

### Mise en Mode ↔ Tonal Categories Mapping

Purpose category mapping (recommended):

- Surface (containers, overlays): Highlights in light mode (`000/025/050`) -> Shadows in dark mode (`900/950/999`).
- Action (interactive buttons): Mid Tones for fills (`400-600`), with text in Highlights on dark fills.
- Control (form inputs/selects): treat as surfaces, with borders in 1/4 Tones and focus rings in Mid Tones.
- Text and icons: 3/4 Tones + Shadows in light mode (`650-900`), Highlights in dark mode (`025-050`).
- Borders and dividers: 1/4 Tones only (`100-350`) in light mode; nearest step above base surface in dark mode (typically `800-850`).

Starter token matrix:

Light mode:

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

Dark mode:

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

### Agent Reasoning for Palette, Scales, Weights, and Tonal Categories

Source abstracted from:

- `/Users/starlord/Downloads/The universal color palette. Supporting a global design system at… _ by Kevin Muldoon _ UX Collective.pdf`

Rules for agents:

- Model every color token as `variant + weight` (for example: `primary-550`, `neutral-200`).
- Use only the fixed 22-step weights: `000, 025, 050, 100, 150, 200, 250, 300, 350, 400, 450, 500, 550, 600, 650, 700, 750, 800, 850, 900, 950, 999`.
- Route decisions by tonal category first:
- Highlights: `000, 025, 050`
- 1/4 tones: `100-350`
- Mid tones: `400-600`
- 3/4 tones: `650-900`
- Shadows: `950, 999`
- Map role to category before picking exact weight:
- Surfaces in light mode: Highlights
- Surfaces in dark mode: Shadows
- Borders/dividers: 1/4 tones
- Control fills/actions: usually Mid tones
- Text/icons: Mid tones minimum; usually 3/4 + Shadows in light mode
- Accessibility defaults:
- `500` is a practical baseline against `000` and `999`
- `550` is a safer baseline for text on Highlight surfaces
- Convert brand colors by nearest L* target to an existing weight; do not invent new weight steps.
- Preserve endpoint discipline: reserve absolute extremes (`000` and `999`) for neutral by default.
- Curate a subset of weights per product; do not force use of all 22 weights.
