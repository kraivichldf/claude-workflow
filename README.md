# claude-workflow

My Claude Code setup: a global `CLAUDE.md` with working rules, plus the
skills it relies on.

## What's here

| Path | What it does |
|---|---|
| `CLAUDE.md` | Always-loaded rules: scope, planning, confirmation list, evidence rules, verification. Goes to `~/.claude/CLAUDE.md`. |
| `skills/project-orient` | Orient in a project before changing code: graphify freshness, query/path/explain, which docs to read, what to trust when sources disagree. |
| `skills/update-docs` | Update notes, ADRs or an Obsidian vault after a durable change, and refresh the graph. |
| `skills/handoff` | Final verification pass and handoff report; rebuild a working summary after context compression. |
| `skills/blender-*` | Ten Blender 5.2 skills (modeling, rigging, animation, baking, export…). Third-party, see below. |

## Install

Windows (PowerShell):

```powershell
git clone https://github.com/kraivichldf/claude-workflow.git
.\claude-workflow\install.ps1
```

The script backs up your existing `~/.claude/CLAUDE.md`, copies this one
in, and copies each skill folder into `~/.claude/skills/`. Start a new
Claude Code session afterwards.

Manual install: copy `CLAUDE.md` to `~/.claude/` and each folder in
`skills/` to `~/.claude/skills/`.

## Other skills this setup uses

These are referenced by `CLAUDE.md` or the skills above but are not
included here. Install them from their own sources:

- **graphify**: [Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify)
  (Apache-2.0). Used by `project-orient` and `update-docs`.
- **explain-diff-html / explain-diff-notion**: offered by `handoff` for
  explaining big diffs.
- **superpowers** plugin (`systematic-debugging`,
  `verification-before-completion`, `requesting-code-review`).
- **desktop-commander** plugin (`obsidian-vault`), used by `update-docs`.

If one is missing, the skills still work; Claude falls back to the
plain instructions.

## Credits

The `blender-*` skills are from **blender-agent-skills** by EL4CTEO,
MIT licensed. See
[`skills/blender-core/LICENSE-blender-agent-skills`](skills/blender-core/LICENSE-blender-agent-skills).
