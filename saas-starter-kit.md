# SaaS Starter Kit

_Last updated: 2026-02-07_

## 1) Technical Profile of the Current App

### Core stack
- **Framework:** Next.js `16.1.1` (App Router, React Server Components, Server Actions, Route Handlers)
- **Runtime:** Node.js `>=24 <25`
- **Language:** TypeScript `5.9.3` (strict mode)
- **React:** `19.2.3`

### UI and styling
- **CSS framework:** Tailwind CSS v4 (`tailwindcss`, `@tailwindcss/postcss`)
- **Component system:** shadcn CLI with Base UI (`@base-ui/react`, style `base-maia`)
- **Icons:** `lucide-react`
- **Toasts:** `sonner`
- **Animation helpers:** `tw-animate-css`
- **Typography:** `next/font` with DM Sans
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
- **Tests:** Vitest 4
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
