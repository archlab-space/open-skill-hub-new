# Changelog

## [0.2.0] - 2026-06-11

### Changed
- Tightened the frontmatter description to trigger-only metadata under 500 characters and a single natural-wrapping line (R1); dropped the inline file-list parenthetical.

## [0.1.0] - 2026-06-02
- Initial release of `readme-writer`: a skill that analyzes a code repository and drafts or audits a
  clear, structured README built from real commands and examples rather than invented content.
- Five-phase workflow (Detect mode → Analyze repo → Confirm gaps → Draft → Review & write) with
  project-type detection (library, CLI, web app, API/service, monorepo) and a write boundary that
  requires user approval before writing or overwriting the README.
- Safety rules against fabricating commands, install steps, APIs, badges, benchmarks, features, or a
  license, with `[verify]` markers for anything unverifiable.
- Reference files: `references/readme-templates.md` (section skeletons per project type) and
  `references/badges.md` (common badge markdown and how to derive each one).
