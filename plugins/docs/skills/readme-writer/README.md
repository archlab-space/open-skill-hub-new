# readme-writer

Analyze a code repository and write the README it actually needs — or audit and improve an existing
one. The skill works from the code itself, so commands, install steps, and examples are real rather
than invented.

## When to use

- You have a repo with no README, or a thin/outdated one, and want a clear, structured document.
- You want an existing README reviewed for gaps, stale commands, or missing sections.
- You want documentation that matches the project type (library, CLI, web app, API, monorepo)
  instead of a generic template.

## What it does

1. Detects whether to **create** a new README or **audit** an existing one.
2. Inspects the repo read-only — manifest files, scripts, entry points, license, CI, and existing
   docs — to detect the project type and gather the facts a README needs.
3. Asks only for intent it cannot infer (value proposition, audience, status, badges, exclusions),
   one question at a time.
4. Drafts a README with sections scaled to the project type, using repo-derived commands and
   examples.
5. Shows the draft and writes the file **only after you approve it**; in audit mode it summarizes
   what changed.

## Scope and safety

- **Reads** the repository freely; **writes** only the README file, and only after approval. Confirms
  before overwriting an existing README.
- **Never fabricates** commands, install steps, APIs, badges, benchmarks, features, or a license.
  Anything it cannot verify is marked `[verify]` or asked about.
- Matches the language of the repo and your input.

## Files

- `SKILL.md` — the canonical workflow.
- `references/readme-templates.md` — section skeletons per project type.
- `references/badges.md` — common badge markdown and how to derive each one.

The main workflow runs without opening the reference files; they hold expanded templates and
snippets.

## Feedback & Contributions

Found a gap or have a suggestion? [Open an issue or PR](https://github.com/archlab-space/open-skill-hub/issues) — improvements are welcome.
