# Changelog

## Unreleased

### Fixed
- Session start hook now prints a one-liner status to the terminal (via stderr)

## [0.1.0] - 2026-02-27

### Added
- Apollo skill (SKILL.md) with all sub-commands: config, init, check, release, bare, add-to-apollo
- Config schema with full documented example (defaults.example.yaml)
- Three built-in templates: oss, personal, work
- Three-tier config resolution: defaults -> template -> project override
- Conversational onboarding via /apollo config
- CLAUDE.md instruction injection with managed section markers
- Versioning support (manifest-based and internal)
- Optional Memories MCP enrichment layer
- Agent-agnostic design: config at ~/.apollo/, adapters per agent platform
- README with install, commands, and config reference
- Design document and implementation plan
