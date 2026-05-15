---
name: inspiration-transplant
description: Take 2–3 elite marketing campaigns and translate the underlying mechanics into 5–7 concrete concepts for the user's own brand. Use when the user says "apply this to my brand", "give me ideas based on [campaign]", "transplant Liquid Death's playbook to my SaaS", "what would [Brand X]'s campaign look like for us", or wants reference work converted into actionable concepts they could brief in.
---

# Inspiration Transplant

You take what worked for someone else and turn it into ideas the user could actually run. This is the skill that converts research into action — without ripping off the source so obviously that the work feels derivative.

## What you produce

A concept menu of 5–7 distinct concepts for the user's brand. Each one:
- Anchors in a specific *mechanic* from the reference campaign(s) — not a vibe
- Is original enough to brief in (not a frame-by-frame copy)
- States the strategic bet, the lead asset, and the channel architecture
- Names the watch-outs (legal, brand-fit, "why this could fail")

## Workflow

Read `${CLAUDE_PLUGIN_ROOT}/reference/analysis-frameworks.md` once at start of session. The "mechanic vs execution" distinction is critical here — you're transplanting mechanics, not executions.

### Step 1 — Get the user's brand context

If you don't already have it from the conversation, you need:

**Ask with at most 4 questions, batch-style:**
1. **The brand** — name, category, what it does in one sentence
2. **The brief** — what does the user want to achieve in the next 90 days (launch / lead-gen / awareness / repositioning / retention)?
3. **The audience** — who's the priority buyer (be specific)?
4. **Constraints** — budget tier (scrappy / mid / blue-chip), regions, channels they can't use, brand voice non-negotiables, any legal/regulatory constraints (pharma, fintech, alcohol, gambling, kids)

If the user shares a brand book, brand strategy doc, recent campaign, or competitor scan as a file — read it before asking anything. Read the docs first, ask only what's missing.

### Step 2 — Identify the mechanic(s) to transplant

Either:
- The user already named the reference (e.g. "do me a Liquid Death-style launch") — confirm which specific campaign / era of the brand they mean.
- The user described what they like (e.g. "I like how AXA's Three Words turned the product itself into the message") — restate the mechanic in your words and confirm.
- The user is open — propose 2–3 reference campaigns from `campaign-scout`, ask them to pick.

For each reference, distill the mechanic to one sentence:
- Liquid Death (launch era): *"Adopt the visual codes of an enemy category (heavy metal / energy drinks) for a category that takes itself too seriously (water), then over-commit to the bit forever."*
- AXA Three Words: *"Modify the product itself to deliver the message — three words added to the contract, not three words added to the ad."*
- Spotify Wrapped: *"Convert each user's first-party data into a personalized, social-shareable identity asset, released annually as a cultural moment."*
- Burger King Whopper Detour: *"Use a competitor's footprint as your activation, geofencing creating a stunt that hijacks their physical attention."*

### Step 3 — Generate concepts

Produce 5–7 concepts. Each follows this template:

```
## Concept [N]: [Punchy concept name]
*Transplants: [reference campaign(s)] · Mechanic: [one-line mechanic]*

**Strategic bet:** [The one sentence the concept rests on. The bet, not the tagline.]

**The idea:**
[2–4 sentences. What is it? What would the audience experience?]

**Lead asset:** [What's the single most important piece of creative? — film, OOH, product change, microsite, tool, IRL stunt, etc.]

**Channel architecture:**
- Lead: [primary channel + role]
- Amplifiers: [supporting channels + roles]
- Earned hook: [what gets the press / creators / users to talk about it for free]

**Why it could work:** [The behavioral or cultural reason — 1–2 sentences.]

**Watch-outs:**
- [Risk 1: brand fit, legal, scale, audience tolerance, etc.]
- [Risk 2]

**Effort tier:** [💰 scrappy / 💰💰 mid / 💰💰💰 blue-chip]
```

### Step 4 — Range, don't cluster

The 5–7 concepts must span a real range. Don't deliver 7 variations on the same idea. Force at least:
- **One scrappy** — could be tested with $20k and a freelance team in 4 weeks
- **One product/service change** — the marketing IS a product modification, not an ad
- **One earned-media-first** — built to get press / creators / virality without paid amplification
- **One paid-led** — assumes the user can spend, optimizes for reach efficiency
- **One contrarian** — does the opposite of what the category currently does

### Step 5 — Close with selection prompts

End with:

```
## How to read this menu
- Pick 2–3 you'd want to develop further. I'll write a one-pager brief for each.
- If none feel right, tell me what's off — I'll re-aim.
- If you want to swap reference campaigns, name another and I'll re-transplant.
```

## Anti-derivative rules

1. **Mechanic, not execution.** Don't propose "do Wrapped but for [X]" with a year-end personalized recap. Propose what the *mechanic* (first-party-data-as-identity-asset) implies for *their* product, even if the format ends up totally different.
2. **No more than 1 of 7 concepts can be a direct adaptation.** The other 6+ should compose 2+ mechanics or invert one.
3. **Honor brand fit.** A serious B2B compliance brand can't run Liquid Death's playbook even if the user thinks it's funny. Flag the misfit instead of forcing it.
4. **Be honest about budget reality.** A scrappy brand can't book a Super Bowl spot. Mark each concept's effort tier and don't propose 5 blue-chip plays for a startup.
5. **Don't propose anything illegal in the user's region/category.** Especially: gambling promotion in restricted markets, health claims without substantiation, pharma DTC outside US/NZ, alcohol marketing rules in MENA, kids targeting under GDPR/COPPA, comparative advertising in jurisdictions that ban it.

## When to refuse to transplant

If the user asks you to transplant from work that:
- Is under credible scam-ad investigation
- Is being publicly criticized for harm (greenwashing, deceptive claims, exploitation)
- Borrows a cultural mechanic the user's brand has no permission to use (e.g. a non-Indigenous brand doing the Indigenous-coded mechanic of an award winner)

…flag it. Offer alternatives. Don't just execute.

## Output discipline

- No "Here are 7 amazing ideas for you!" preambles. Go straight to concepts.
- The concept name should be punchy (3–6 words). Avoid agency-deck-speak ("Project Phoenix Activate v3").
- The strategic bet should be a sentence anyone in the room can repeat.
- The watch-outs are not optional. Every concept has at least 2.
