# Changelog

All notable changes to this project will be documented in this file.
Format: [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) · [Semantic Versioning](https://semver.org/)

## v0.2.0 — 2026-03-19

### Added
- `.gitignore` for Node.js projects

### Changed
- SKILL.md parser now delegates to `@effectorhq/core/skill` — eliminates the in-repo duplicate parser
- Package stays `@effectorhq/skill-lint`

---

## v0.1.0 — 2026-03-05

Initial release.

### Added
- **CLI** — `npx @effectorhq/skill-lint <path>` validates one or more SKILL.md files
- **Parser** — splits YAML frontmatter from markdown body; catches malformed delimiters
- **Rules** (16 total across error / warning / info):
  - `missing-name` / `missing-description` — required field errors
  - `name-format` — enforces kebab-case
  - `description-too-short` / `description-too-long` — discovery quality
  - `missing-openclaw-metadata` — warns when `metadata.openclaw` block is absent
  - `missing-emoji` — warns when emoji is missing
  - `install-*` — validates install entry structure
  - `requires-*` — validates bins/env array types
  - `env-not-uppercase` — warns on lowercase env var names
  - `missing-setup` / `missing-examples` — body structure checks
- **Flags** — `--fail-on-warnings`, `--json`, `--quiet`, `--version`
- **Exit codes** — `0` clean, `1` errors (or warnings with `--fail-on-warnings`)
- Zero dependencies — Node.js 20 built-ins only
- 21 passing tests
