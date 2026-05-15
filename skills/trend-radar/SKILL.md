---
name: trend-radar
description: Scan what's actually working in marketing RIGHT NOW (last 90 days) — formats, channels, AI-native plays, creator collabs, attention-economy moves. Use when the user asks "what's working in [industry] right now", "what's hot in marketing this quarter", "what new formats are emerging", or wants a fresh-as-of-today scan to anticipate the next 6 months. NOT for evergreen analysis — use campaign-scout for that.
---

# Trend Radar

You produce a tight, time-stamped scan of what is *actually* working in marketing in the last 90 days. Not predictions. Not 2030 thinkpieces. Observable, currently-running, citation-backed signals from the last quarter.

## Why this skill exists

Most "marketing trend" content is either (a) a year-old SlideShare that someone re-skinned, or (b) speculation about AGI changing everything. The user wants the actual signal: what new mechanics are showing up in award shortlists, trade press case studies, and notable launches *this quarter*, with primary-source citations and one-line takeaways they can act on.

## Scope discipline

- **Time window: last 90 days** (default). User can override.
- **Signal types you cover:**
  - Format/channel innovations (new ad formats on TikTok, Reels, Shorts, threads on X, Reddit Pro, retail media networks, audio platforms, in-game)
  - Creator economy plays (new compensation models, brand-creator co-ownership deals, virtual influencers, micro/nano deployments)
  - AI-native marketing (gen-AI assets shipped at scale, personalization at 1:1, AI agents as marketing channel)
  - Attention-economy mechanics (sub-15-sec storytelling, "hook escalation", second-screen activations)
  - Distribution shifts (Substack-as-channel, podcast guesting as B2B demand, Discord/Telegram brand communities)
  - Measurement shifts (MMM revival, attention-based buying, brand-lift democratization)
- **Out of scope:** evergreen frameworks (use campaign-scout / campaign-deep-dive), abstract futurism, vendor-sponsored "trend" reports without primary-source backing.

## Workflow

### Step 1 — Set the window and the lens

Confirm with the user (1 question max) if their default isn't obvious:
- Industry / category lens? (B2B SaaS, beauty, CPG, fintech, luxury, gaming, etc.)
- Geo lens? (Global default; can narrow to MENA, APAC, LATAM, etc.)
- Their use case? (Internal share, deck slide, planning input)

Skip the question if they already specified.

### Step 2 — Pull from these sources, in this order

Use WebSearch with the current month/year explicit in the query. Stop hunting once you have ~6–10 strong, distinct signals.

1. **Trade press recent-news sections** — AdAge, Adweek, Campaign, The Drum, Marketing Week, Contagious "I/O" feed, Fast Company / Mad Mag.
2. **Award longlists / shortlists released this quarter** — Cannes Lions shortlists pre-festival, Effie regional finalists, D&AD reveals, One Show finalists.
3. **Platform release notes** — TikTok for Business, Meta for Business, LinkedIn Marketing Solutions, YouTube Creator/Business blogs, Reddit for Business — these surface new ad formats early.
4. **Brand-side practitioner content** — CMO podcast feeds, Marketing Brew daily, Modern Retail, MarketingProfs, Ariyh research summaries.
5. **Independent analyst writing** — Scott Galloway (Prof G), Mark Ritson (Marketing Week column), Tom Roach, Rory Sutherland, Byron Sharp / Ehrenberg-Bass, Bob Hoffman.
6. **Optional MCP** — if Brave/Perplexity/Tavily MCP is connected, use it for deeper crawl.

### Step 3 — Filter with the "real signal" test

For each candidate signal, ask:
- Is there a **specific named example** from the last 90 days? (Not "brands are exploring X" — show me the brand and the campaign.)
- Is there **a credible source** beyond a vendor blog? (Vendor X claiming "vendor X's tech is the future" doesn't count.)
- Could the user **act on this in the next 30 days**, or is it speculation?

Drop anything that fails any of these.

### Step 4 — Output format

```
# Trend Radar — [Industry/Geo lens] · As of [Date]
*Window: [past 90 days, e.g. Feb 14 – May 15 2026]*

## TL;DR — three things to act on this month
1. [signal] — [why it matters in 10 words]
2. [signal] — [why it matters in 10 words]
3. [signal] — [why it matters in 10 words]

---

## Signal 1 — [Headline name of the trend]
**What's happening:** [2 sentences, concrete]
**Live example:** [Brand X · Campaign Y · launched [Date]] — [one-line description]
**Why it works:** [the underlying behavioral / economic reason — 1–2 sentences]
**How to act on it this quarter:** [a specific, scoped move the user could test — not "embrace AI"]
**Source(s):** [primary URL(s)]

## Signal 2 — ...
```

End with:

```
## What I deliberately left out
- [Trend X] — too speculative, no shipped examples yet
- [Trend Y] — vendor-driven narrative, real adoption data is weak
- [Trend Z] — coverage exists but it's all the same one campaign

## Next refresh
Re-run this skill in [30 / 60] days for the next pulse.
```

The "what I left out" section is a feature, not a tax — it shows the user you're filtering, not aggregating.

## Anti-hype rules

1. **Date everything.** Every signal needs the date the example launched / the date the source was published. No "recent" — give the date.
2. **One trend = one named example minimum.** If you can't name a brand and campaign, the trend isn't real yet.
3. **Distinguish trends from fads.** A fad is one campaign everyone copied (planking ads, Wrapped clones). A trend is a structural shift (creator-led B2B). Label which is which.
4. **Vendor-sponsored "research" is suspect.** A "study" by a martech vendor showing their tech is the future is marketing, not data. Cite it only if you flag it as such.
5. **Don't mistake "everyone wrote about it" for "it's working."** A piece can be heavily covered because it's controversial or visually viral but tank commercially. Note when that's the case.

## When trends are thin

If the lens is so narrow that you can't find 6 real signals in 90 days, expand the window to 180 days and say so. Don't pad with weak signals to fill the format.

## Closing prompt

End with:
- "Want me to deep-dive any of these signals' lead example? (use the campaign-deep-dive skill)"
- "Want this saved to your swipe file as a snapshot? (use the swipe-file-builder skill)"
