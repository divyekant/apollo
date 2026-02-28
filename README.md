# Apollo

Agent-agnostic project lifecycle manager. Encodes your development preferences into a universal YAML config and enforces them by injecting rules into agent instruction files.

## Install

```bash
# Claude Code
ln -s <path-to-apollo>/skills/apollo ~/.claude/skills/apollo

# First run — Apollo walks you through setup
/apollo config
```

## Commands

| Command | Purpose |
|---------|---------|
| `/apollo config` | Set up or edit your global preferences (conversational) |
| `/apollo init` | Create a new project from a template (conversational) |
| `/apollo check` | Health check — validates repo state, surfaces gaps |
| `/apollo` | Context-aware "what should I do next?" |
| `/apollo release` | Guided release — bump, changelog, tag, publish |
| "add to Apollo: ..." | Update config mid-session via natural language |

## Config

Apollo uses three-tier config resolution:

1. `~/.apollo/defaults.yaml` — your global preferences
2. `~/.apollo/templates/<name>.yaml` — project type templates
3. `.apollo.yaml` (in project root) — per-project overrides

See [`config/defaults.example.yaml`](config/defaults.example.yaml) for the full schema.

## Templates

Three built-in templates:

- **oss** — open source: full docs, changelog, license, contributing guide
- **personal** — side projects: lighter docs, no review gate, flexible
- **work** — corporate: strict discipline, thorough comments, review-gated

Create custom templates by adding YAML files to `~/.apollo/templates/`.

## Agent Support

Apollo's config format is agent-agnostic. The YAML files at `~/.apollo/` can be read by any agent.

Rule enforcement works by injecting a managed section into the agent's instruction file:

| Agent | Instruction file |
|-------|-----------------|
| Claude Code | `CLAUDE.md` |
| Cursor | `.cursorrules` |
| Codex | `CODEX.md` |
| Windsurf | `.windsurfrules` |

Currently ships with a Claude Code skill adapter. Other adapters can be built using the same config format.

## License

MIT
