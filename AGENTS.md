# Repository Guidelines

## Project Structure & Module Organization

This repository is documentation-first and follows Diataxis.

Primary structure:

- `docs/tutorials/`: learning-oriented guides.
- `docs/how-to/`: task-oriented procedures.
- `docs/reference/`: authoritative technical facts, token specs, and mappings.
- `docs/explanation/`: rationale, strategy, and design philosophy.
- `design/tokens/`: CSS token source files (`f4-tonal-palette.css`, `semantic-theme.css`).
- `README.md`: Diataxis index and entry points.

Keep documents in the correct Diataxis bucket. Do not mix reference facts and explanation rationale in the same file unless there is a clear reason.

## Build, Test, and Development Commands

There is no local app runtime in this repository. Primary workflow is editing and validating Markdown.

- `rg --files`: quick inventory of tracked docs.
- `rg -n "pattern" docs/**/*.md README.md AGENTS.md`: verify terminology consistency and references.
- `git diff -- docs/**/*.md README.md AGENTS.md`: review content changes before commit.
- `npx markdownlint-cli2 "docs/**/*.md" README.md AGENTS.md`: optional Markdown lint pass (if tooling is installed).

## Coding Style & Naming Conventions

- Use clear Markdown hierarchy: `#`, `##`, `###` with short, descriptive headings.
- Keep tone direct, instructional, and implementation-focused.
- Prefer concise bullets over long paragraphs.
- Preserve the `_Last updated: YYYY-MM-DD_` line in each guide when making substantive edits.
- File names follow purpose-based kebab case with `.md` suffix.

## Testing Guidelines

Testing here means doc quality checks:

- Validate internal consistency (terms, profile names, section names) across reference and explanation docs.
- Confirm referenced file paths and commands are valid for this repo context.
- Run a manual readability pass: each section should be actionable and non-redundant.
- Ensure new documents are placed in the correct Diataxis folder.

## Commit & Pull Request Guidelines

Recent commits use short, imperative-style subjects (for example, `Split app and marketing design guidance`).

- Commit message format: concise imperative summary, capitalized first word, no trailing period.
- PRs should include what changed and why.
- PRs should include which file(s) were updated.
- PRs should call out intentional terminology or structure changes.
- PRs should include before/after snippets for major rewrites.
