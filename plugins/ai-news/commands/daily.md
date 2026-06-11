---
description: Compile a dated daily digest of the most significant AI and tech news from the last 24-48 hours.
argument-hint: [topic or focus area (optional)]
allowed-tools: WebSearch, WebFetch
---

You are producing the **AI Daily** digest. Follow the ai-news newsroom-style sourcing standards.

## Step 0 — Anchor on the real date
First determine the actual current date (do not assume). Compute "recent" as the trailing ~24-48 hours relative to that date. The digest headline must carry that real date.

## Step 1 — Gather (WebSearch)
Run SEVERAL distinct WebSearch queries to span the major beats. Use the real current date in queries. Suggested queries (adapt wording, run a spread of them):
- `AI model release [current month year]`
- `AI research paper breakthrough this week`
- `AI funding round / acquisition [current month year]`
- `AI regulation policy EU US [current month year]`
- `new AI product launch [current month year]`
- `OpenAI OR Anthropic OR Google DeepMind OR Meta AI news today`
- `AI chips / compute / Nvidia news [current month year]`

If `$ARGUMENTS` is provided, FOCUS the digest on that topic: bias every query toward `$ARGUMENTS` (e.g. `$ARGUMENTS AI news [current month year]`) and only include off-topic items if they are unavoidably major.

## Step 2 — Triage
Dedupe overlapping stories (same event from multiple outlets = one item, cite the strongest source). Rank candidates by significance: scale of impact, novelty, credibility of outlet, and recency. Keep the top 5-8.

## Step 3 — Confirm (WebFetch)
WebFetch the top items to confirm the specific claims, the outlet name, and the publication date. Do not summarize from the search snippet alone for headline items — open the page.

## Step 4 — Write the digest
Output in this exact shape:

**AI Daily — [real current date]**

_TL;DR:_ one sentence capturing the single biggest development of the day.

Then 5-8 items, each:

**Headline (what happened, active voice)**
2-3 sentence summary: lead with the news, then the context/why it matters.
_Source: Outlet, publication date, URL_

End with:

**What to watch:** one line on the most important thing to track next.

## Sourcing rules (non-negotiable)
Never invent quotes, statistics, dates, outlet names, or URLs. Every item must trace to a source you actually fetched this session. If you could not fetch or verify an item, drop it or flag it explicitly — do not guess. Prefer primary sources and reputable outlets; always note the outlet and publication date.
