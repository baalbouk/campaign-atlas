---
name: swipe-file-builder
description: Save campaigns the user loves into a structured local swipe file in their working directory. Creates and maintains a SWIPE.md index plus per-campaign cards in swipe/ folder. Use when the user says "save this", "swipe this", "add to my swipe file", "remember this campaign", or wants a personal library of inspiration they can grep, search, and revisit.
---

# Swipe File Builder

You maintain the user's personal swipe file — a local, version-controllable archive of marketing campaigns worth stealing from. Designers and creative directors have kept swipe files since Paul Rand. This is yours, in their working directory.

## What you produce

In the user's current working directory:

```
swipe/
├── SWIPE.md                      ← index, sorted by date added
├── 2026-05-15_axa-three-words.md
├── 2026-05-12_spotify-wrapped-2025.md
├── 2026-05-10_liquid-death-launch.md
└── ...
```

`SWIPE.md` is the table-of-contents the user actually reads. Each card is the deep-dive of one campaign.

## Workflow

### Step 1 — Establish or locate the swipe folder

Check if `swipe/` exists in the user's current working directory.
- If yes — use it.
- If no — create `swipe/` and a starter `SWIPE.md` (template below).

If the user is in a folder that clearly isn't theirs (a system folder, a temp dir), ask where they want their swipe file kept. Default suggestion: their Documents or a dedicated `~/marketing-swipe/` folder.

### Step 2 — Capture the campaign

You need enough to make a useful card. If the conversation has just produced a campaign deep-dive (via `campaign-deep-dive`), reuse that content directly. If not, you have two paths:

- **The user named a campaign** — run a brief version of `campaign-deep-dive` to produce the card.
- **The user pasted a URL or attachment** — fetch / read it and extract the structured data.

Required fields for every card:
- Campaign name
- Brand · Agency · Country · Year
- Awards (if any)
- One-line insight
- One-line mechanic
- Why the user saved it (their reason — ask if not implicit)
- Primary source URL
- Date added (today's date)
- Tags (industry, mechanic-type, channel, region — for grep-ability later)

### Step 3 — Write the card

Filename: `swipe/YYYY-MM-DD_kebab-case-campaign-name.md`

Card template:

```
---
campaign: "Campaign Name"
brand: "Brand"
agency: "Agency, City"
country: "Country"
year: 2026
date_added: 2026-05-15
awards:
  - "2026 Cannes Lions Direct Lions Grand Prix"
  - "WARC Creative 100 #1"
tags: [insurance, social-purpose, product-as-message, france, tier1]
source: "https://www.canneslions.com/news/..."
---

# [Campaign Name]
**Brand · Agency · Country · Year**

## Why I saved it
[1–3 sentences in the user's own voice if they gave a reason; otherwise neutral.]

## The insight
[One sharp sentence.]

## The mechanic
[2–4 sentences.]

## Transferable lesson
- [bullet]
- [bullet]
- [bullet]

## Source
[Primary URL]

---
*Saved [date]. To re-deep-dive: run /analyze [campaign name].*
```

### Step 4 — Update SWIPE.md

Append (don't rewrite) to the index. Format:

```
# Swipe File
*Last updated: [today's date]*

A personal library of marketing campaigns worth stealing from.
Run `/swipe [campaign]` to add. Run `/analyze [campaign]` to re-deep-dive any saved card.

## Recently added

| Date | Campaign | Brand | Tags | Card |
|------|----------|-------|------|------|
| 2026-05-15 | Three Words | AXA | insurance, social-purpose, france | [↗](swipe/2026-05-15_axa-three-words.md) |
| 2026-05-12 | Wrapped 2025 | Spotify | data-as-creative, social, identity | [↗](swipe/2026-05-12_spotify-wrapped-2025.md) |
...

## By tag
*Auto-generated from card frontmatter — do not edit by hand.*

### insurance
- AXA Three Words

### social-purpose
- AXA Three Words
- ...
```

When you append, also re-build the "By tag" section by reading all card frontmatters. Keep the index sorted newest-first.

### Step 5 — Confirm and prompt

After saving, output:

```
✅ Saved to swipe/2026-05-15_axa-three-words.md
   Indexed in swipe/SWIPE.md

Want to also:
- Transplant the mechanic to your brand? (use the inspiration-transplant skill)
- Find similar campaigns? (use the campaign-scout skill — "find me more like AXA Three Words")
```

## Bulk operations

If the user just got a shortlist from `campaign-scout` and says "save them all" — confirm count, then write all cards in one batch and update the index once.

If the user says "save my whole conversation" — extract every campaign mentioned with sufficient detail and create cards for each. Ignore campaigns that were only name-dropped without analysis.

## Search and re-surface

If the user asks "what did I save about [topic / industry / mechanic]" — read SWIPE.md and the relevant card frontmatters, return matches. Don't re-fetch from the web.

If the user asks "show me my swipe file" — list the index in the chat.

## Discipline

1. **Never silently overwrite.** If a card with the same campaign name exists, ask: update existing or create dated revision (e.g. `_v2.md`)?
2. **Keep frontmatter machine-parseable.** YAML, valid syntax, no trailing commas, lowercase tags with hyphens.
3. **Don't fabricate tags.** Tags must come from the actual content of the deep-dive — don't invent "AI-powered" if the campaign wasn't AI-powered.
4. **Respect the user's voice.** If they wrote a "why I saved it" reason, preserve it verbatim. Don't editorialize.
5. **Never push to git.** This is the user's local file. Mention git only if they explicitly ask.
