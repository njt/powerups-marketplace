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

### Code Investigation

**Description:** Evidence-based codebase investigation with mandatory citations — prevents guesses and assumptions.

**Install:**
```
/plugin install powerups-code-investigation@powerups-marketplace
```

**What you get:**
- `code-investigation` skill — 6-phase investigation protocol
- Mandatory `file:line` citations for every claim
- Red flags that stop Claude from guessing
- Database-specific investigation rules
- Structured findings output format

**Repository:** https://github.com/njt/powerups-code-investigation

---

### VaultBot 3000

**Description:** Automated journaling and reflection for Claude Code sessions — writes structured records into an Obsidian vault with thread tracking and weekly digests.

**Install:**
```
/plugin install powerups-vaultbot3000@powerups-marketplace
```

**What you get:**
- `journal` skill — structured session journal written to Obsidian on session end
- `reflect` skill — synthesize journals into thread documents and weekly digests
- SessionEnd hook — automatic journaling when sessions close
- Weekly digest cron job (Sunday 5am)

**Prerequisites:** `notesmd` CLI, `jq`, Obsidian vault with `Agent Journals` folder

**Repository:** https://github.com/njt/powerups-vaultbot3000

---

### Wiki Ingest

**Description:** Feed it a URL or GitHub repo; it fetches the source, analyzes it with an LLM, and files a cross-linked page into your Obsidian wiki — updating an index and an append-only log. Each ingest runs in an isolated git worktree, so many URLs process in parallel safely.

**Install:**
```
/plugin install powerups-wiki-ingest@powerups-marketplace
```

**What you get:**
- `/wiki-ingest` command — ingest one or many URLs (regular pages or deep GitHub-repo analysis)
- `wiki-ingest-setup` — one-command bootstrap of a new wiki
- Deterministic duplicate detection, merge-retry, best-effort push, optional `surf` browser fallback

**Configuration:** `WIKI_PATH` (required — your wiki directory); `WIKI_INGEST_CLI` (optional — the LLM CLI, default `claude`)

**Repository:** https://github.com/njt/powerups-wiki-ingest

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
