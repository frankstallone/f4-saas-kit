# Repository Guidelines

## Project Structure & Module Organization

This repository is documentation-first. Current top-level files:

- `saas-starter-kit.md`: technical baseline and architecture decisions for the starter.
- `ai-app-design-guidance.md`: design rules for authenticated product UI.
- `ai-marketing-design-guidance.md`: design rules for public marketing pages.

Keep related guidance in these files instead of duplicating content. If a section spans app and marketing concerns, split it across the two guidance docs and cross-reference.

## Build, Test, and Development Commands

There is no local app runtime in this repository. Primary workflow is editing and validating Markdown.

- `rg --files`: quick inventory of tracked docs.
- `rg -n "pattern" *.md`: verify terminology consistency and references.
- `git diff -- *.md`: review content changes before commit.
- `npx markdownlint-cli2 "*.md"`: optional Markdown lint pass (if tooling is installed).

## Coding Style & Naming Conventions

- Use clear Markdown hierarchy: `#`, `##`, `###` with short, descriptive headings.
- Keep tone direct, instructional, and implementation-focused.
- Prefer concise bullets over long paragraphs.
- Preserve the `_Last updated: YYYY-MM-DD_` line in each guide when making substantive edits.
- File names follow purpose-based kebab case with `.md` suffix (for example, `ai-app-design-guidance.md`).

## Testing Guidelines

Testing here means doc quality checks:

- Validate internal consistency (terms, profile names, section names) across all three guides.
- Confirm referenced file paths and commands are valid for this repo context.
- Run a manual readability pass: each section should be actionable and non-redundant.

## Commit & Pull Request Guidelines

Recent commits use short, imperative-style subjects (for example, `Split app and marketing design guidance`).

- Commit message format: concise imperative summary, capitalized first word, no trailing period.
- PRs should include what changed and why.
- PRs should include which file(s) were updated.
- PRs should call out intentional terminology or structure changes.
- PRs should include before/after snippets for major rewrites.
