<div align="center">

# 🌍 Campaign Atlas

**Reverse-engineer the world's most awarded marketing campaigns inside Claude Code.**

*Five skills for finding, dissecting, and stealing from the global elite — Cannes Lions, Effies, WARC, D&AD, One Show, Webby. Primary-source cited. Anti-hallucination. Modern-channel aware.*

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Claude Code Plugin](https://img.shields.io/badge/Claude_Code-Plugin-D97757)](https://code.claude.com/docs/en/plugins)
[![Made for marketers](https://img.shields.io/badge/made_for-marketers-black)](#)

</div>

---

## What it does

You ask: *"Find me the best B2B SaaS launch campaigns from the last two years."*
Claude returns: a primary-source-cited shortlist with awards, insights, mechanics, and links — pulled live from Cannes Lions, Effie, WARC, AdAge, Contagious, and agency case-study libraries.

Then you ask: *"Deep-dive AXA Three Words."*
Claude returns: an 8-section forensic anatomy — brief, insight, tension, strategic idea, mechanic, execution, sourced results, transferable lesson.

Then you ask: *"Save it to my swipe file. Now transplant the mechanic to my fintech brand."*
Claude saves a structured card to your local `swipe/` folder, then generates 5–7 concrete campaign concepts you could brief in this week.

That's the loop.

## The five skills

| Skill | Trigger phrases | What it does |
|---|---|---|
| **🔍 campaign-scout** | *"find me campaigns about…"*, *"best X in Y"*, *"who won at Cannes for…"* | Ranked, sourced shortlist of elite campaigns matching your brief |
| **🔬 campaign-deep-dive** | *"analyze X"*, *"break down Y"*, *"anatomy of Z"* | Forensic 8-section breakdown of one campaign |
| **📡 trend-radar** | *"what's working in X right now"*, *"what's hot this quarter"* | Last-90-days scan of formats, channels, plays — with named examples |
| **💾 swipe-file-builder** | *"save this"*, *"swipe this"*, *"add to my swipe file"* | Builds a local `swipe/` folder of structured campaign cards |
| **💡 inspiration-transplant** | *"apply this to my brand"*, *"do an X for me"* | Translates elite mechanics into 5–7 concepts for your brand |

Plus four slash commands you can invoke directly:

```
/find-campaigns [brief]
/analyze [campaign or URL]
/trend-radar [industry]
/swipe [campaign or "all"]
```

And one specialist subagent (`campaign-research-scout`) that the skills auto-spawn for heavy parallel research without burning your main context window.

---

## Install

### One-line install (recommended)

Inside Claude Code:

```bash
/plugin marketplace add baalbouk/campaign-atlas
/plugin install campaign-atlas@campaign-atlas
```

That's it. Restart Claude Code if commands don't appear immediately.

### Manual install

Clone the repo into your Claude Code plugins directory:

```bash
git clone https://github.com/baalbouk/campaign-atlas.git ~/.claude/plugins/campaign-atlas
```

Then restart Claude Code.

### Verify install

In Claude Code, run:

```
/plugin list
```

You should see `campaign-atlas` enabled. Try:

```
/find-campaigns Cannes 2026 Direct Lions winners
```

If you get a sourced shortlist, you're live.

---

## Quick start (90 seconds)

```bash
# 1. Find elite work in your space
/find-campaigns sustainable luxury fashion campaigns 2024-2026

# 2. Deep-dive one that catches your eye
/analyze Stella McCartney Future of Fashion

# 3. Save to your local swipe file
/swipe

# 4. Transplant the mechanic to your own brand
"Now transplant the underlying mechanic to my [your brand], a [your category]
 trying to [your objective]. Audience: [your audience]. Budget tier: scrappy."
```

You'll get 5–7 concrete concepts, each with strategic bet, lead asset, channel architecture, watch-outs, and effort tier.

---

## Why it's different from "ChatGPT, summarize a marketing campaign"

| Generic LLM use | Campaign Atlas |
|---|---|
| Hallucinates campaigns that never existed | **Refuses to cite a campaign without a primary-source URL** |
| US/UK-biased examples | **Forces non-Western balance by default (Brazil, Japan, India, MENA, Korea, Nordics, LATAM)** |
| Quotes "300% lift" with no source | **Distinguishes verified business outcomes from agency claims from earned-media vanity metrics** |
| Treats Old Spice as a 2010 reference | **Mixes timeless reference work with last-90-days signals** |
| Misses scam-ad red flags | **Surfaces credible scam-ad investigations and rescinded awards** |
| One-shot answers | **Five-skill loop: scout → deep-dive → transplant → swipe → trend-radar** |
| Generic "be creative" advice | **Mechanic-level transplant: distills the structural move you can re-run, not the execution you'd be ripping off** |

---

## What the skills load (and why this matters)

Each skill reads four reference files at session start:

- **`reference/awards-taxonomy.md`** — what counts as a Tier-1 award, by region and specialism, with authority URLs
- **`reference/analysis-frameworks.md`** — the strategic vocabulary (insight → tension → idea → mechanic → execution → effect), Binet & Field, Sharp/Ehrenberg-Bass, attention research, mechanic types
- **`reference/modern-channels.md`** — what's actually moving in 2025–2026 (TikTok, RMNs, CTV, podcasts, creator co-ownership, gen-AI creative)
- **`reference/source-list.md`** — ranked source trust tiers, regional trade press, search-query patterns

These keep Claude's analysis consistent across sessions and prevent drift toward generic marketing-speak.

---

## Optional: supercharge with an MCP search server

Campaign Atlas works fully with Claude Code's built-in `WebSearch` and `WebFetch`. **No API keys required.**

If you want deeper crawl, Campaign Atlas auto-detects and uses any of these MCP servers if connected:

- **Brave Search MCP** — better for fresh / regional results
- **Perplexity MCP** — better for synthesized research
- **Tavily MCP** — better for structured web extraction

Skills detect availability silently. They never error if no MCP is present. You don't need to do anything — install an MCP server in Claude Code and Campaign Atlas uses it automatically when relevant.

---

## Examples in action

### Example 1 — Cold scout

```
> /find-campaigns insurance brands doing social-purpose work, 2023-2026

# Shortlist: insurance brands · social-purpose · 2023–2026

## 1. Three Words — AXA, Publicis Conseil, Paris (2025)
**Awards:** 2026 Cannes Lions Direct Lions Grand Prix · Creative Strategy Grand Prix · WARC Creative 100 #1 (2026)
**Insight:** Insurance contracts can be a delivery mechanism for social action, not just legal protection.
**Mechanic:** Added the words "and domestic violence" to AXA's home insurance contract in France — when victims call the emergency number, they're immediately relocated and supported.
**Why it fits your brief:** Pure product-as-message, won the most prestigious double-Grand-Prix of 2026.
**Source:** https://www.canneslions.com/news/...

## 2. ...
```

### Example 2 — Deep-dive

```
> /analyze Spotify Wrapped 2025

# Spotify Wrapped 2025
**Brand:** Spotify · **Agency:** In-house + FCB NY · **Year:** 2025 · **Market:** Global
**Awards:** [pulled live]

## 1. The brief
Drive Q4 active-user re-engagement and convert free-tier listeners to Premium during gift-giving season.

## 2. The insight
People want to use Spotify not just to listen, but to *perform their identity* on social — but they only do it once a year, when prompted.

## 3. The tension / cultural moment
[continued...]
```

### Example 3 — Transplant

```
> Now transplant Wrapped's mechanic to my B2B SaaS analytics product (audience: marketing ops leaders, budget: scrappy).

## Concept 1: Stack Wrapped
*Transplants: Spotify Wrapped · Mechanic: first-party data → identity asset, released annually as cultural moment*

**Strategic bet:** Marketing ops leaders quietly love showing off their stack — give them a year-end visual receipt to share on LinkedIn.

**The idea:**
End-of-year, send each customer a personalized "Your Stack 2026" microsite — top 3 dashboards built, # of integrations shipped, hours saved, weirdest custom event name they tracked. Built to screenshot.

**Lead asset:** Personalized microsite (one URL per customer)
**Channel architecture:**
- Lead: in-product CTA + email
- Amplifiers: LinkedIn (sized for the post format), X
- Earned hook: weirdest-custom-event-name leaderboard (opt-in)

**Why it could work:** Marketing ops sits in a discipline that craves recognition; LinkedIn is their stage; year-end reflection content already over-indexes in their feeds.

**Watch-outs:**
- Privacy — must use only the customer's own data, not their end-users'
- Risk of looking like a Wrapped clone if not visually differentiated

**Effort tier:** 💰 scrappy (microsite generator + 1 designer + email)
```

---

## What's NOT in v1 (yet)

Honest about scope. v1 ships these five skills. Not in scope (yet):

- **Live award-show scoring predictions** — interesting but speculative
- **Auto-generated creative briefs from the transplant concepts** — coming in v1.1
- **Image/video asset generation** — out of scope; use a dedicated image MCP
- **Campaign performance benchmarking against your own KPIs** — connect a data MCP
- **Auto-PR generation** — out of scope

See [CHANGELOG.md](CHANGELOG.md) for what's shipped and roadmap.

---

## Contributing

Yes, please. See [CONTRIBUTING.md](CONTRIBUTING.md). The two highest-leverage things you could contribute:

1. **More regional source coverage** — especially APAC, LATAM, and African trade press in `reference/source-list.md`
2. **Frontend examples** — show how you used Campaign Atlas in a real project (anonymous okay)

---

## Methodology

Built using the **Get Shit Done (GSD)** spec-driven loop: research → discuss → plan → execute → verify → ship. Each skill was written from the same skeleton — research first, structure next, anti-hallucination guards last. See `CONTEXT.md` for the design decisions if you want to fork.

---

## License

[MIT](LICENSE) — use it, fork it, ship it. If you build something cool with it, tag the repo so I can see.

---

<div align="center">

**Built by [Bold Creatives](https://github.com/baalbouk).**
*If you know clearly what you want, this WILL find it. No bs.*

</div>
