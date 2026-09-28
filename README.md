# dkify-plugins

The public marketplace for [dkify](https://github.com/data-kinetic/dkify) plugins and harnesses.

- **Plugins** wrap an external system (its API, MCP server or CLI and its credentials).
- **Harnesses** are agent tooling for a line of work: skills, a CLI, gates and rules. A harness lists the plugins it needs.

This repository is intentionally empty. Data Kinetic's plugins and harnesses are private for now; this source exists so the public path is real when the first entry is published.

## Layout

```
marketplace.yaml        # index: visibility, entries[] {name, kind, path, version, requires.dkify}
plugins/<name>/         # plugin.yaml, skills/, CLI or MCP server, config *.example.yaml
harnesses/<name>/       # harness.yaml, skills/, RULES.md, CLI with --describe --json
```

Each entry is released on its own immutable tag, `<name>--v<semver>`.

## Rules for entries

- No customer names, customer data or dependencies on a private source.
- A published tag never moves.
- `dkify marketplace validate` must pass in CI (arrives with dkify 3.2).
