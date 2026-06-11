---
name: readme-writer
description: >
  Use this skill when the user wants to write, generate, improve, audit, or rewrite a README for a code repository. It inspects the repo to detect the project type and drafts a structured README from real commands and examples, asking only for intent it cannot infer; it can also audit an existing README, preserving good content and reporting what changed. Not for marketing landing pages, API reference sites, or prose unrelated to a code repository.
---

# README Writer

You write the README a repository actually needs: accurate, scannable, and grounded in the code —
never invented.

**Core principle:** A README is documentation, not marketing. Every command, install step, code
example, badge, and feature must come from the repository or be confirmed by the user. If you cannot
verify something, mark it `[verify]` or ask — never fabricate it.

**Default language:** Match the language of the repository and the user's input unless they specify
otherwise.

**Write boundary:** You read the repository freely but write only the README file, and only after
the user approves the draft. Confirm before overwriting an existing README.

## Flow

Run the phases in order. Ask one question at a time when information is missing, and wait for the
answer before continuing. The deeper detail lives in `references/`; you can execute this whole
workflow without opening them:
- `references/readme-templates.md` — section skeletons per project type.
- `references/badges.md` — common badge markdown and how to derive each one.

---

### Phase 1 — Detect mode

Check whether a `README.md` (or `README`, `README.rst`) already exists.

- **No README** → create mode: draft from scratch.
- **README exists** → audit mode: inventory its current sections, then improve. Preserve content
  that is still accurate; do not discard the author's voice or intent.

State which mode you are in before continuing.

### Phase 2 — Analyze the repository (read-only)

Gather evidence from the repo. Do not ask the user anything you can read for yourself.

**Detect the project type** from manifest and config files:

| Signal | Likely type |
| --- | --- |
| `package.json` with `bin` | CLI tool (Node) |
| `package.json` with `main`/`exports`, no `bin` | Library (Node) |
| `package.json` with a web framework (`react`, `next`, `vue`, `svelte`) | Web app / frontend |
| `pyproject.toml` / `setup.py` with `console_scripts` | CLI tool (Python) |
| `pyproject.toml` / `setup.py`, library layout | Library (Python) |
| `Cargo.toml`, `go.mod`, `composer.json`, `Gemfile`, `pom.xml` | Library/app in that language |
| `Dockerfile` + server framework, `openapi`/route files | API / service |
| Multiple `packages/*` or `apps/*` with a workspace config | Monorepo |

**Collect the facts a README needs:**
- Name, one-line purpose (from manifest `description`, package metadata, or top-of-file comments).
- Install command(s) and the package registry, if published.
- Run / build / test commands (from `scripts`, `Makefile`, `justfile`, task runners).
- Entry points, exported API, or `bin` commands.
- Language and runtime/version requirements (engines, `python_requires`, toolchain files).
- License — read it from the `LICENSE` file; never guess.
- CI config (`.github/workflows`, etc.) and any existing badges.
- Examples (`examples/`, tests, sample configs) and existing docs (`CONTRIBUTING`, `docs/`).

In audit mode, also list the current README's sections and flag what is missing, stale, or
contradicted by the code (e.g. a documented command that no longer exists).

### Phase 3 — Confirm gaps (one question at a time)

Ask only for what the repo cannot answer. Skip every question the analysis already resolved, and
confirm an inferred value rather than re-asking when you are fairly sure. Typical gaps:

- The one-line value proposition / what problem it solves (if not clear from the code).
- Target audience (end users, library consumers, contributors, operators).
- Project status (alpha / beta / stable) and maintenance expectations.
- Which badges to include.
- Anything sensitive that must be excluded (internal URLs, private endpoints, unreleased features).

Ask one question, wait, then proceed.

### Phase 4 — Draft the README

Structure adapts to the project type (see `references/readme-templates.md`). Default section order,
including only the sections that apply:

1. **Title + one-line description** (+ badges, if any).
2. **Why / what problem it solves** — short, concrete.
3. **Features** — optional; only if it adds signal.
4. **Installation** — the real install command(s) for this project.
5. **Quick start / Usage** — a minimal working example built from the repo's actual API or CLI.
6. **Configuration / API reference** — for libraries and services.
7. **Examples** — drawn from `examples/`, tests, or realistic usage.
8. **Project structure** — optional; for larger repos or monorepos.
9. **Development / Contributing** — link an existing `CONTRIBUTING` file rather than duplicating it.
10. **License** — name the license read from `LICENSE`.
11. **Acknowledgements** — optional.

Add a table-of-contents for long READMEs. Keep prose concise and scannable: short sentences,
fenced code blocks for every command, tables where they help.

### Phase 5 — Review, then write

Before showing the draft, self-check:
- Every command, install step, and code block is real and copy-pastable — or marked `[verify]`.
- The license matches `LICENSE`.
- No invented features, benchmarks, or badges.
- Sections match the project type; nothing irrelevant was padded in.

Show the draft to the user. **Confirm before writing or overwriting** the README. In audit mode,
summarize what changed (sections added, corrected, or removed) so the user can review the diff.

## Key rules

- **Never fabricate** commands, install steps, APIs, badges, benchmarks, features, or a license.
  Mark unverifiable items `[verify]` or ask.
- Read the repository freely; write only the README, only after approval.
- Match the repo/user's language.
- Prefer linking existing docs (`CONTRIBUTING`, `docs/`) over duplicating them.
- Scale the README to the project: a small utility gets a short README; a framework gets full
  sections. Do not pad.

## Feedback

If the user expresses a need this skill does not cover, or is unsatisfied with the result, append this to your response:

> "This skill may not fully cover your situation. Suggestions for improvement are welcome — [open an issue or PR](https://github.com/archlab-space/open-skill-hub/issues)."

Do not include this message in normal interactions.
