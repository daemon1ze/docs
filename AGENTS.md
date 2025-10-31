# Repository Guidelines

## Project Structure & Module Organization
The Mintlify documentation site lives in `docs/`, with navigation defined by `docs/docs.json`. Page content is grouped by topic: narrative guides in `docs/overview/`, GTM assets in `docs/essentials/`, architectural deep dives in `docs/architecture/`, API schemas inside `docs/api-reference/`, and UI copy blocks in `docs/snippets/`. Shared styling is centralized in `docs/styles.css`, and images or brand marks belong in `docs/images/` and `docs/logo/`.

## Build, Test, and Development Commands
- `npm install` – Sync local dependencies (primarily Mintlify components) before editing.
- `mint dev` – Serve the docs locally from `docs/` for live-preview at http://localhost:3000.
- `mint build` – Produce the static export used by production; run before PRs that touch site-wide components.

## Coding Style & Naming Conventions
Every MDX page begins with front matter (`title`, `description`) followed by concise H2/H3 headings. Mirror the existing hyphenated filenames (e.g., `how-it-works.mdx`) and keep nested HTML/JSX indented two spaces. Prefer Mintlify callouts (`:::note`) and the custom `usb-` utility classes defined in `styles.css` over ad hoc inline styling. Reference assets with relative paths and use fenced code blocks with explicit language tags for examples.

## Testing Guidelines
Preview changes with `mint dev`, click through the sidebar routes, and watch the terminal for build warnings. Run `mint build` to confirm the static compilation succeeds; it catches missing imports, malformed front matter, and broken component references. Document any known gaps (e.g., placeholder copy) directly in the PR so reviewers know what is intentional.

## Commit & Pull Request Guidelines
Commit subjects should be imperative and scoped (`docs: clarify collateral flow`). Group related file edits in one commit to simplify rollback. PRs must summarize the reader impact, list any new routes added to `docs/docs.json`, and include before/after screenshots or GIFs when visual components change. State which commands you ran (`mint dev`, `mint build`) and link related Linear/GitHub issues where applicable.

## Assets & Styling
Favor SVGs for icons in `docs/images/` and optimize PNG/JPEG exports below 500 KB to keep build times quick. Extend `styles.css` by appending new `.usb-*` utilities instead of overriding Mintlify defaults inline, and document any global CSS additions in the PR description so downstream agents can trace styling decisions.
