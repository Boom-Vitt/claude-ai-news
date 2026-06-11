---
name: newsroom-style
description: Use when writing, editing, summarizing, or fact-checking AI/tech news. Establishes wire-service editorial standards — sourcing, attribution, recency, inverted-pyramid structure, neutral voice, AI-domain precision — and the anti-fabrication guardrails every ai-news command and agent must follow.
---

# Newsroom Style

The shared editorial standard for the ai-news plugin. Every command and agent that writes, edits, summarizes, or fact-checks news MUST follow these rules. When a rule here conflicts with a request to "make it punchier" or "fill in the details," this standard wins.

## 1. Anti-fabrication — the cardinal rule

Never invent. This is non-negotiable and overrides any instinct to produce complete-looking copy.

- **Do not fabricate** quotes, statistics, dates, study results, benchmark numbers, dollar figures, outlet names, author bylines, or URLs.
- **Every factual claim must trace to a real source** fetched in the current session via `WebFetch` or `WebSearch`. If you did not retrieve it this session, you do not know it.
- **If a fact cannot be verified, mark it `[NEEDS VERIFICATION]` or omit it.** Never paper over a gap with a plausible-sounding guess. A missing fact is acceptable; an invented one is a failure.
- **Quotes must be verbatim** from a real fetched source, with attribution (speaker + where it was said/published). If you are restating rather than quoting, write "paraphrasing" or drop the quotation marks — never present a paraphrase inside quote marks.
- **Do not guess at numbers.** "Roughly" and "about" are allowed only when the source itself hedges or when rounding a real figure; they are never license to estimate a number you don't have.
- When unsure whether you're remembering vs. citing: assume you're remembering, and verify before printing.

## 2. Sourcing standards

- **Prefer primary sources**: the company blog post, the research paper/preprint, the official SEC/regulatory filing, the press release, the live-stream — over secondary reporting about them.
- **Corroborate load-bearing facts with ≥2 independent sources.** "Independent" means not republishing the same wire copy or each other. A single primary source is fine for what that party says about itself; a contested or surprising claim needs corroboration.
- **Attribute every item**: outlet/publisher + publication date + URL. No naked claims.
- **Grade certainty explicitly** and keep the grades distinct:
  - *Confirmed* — verifiable in a primary source or by multiple independent outlets.
  - *Reported* — a credible outlet reports it; not independently confirmed here.
  - *Rumored / unconfirmed* — circulating but unverified; label it as such.
- **Treat social posts (X, LinkedIn, Reddit, Discord, forums) as claims, not facts**, until corroborated by a primary source or independent reporting — even posts from official or executive accounts, which can be deleted, edited, or walked back.

## 3. Recency and dating

- **Compute recency against the actual current date** (the real date in this session, not a remembered one). Do the arithmetic.
- **Always state when something happened** — the event date, not just "recently" or "this week."
- **Flag stale info.** If the most recent source is months old, say so; don't imply freshness you can't support.
- **Catch recycled news.** If a "breaking" item is actually a re-surfaced older story, note the original date and that it is not new.
- Distinguish *announced* from *available*: an announcement date is not a ship date.

## 4. Structure — inverted pyramid

- **Lead with the single most newsworthy fact** — the who / what / when / where / why — in the first sentence or two. The reader who stops after the lead should still have the story.
- **Descend by importance.** Each subsequent paragraph is less essential than the one above it, so the piece can be cut from the bottom without losing the core.
- **One idea per paragraph.** Keep paragraphs short.
- **Headline is specific and non-clickbait.** Name the actor and the action ("Anthropic releases X with Y"), not "You won't believe what just happened in AI." No vague teasers, no withheld payoff.
- **Include a nut graf / "why it matters"** — one line establishing significance and context, high in the piece.

## 5. Neutral voice

- **Wire-service tone.** Report; don't sell, cheer, or scold.
- **No hype.** Avoid "revolutionary," "game-changing," "mind-blowing," "stunning," "breakthrough" unless quoting a source — and then attribute the word to them.
- **Attribute opinions and characterizations.** "Critics say," "the company calls it," "according to analysts" — not the narrator's own verdict.
- **Separate fact from analysis.** If you offer interpretation, label it (e.g., an "Analysis" line) so it can't be mistaken for reporting.
- **Avoid loaded adjectives** and editorializing verbs ("slammed," "crushed," "dominates"). State what happened.
- **Hedge to match the evidence.** Use "reportedly," "according to," "appears to" when certainty isn't warranted — and drop the hedges when a fact is confirmed.

## 6. AI-domain specifics

- **Be exact with model names and versions.** "GPT-4o" ≠ "GPT-4" ≠ "GPT-4.1"; "Claude Opus 4.1" ≠ "Claude Opus 4." Match the vendor's exact string, including dates/suffixes.
- **Benchmark numbers must cite the eval and the source.** Name the benchmark (MMLU, SWE-bench Verified, GPQA, ARC-AGI, etc.), the score, the conditions if relevant, and where the number came from. Note when a number is self-reported by the vendor vs. independently reproduced.
- **Get lab/company names and relationships right** (e.g., who owns/funds/partners with whom). Don't conflate a model, the lab that made it, and the product that serves it.
- **Funding and financial figures cite the filing or announcement** — round, valuation, lead investor, date. Distinguish "raised" from "valued at" from "in talks to raise."
- **Distinguish research from product.** A paper, a demo, a waitlist, a limited preview, and general availability are different things. Don't write "you can now use X" off a research announcement.
- **Watch for vendor marketing dressed as news.** Benchmark cherry-picking, "state-of-the-art" claims, and launch-day superlatives are claims by an interested party — attribute them, and seek independent corroboration before stating them as fact.

## 7. Output hygiene

- **End every news output with a Sources list** of the actual URLs fetched this session, each with outlet + date. No URL that wasn't really retrieved.
- **If search or fetch returned nothing, say so explicitly** — "No sources found for X as of [date]" — rather than generating coverage to fill the space.
- **Surface verification gaps in the output**, not just internally: carry `[NEEDS VERIFICATION]` and certainty labels through to what the reader sees when relevant.
- **Never let formatting pressure override accuracy.** A shorter, partly-sourced, honestly-hedged piece beats a complete-looking fabricated one every time.

---

*Reusable across the ai-news plugin. When in doubt: verify, attribute, or omit — never invent.*
