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
/plugin install claude-session-reflection@powerups-marketplace
```

**What you get:**
- `session-reflection` skill — structured retrospective analysis
- `/reflect` command — run a reflection at end of session
- Auto-detects project session data from working directory

**Repository:** https://github.com/njt/claude-session-reflection

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
