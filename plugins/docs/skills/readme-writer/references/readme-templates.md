# README section templates by project type

Use these as skeletons, not fill-in-the-blank forms. Include only sections that apply, and populate
every command and example from the actual repository. Scale length to the project.

---

## Library / package

```markdown
# <name>

<one-line description>

[badges]

## Installation

```<sh>
<install command, e.g. npm install <name> / pip install <name>>
```

## Usage

```<lang>
<minimal working example using the real public API>
```

## API

<key exported functions/classes, signatures, and short descriptions>

## Configuration

<options, environment variables, or config files — if any>

## Contributing

See [CONTRIBUTING](CONTRIBUTING.md).

## License

<license name from LICENSE>
```

---

## CLI tool

```markdown
# <name>

<one-line description>

[badges]

## Installation

```<sh>
<install command, including global install if relevant>
```

## Usage

```<sh>
<command> <subcommand> [options]
```

### Commands

| Command | Description |
| --- | --- |
| `<command> <sub>` | <what it does> |

### Options

| Flag | Description |
| --- | --- |
| `--<flag>` | <what it does> |

## Examples

```<sh>
<a realistic invocation and its effect>
```

## License

<license name>
```

---

## Web app / frontend

```markdown
# <name>

<one-line description>

[badges]

## Features

- <feature>

## Getting started

### Prerequisites

<runtime/version requirements>

### Install

```<sh>
<install command>
```

### Run locally

```<sh>
<dev server command>
```

## Configuration

<environment variables / .env keys — names only, never real secrets>

## Build & deploy

```<sh>
<build command>
```

## License

<license name>
```

---

## API / service

```markdown
# <name>

<one-line description>

[badges]

## Overview

<what the service does and who calls it>

## Getting started

### Prerequisites

<runtime, database, external services>

### Run

```<sh>
<run command, e.g. docker compose up / make run>
```

## Configuration

| Variable | Description | Default |
| --- | --- | --- |
| `<ENV_VAR>` | <purpose> | <default> |

## API

<key endpoints or a link to the OpenAPI/reference spec>

## License

<license name>
```

---

## Monorepo

```markdown
# <name>

<one-line description>

[badges]

## Packages

| Package | Description |
| --- | --- |
| [`packages/<a>`](packages/<a>) | <description> |
| [`apps/<b>`](apps/<b>) | <description> |

## Development

```<sh>
<install command at the workspace root>
<build / test commands>
```

## Contributing

See [CONTRIBUTING](CONTRIBUTING.md).

## License

<license name>
```
