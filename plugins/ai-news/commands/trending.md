---
description: Surface what is trending in AI right now and explain why, clustered into themes with momentum reads.
argument-hint: [niche (optional)]
allowed-tools: WebSearch, WebFetch
---

You are producing the **AI Trending** report — not a list of single stories, but the themes that are surging right now and the reason behind each. Follow the ai-news newsroom-style sourcing standards.

## Step 0 — Anchor on the real date
Determine the actual current date first. "Trending now" means activity in roughly the last few days to a week relative to that real date.

## Step 1 — Cast a wide net (WebSearch)
Run multiple WebSearch queries across BOTH news and discussion surfaces so you catch momentum, not just press releases. Suggested queries (adapt; use the real current date):
- `trending AI topics this week [current month year]`
- `AI Twitter / X discussion trending [current month year]`
- `Hacker News AI top discussion [current month year]`
- `Reddit r/MachineLearning OR r/LocalLLaMA hot [current month year]`
- `most discussed AI release OR controversy [current month year]`
- `AI [current month year] backlash OR debate`

If `$ARGUMENTS` is given, scope to that niche (e.g. `$ARGUMENTS AI trending [current month year]`, plus the relevant community for that niche).

## Step 2 — Cluster into themes
Group related stories into 5-7 THEMES (e.g. "open-weight model price war", "agentic coding tools", "EU AI Act enforcement"). A theme bundles multiple stories around one underlying current — do not report the same theme twice under different headlines.

## Step 3 — Corroborate (WebFetch)
For each theme, WebFetch 1-2 sources that confirm it is real and current. A theme with no fetchable corroboration does not make the list.

## Step 4 — Write the report
Output in this shape:

**AI Trending — [real current date]**

For each of the 5-7 themes:

**Theme name**
- **The trend:** what is moving (1-2 sentences).
- **Why now:** the specific trigger making it surge this week.
- **Sources:** 1-2 fetched links — _Outlet, date, URL_.
- **Momentum:** Rising / Peaking / Fading, with a half-line of justification.

## Sourcing rules (non-negotiable)
Never invent quotes, statistics, dates, outlet names, or URLs. Every theme and its "why now" must trace to sources you actually fetched this session. Distinguish genuine momentum from a single loud post; if a theme is only one source thin, say so or drop it. Note outlet and date for each link.
