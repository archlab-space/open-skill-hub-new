# Open Skill Hub

A portable, global skill library for AI coding agents — organized into domain-specific
plugins you can install into Claude Code.

Each plugin packages reusable **skills**: focused, trigger-driven instructions that teach an
agent how to perform a task accurately (write a README from real code, optimize content for AI
answer engines, turn notes into social posts). Skills are written in plain Markdown and authored
to be portable across agent platforms; the install steps below cover Claude Code.

## What's inside

The hub is split into three plugins. Install only the ones you need.

| Plugin | Install name | Skills |
| --- | --- | --- |
| **docs** | `open-skill-hub-docs` | [`readme-writer`](plugins/docs/skills/readme-writer/README.md) — analyze a repo, detect its type, and draft or audit a README from real commands and examples. |
| **seo** | `open-skill-hub-seo` | [`geo-first-seo`](plugins/seo/skills/geo-first-seo/README.md) — end-to-end Generative Engine Optimization: strategy → create/audit content → markup → score, so a page is more likely to be cited by AI answer engines. |
| **writing** | `open-skill-hub-writing` | [`x-post-strategist`](plugins/writing/skills/x-post-strategist/README.md) — turn ideas, notes, or reports into X posts and threads.<br>[`saas-founder-content-writer`](plugins/writing/skills/saas-founder-content-writer/README.md) — turn product updates and founder lessons into high-signal posts for X, Reddit, and LinkedIn. |

## Installation

In Claude Code, add the marketplace once:

```
/plugin marketplace add archlab-space/open-skill-hub
```

Then install the plugins you want:

```
/plugin install open-skill-hub-docs@open-skill-hub
/plugin install open-skill-hub-seo@open-skill-hub
/plugin install open-skill-hub-writing@open-skill-hub
```

Reload so the new skills are available:

```
/reload-plugins
```

## Usage

Once installed, skills activate automatically when your request matches a skill's trigger, or you
can invoke one explicitly by name:

```
/open-skill-hub-docs:readme-writer
```

Each skill's `README.md` (linked in the table above) describes its scope, workflow, and any
inputs it needs.

## Repository structure

```text
plugins/<domain>/
  README.md            # plugin overview and skill index
  .claude-plugin/      # Claude Code plugin manifest
  .codex-plugin/       # Codex plugin manifest
  skills/<skill-name>/
    README.md           # human-facing overview
    SKILL.md            # canonical skill instructions
    CHANGELOG.md        # per-skill version history
```

See [`CLAUDE.md`](CLAUDE.md) for the full authoring guide — repository workflow, skill structure,
naming, frontmatter, and safety conventions.

## Contributing

Skills live under `plugins/<domain>/skills/<skill-name>/`. Before adding or changing a skill, read
[`CLAUDE.md`](CLAUDE.md): it covers branch workflow, the standard skill layout, version bumping,
and the changelog requirement. Open changes via a pull request — `main` is protected.

## License

MIT, as declared in each plugin's `plugin.json`. _[verify] No root `LICENSE` file currently exists
in the repository — adding one is recommended so the license is unambiguous._

## Feedback & Contributions

Found a gap or have a suggestion? [Open an issue or PR](https://github.com/archlab-space/open-skill-hub/issues) — improvements are welcome.
