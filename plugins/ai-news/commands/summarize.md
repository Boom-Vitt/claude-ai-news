---
description: Summarize a specific article URL (or find and summarize the best article on a topic) into a structured brief.
argument-hint: <url or topic>
allowed-tools: WebSearch, WebFetch
---

You are producing a structured news brief from a single source. Follow the ai-news newsroom-style sourcing standards.

## Step 1 — Resolve the source
Look at `$ARGUMENTS`:
- **If it is a URL:** WebFetch it directly. That fetched page is your only source for facts.
- **If it is a topic (not a URL):** run a WebSearch to find the single most relevant, most recent, most authoritative article on `$ARGUMENTS`, then WebFetch that article. State which article you chose and why before the brief.

If the page cannot be fetched, say so plainly and stop — do not summarize from memory or from a search snippet.

## Step 2 — Write the brief
Output in this exact shape:

**Headline:** the article's actual headline (or a faithful one-line restatement if none is present).

**Nut graf:** one sentence capturing the core of the story.

**Key points:**
- 3-5 bullets, each a distinct factual takeaway drawn from the source.

**Figures & quotes:** include ONLY if present in the source. Quote text verbatim and attribute it ("Name, title, said..."). Reproduce statistics exactly as written. If the source has none, write "None stated in source." Do not manufacture any.

**Why it matters:** two sentences of significance — grounded in the article, not your own speculation.

**Source:** Outlet, publication date, URL.

## Step 3 — Flag the gaps
Add a short **Not established by this source:** line noting anything a reader might assume but the article does NOT actually claim (e.g. pricing, availability, causation, independent verification).

## Sourcing rules (non-negotiable)
Never invent quotes, statistics, dates, outlet names, or URLs, and never embellish beyond what the source states. Every line of the brief must trace to the fetched page. If a fact is implied but not stated, treat it as not established.
