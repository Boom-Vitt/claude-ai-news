---
description: Research and draft a publishable, inverted-pyramid news article about an AI topic with real attributed sourcing.
argument-hint: <topic or angle>
allowed-tools: WebSearch, WebFetch, Write
---

You are drafting a publishable news article on `$ARGUMENTS`. Follow the ai-news newsroom-style sourcing standards.

## Step 1 — Report it out first (do NOT write yet)
Determine the real current date, then research `$ARGUMENTS`:
- Run WebSearch to find the primary development and reactions. Suggested queries: `$ARGUMENTS [current month year]`, `$ARGUMENTS announcement OR release`, `$ARGUMENTS reaction OR analysis`, plus the primary actor's own page/blog.
- WebFetch **2-4 real sources** — prioritize the primary source (company post, paper, filing, official statement) plus independent coverage. Capture the exact outlet, date, URL, and any verbatim quotes you may use.

Do not begin writing until you have at least two fetched sources you can attribute.

## Step 2 — Write the article (inverted pyramid)
Structure, in descending order of importance:

**Headline** — specific, active, accurate. No hype.

**Lead paragraph** — who, what, when, where, and the why/significance, in 1-2 tight sentences.

**Body paragraphs** — supporting detail in descending importance: the key facts, then context, then reactions/quotes, then background. Attribute every claim ("according to [Outlet]", "the company said in a blog post"). Use real quotes verbatim with attribution.

**Sources** — a list at the end of every URL you fetched, with outlet and date.

## Step 3 — Offer to save
After presenting the draft, offer to save it to a file with the Write tool (e.g. a slugged `.md`) if the user wants.

## Hard rules (non-negotiable)
- Only state facts grounded in the sources you fetched this session.
- Quotes must be verbatim from a source and attributed — **never fabricate or paraphrase-into-quotes**.
- Never invent statistics, dates, outlet names, or URLs.
- Where the story needs a fact you could not source, write `[NEEDS VERIFICATION]` inline rather than filling it in. Do not paper over a gap.
- Keep the voice wire-service: lead with what happened, stay concise, skip editorializing.
