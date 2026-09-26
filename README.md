# Powerups Marketplace

Practical workflow skills and tools for Claude Code.

## Installation

Add this marketplace to Claude Code:

```
/plugin marketplace add njt/powerups-marketplace
```

## Available Plugins

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
- `journal` skill — structured session journal written to Obsidian when a session ends
- `reflect` skill — synthesize journals into thread documents and weekly digests
- SessionEnd hook — hands off to a background worker so journaling survives Claude Code cancelling the hook
- Weekly cron jobs — catch-up for missed sessions (Sunday 3am) and the digest (Sunday 5am)

**Prerequisites:** `jq`, `python3`, `cron`, an Obsidian vault (or any markdown folder). macOS and Linux only.

**Repository:** https://github.com/njt/powerups-vaultbot3000

---

### Rate My CLI

**Description:** Assess and remediate a CLI codebase against agent-native CLI principles — 48 static pass/fail checks across 10 principles, with a read-only assessment and a conformance-fix loop.

**Install:**
```
/plugin install powerups-rate-my-cli@powerups-marketplace
```

**What you get:**
- `rate-my-cli` skill — statically score a CLI on how well it serves AI agents (inspired by Trevin Chow's *10 Principles for Agent-Native CLIs*)
- `assess` mode — read-only, static; fans out one evaluator per principle into a `SCORECARD.md` with `file:line` evidence and a prioritized remediation plan
- `remediate` mode — conformance-fix loop: auto-fixes localized `conformance` gaps (Blockers first), verifies with read-only commands, and only *proposes* whole-subsystem `feature` gaps
- `validate` mode (opt-in) — runs the remediated CLI live to catch bugs static analysis misses; mutations run only against an explicit throwaway sandbox

**Safety:** Assessment never runs the target CLI; remediation edits source and verifies with provably read-only commands only.

**Repository:** https://github.com/njt/powerups-rate-my-cli

---

### Wiki Ingest

**Description:** Fetch a URL (or GitHub repo), analyze it with an LLM, and file it as cross-linked pages in an Obsidian wiki.

**Install:**
```
/plugin install powerups-wiki-ingest@powerups-marketplace
```

**What you get:**
- `/wiki-ingest` command — ingest one or many URLs in parallel: web pages, deep GitHub-repo analysis, and YouTube videos (transcript via `ytx`)
- Three tiers per source — `raw/` (verbatim), `summary/` (précis tagged with one or two topics from a fixed `topics.md`), `note/` (the analysis page)
- Compiled topic pages — `wiki-compile` and `wiki-recompile` rebuild each `topic/` page from every summary tagged with it; `wiki-curate` runs deterministic health checks with no LLM
- `wiki-ingest-setup` — one-command bootstrap of a new wiki; `wiki-migrate-topics` upgrades a 2.x wiki
- Deterministic duplicate detection, merge-retry, best-effort push, optional `surf` browser fallback for JS-heavy pages

**Configuration:** `WIKI_PATH` (required — your wiki directory); `WIKI_INGEST_CLI` (optional — the nested LLM CLI, `claude` by default or `pi`). See the plugin README for the single-call mode and model variables.

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
