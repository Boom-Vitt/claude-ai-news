# AI News — a Claude Code plugin

[![Claude Code Plugin](https://img.shields.io/badge/Claude%20Code-plugin-da7756)](https://code.claude.com/docs/en/plugins)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)
[![Version](https://img.shields.io/badge/version-0.1.0-informational)](./plugins/ai-news/CHANGELOG.md)

Research, curate, summarize, and write **AI & tech news** inside Claude Code — with one rule above all others: **every claim is tied to a real source fetched this session. No invented quotes, numbers, dates, outlets, or URLs.**

This repository is a single-plugin [Claude Code marketplace](https://code.claude.com/docs/en/plugin-marketplaces). The plugin lives in [`plugins/ai-news`](./plugins/ai-news).

---

## What it does

| Command | What it does |
| :--- | :--- |
| `/ai-news:daily [topic]` | A dated digest of the most significant AI/tech stories from the last 24–48h, each item sourced. |
| `/ai-news:trending [niche]` | Surfaces 5–7 trending themes (not just single stories), with a momentum read and corroboration. |
| `/ai-news:summarize <url\|topic>` | Turns an article (or the best article on a topic) into a structured, source-faithful brief. |
| `/ai-news:write <topic>` | Researches, then drafts a publishable inverted-pyramid news article with attributed sourcing. |

Two subagents do the heavy lifting and can be invoked automatically:

- **`news-researcher`** — gathers and verifies facts across diverse sources, returns a tiered (confirmed / single-sourced / contested) research brief. It researches; it doesn't write prose.
- **`news-editor`** — fact-checks and copy-edits a draft against its sources, returns an edit report plus a corrected version. It never invents facts to fill gaps.

Both, and every command, follow the bundled **`newsroom-style`** skill: wire-service sourcing standards, inverted-pyramid structure, neutral voice, AI-domain precision, and the anti-fabrication guardrails.

> The plugin uses Claude Code's built-in **WebSearch** and **WebFetch** to gather news. It does not require any API keys or external MCP servers.

---

## Install

```bash
# 1. Add this marketplace
/plugin marketplace add Boom-Vitt/claude-ai-news

# 2. Install the plugin
/plugin install ai-news@claude-ai-news
```

Then run any command, e.g. `/ai-news:daily` or `/ai-news:write the latest open-weight model release`.

To try it locally without installing from GitHub:

```bash
claude --plugin-dir /path/to/claude-ai-news/plugins/ai-news
```

---

## The anti-fabrication contract

A news tool that hallucinates a source is worse than useless. Every component here is built around one cardinal rule, drawn from the [`newsroom-style`](./plugins/ai-news/skills/newsroom-style/SKILL.md) skill:

- **Never** invent a quote, statistic, date, study result, outlet name, person, or URL.
- Every factual claim must trace to a source actually fetched this session.
- Quotes are verbatim from a real source, with attribution. Paraphrase is marked as paraphrase.
- When something can't be verified, it's flagged `[NEEDS VERIFICATION]` or omitted — never filled in with a plausible guess.
- Outputs end with a **Sources** list of the real URLs that were fetched.

---

## Repository structure

This follows the [standard Claude Code plugin layout](https://code.claude.com/docs/en/plugins-reference) — only `plugin.json` lives in `.claude-plugin/`; every component directory sits at the plugin root.

```text
claude-ai-news/
├── .claude-plugin/
│   └── marketplace.json          # marketplace catalog (name, owner, plugins[])
├── plugins/
│   └── ai-news/
│       ├── .claude-plugin/
│       │   └── plugin.json        # plugin manifest (name, version, metadata)
│       ├── commands/              # slash commands (flat .md)
│       │   ├── daily.md
│       │   ├── trending.md
│       │   ├── summarize.md
│       │   └── write.md
│       ├── agents/                # subagents
│       │   ├── news-researcher.md
│       │   └── news-editor.md
│       ├── skills/                # reusable skills
│       │   └── newsroom-style/
│       │       └── SKILL.md
│       ├── CHANGELOG.md
│       └── LICENSE
├── LICENSE
└── README.md
```

---

## Development

```bash
# Validate the manifest and all component frontmatter
claude plugin validate ./plugins/ai-news --strict

# Inspect the component inventory and token cost
claude plugin details ai-news@claude-ai-news
```

Contributions welcome — bump the version in both `plugin.json` and the marketplace entry, and add a `CHANGELOG.md` note, when you ship changes.

---

## License

[MIT](./LICENSE) © Boom-Vitt
