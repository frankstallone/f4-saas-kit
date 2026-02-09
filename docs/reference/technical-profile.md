# Technical Profile

_Last updated: 2026-02-08_

## Core Stack

- Framework: Next.js `16.1.1` (App Router, RSC, Server Actions, Route Handlers)
- Runtime: Node.js `>=24 <25`
- Language: TypeScript `5.9.3` (strict)
- React: `19.2.3`
- React Compiler: enabled in Next.js config

## UI and Styling

- Tailwind CSS v4 (`tailwindcss`, `@tailwindcss/postcss`)
- shadcn CLI with Base UI (`@base-ui/react`, `base-maia`)
- Icons: `lucide-react`
- Toasts: `sonner`
- Animation helper: `tw-animate-css`
- Fonts: `next/font` with DM Sans
- Theme engine: `next-themes`

## Auth and Access

- Better Auth with `better-auth/next-js` and `nextCookies()`
- Google OAuth provider
- Optional email allowlist via `ALLOWED_EMAILS`
- Auth route pattern: `app/api/auth/[...all]/route.ts`

## Data Layer

- Database: PostgreSQL (Neon-compatible)
- Query builder: Kysely `0.28.x`
- Drivers: `@neondatabase/serverless` (app), `pg` (auth/scripts)
- SQL-first migrations in `db/migrations/`
- Reference schema in `db/schema.sql`

## Storage and Uploads

- Provider abstraction in `lib/storage`
- Supported providers: S3-compatible (default), Vercel Blob, local disk
- Upload flow: app-issued upload targets, then direct upload from client
- Validation guards: MIME allowlist and max file size

## Integrations and Runtime

- Unsplash search/download tracking APIs
- In-memory rate limiter for Unsplash endpoints
- PWA enabled with `next-pwa` and web manifest
- `next/image` remote patterns configured for Unsplash, Google avatars, storage

## Quality and Delivery

- ESLint 9 + Next core-web-vitals
- Prettier 3
- Vitest 4
- Husky + lint-staged
- GitHub Actions: lint, test, build
- release-please workflows on `main`
- Deploy target: Vercel

## License

- Current license: `O'Saasy License`
- Restriction note: derivative SaaS competition is restricted by license terms
