# Changelog

All notable changes to this template are documented here. The format is based on
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added

- `tools/validate_template.py`: standard-library structural validator for the
  core files, internal Markdown links and anchors, fenced blocks, tables, spaced
  paths, and the uninitialized checkpoint/report state. Makes a "PASS - N
  structural checks" result reproducible from the repository.
- `.github/workflows/validate.yml`: CI that runs the validator on pushes to
  `main` and on pull requests.
- `.gitignore`: keep local credentials, private inputs, and working data out of
  version control (the template previously had none despite handling private data
  and running analysis code).
- `LICENSE`: MIT license (update the copyright holder before reuse).
- `CLAUDE.md` and `.claude/commands/setup.md` + `.claude/commands/loop.md`: a thin
  Claude Code adapter and slash commands that wrap the canonical README prompts.
- `CHANGELOG.md`: this file.
- README note pointing to the maintainer tooling above.

### Changed

- Renamed `prompt record.txt` → `prompt-record.txt` for portability (no spaces in
  tracked paths).
