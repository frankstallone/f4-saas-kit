# Starter Strategy

_Last updated: 2026-02-08_

## Why This Starter Exists

The goal is a reusable SaaS foundation that can support both:

- Authenticated product applications
- Public marketing sites

without cloning private repositories for every new project.

## Reusable Patterns to Keep

- App Router + Server Actions for core CRUD workflows
- SQL-first migrations committed to git
- Typed data access modules separated from UI components
- Auth session wrappers and centralized access-control logic
- Storage provider abstraction to avoid cloud lock-in
- Environment validation at startup
- CI and release automation from day one

## Product Variants to Support

- Private SaaS app starter
- Public marketing site starter
- Combined monorepo starter (default recommendation)

## Template Direction

- Use one GitHub template repo as core infrastructure.
- Keep business-domain logic isolated in feature modules so products can swap features without replacing infrastructure.
- Provide post-clone bootstrap scripts for app metadata and environment setup.

## Licensing Decisions Needed

Choose explicit defaults for template publishing:

- MIT (adoption-focused)
- Apache-2.0 (patent grant)
- Source-available (if anti-competition restrictions are required)

Also decide whether public marketing code and private product code share one license model.

## Immediate Next Moves

1. Convert this repository into a template-oriented core.
2. Extract F4 domain logic into modular features.
3. Publish a public starter template repo.
4. Offer a marketing-only variant.
5. Finalize license strategy before broader adoption.

## Related Documents

- App design philosophy: `docs/explanation/app-design-philosophy.md`
- Marketing design philosophy: `docs/explanation/marketing-design-philosophy.md`
- Technical profile: `docs/reference/technical-profile.md`
- Token system and mappings: `docs/reference/design-tokens.md`
