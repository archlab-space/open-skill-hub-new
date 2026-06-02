# Badges: markdown and how to derive each one

Only add a badge when its source actually exists in the repo. Never invent a build status, coverage
number, version, or download count. If you cannot confirm the value or the source, omit the badge or
mark it `[verify]` and ask the user.

Badges go on one line directly under the title. Keep them few and meaningful — three to five is
usually enough.

## Common badges

Replace `<owner>`, `<repo>`, and `<package>` with real values from the repo's git remote and
manifest.

### CI / build status (GitHub Actions)

Only if a workflow exists under `.github/workflows/`.

```markdown
[![CI](https://github.com/<owner>/<repo>/actions/workflows/<workflow-file>.yml/badge.svg)](https://github.com/<owner>/<repo>/actions/workflows/<workflow-file>.yml)
```

### npm version

Only if the package is published to npm (a `name` in `package.json` that resolves on the registry).

```markdown
[![npm](https://img.shields.io/npm/v/<package>.svg)](https://www.npmjs.com/package/<package>)
```

### PyPI version

Only if published to PyPI.

```markdown
[![PyPI](https://img.shields.io/pypi/v/<package>.svg)](https://pypi.org/project/<package>/)
```

### Crates.io version (Rust)

```markdown
[![crates.io](https://img.shields.io/crates/v/<package>.svg)](https://crates.io/crates/<package>)
```

### License

Derive the license name from the `LICENSE` file or manifest `license` field.

```markdown
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
```

### Coverage

Only if a coverage service (Codecov, Coveralls) is already configured in the repo.

```markdown
[![codecov](https://codecov.io/gh/<owner>/<repo>/branch/main/graph/badge.svg)](https://codecov.io/gh/<owner>/<repo>)
```

## Deriving values

- `<owner>/<repo>` — from `git remote get-url origin`.
- `<package>` — from the manifest (`package.json` `name`, `pyproject.toml` `project.name`, etc.).
- License — from the `LICENSE` file; match the badge label to the actual license.
- Workflow file — the filename under `.github/workflows/`.

If a badge's underlying service is not set up (no CI workflow, not published, no coverage service),
do not add the badge. A missing badge is better than a broken or fabricated one.
