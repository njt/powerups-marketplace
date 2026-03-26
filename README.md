# Powerups Marketplace

Practical workflow skills and tools for Claude Code.

## Installation

Add this marketplace to Claude Code:

```
/plugin marketplace add njt/powerups-marketplace
```

## Available Plugins

### Session Reflection

**Description:** Analyze session history for inefficiency patterns and propose actionable improvements.

**Install:**
```
/plugin install powerups-session-reflection@powerups-marketplace
```

**What you get:**
- `session-reflection` skill — structured retrospective analysis
- `/reflect` command — run a reflection at end of session
- Auto-detects project session data from working directory

**Repository:** https://github.com/njt/powerups-session-reflection

---

### Requirements Management

**Description:** Requirements management toolkit: Socratic elicitation, reverse-engineering from code, and maintenance during development.

**Install:**
```
/plugin install powerups-requirements@powerups-marketplace
```

**What you get:**
- `gathering-requirements` skill — Socratic elicitation for new projects
- `reverse-engineering-requirements` skill — extract requirements from existing code
- `requirements-management` skill — keep requirements in sync during development
- `requirements-editor` agent — subagent for structured doc edits
- `req_change_hook` — reminds Claude to check for requirement changes on every message
- Templates for `requirements.md` and `systems.md`

**Repository:** https://github.com/njt/powerups-requirements

---

## Marketplace Structure

```
powerups-marketplace/
├── .claude-plugin/
│   └── marketplace.json       # Plugin catalog
└── README.md
```

## License

Marketplace metadata: MIT License

Individual plugins: See respective plugin licenses.
