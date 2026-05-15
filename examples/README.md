# Examples — Campaign Atlas in action

Real (lightly-anonymized) transcripts of using each skill. Useful as smoke-test inputs and as a feel for what good output looks like.

## /find-campaigns — discovering the brief

**Input:**
```
/find-campaigns sustainable luxury fashion campaigns 2024-2026
```

**Expected output shape:** A 5–8 item shortlist, each with award context, one-line insight, one-line mechanic, and a primary source URL. At least 2 entries from non-US/UK markets. No fabricated campaigns.

---

## /analyze — forensic deep-dive

**Input:**
```
/analyze AXA Three Words
```

**Expected output shape:** The 8-section anatomy:
1. The brief (1 sentence)
2. The insight (1 sharp sentence)
3. The tension / cultural moment
4. The strategic idea
5. The creative mechanic
6. Execution highlights (2–4 specific facts)
7. Results — with sources, distinguishing verified business outcomes from agency-reported metrics from earned-media vanity
8. The transferable lesson

Followed by a prompt to transplant or save.

---

## /trend-radar — last-90-days scan

**Input:**
```
/trend-radar B2B SaaS
```

**Expected output shape:**
- Time-stamped header (date + window)
- TL;DR three things to act on
- 6–10 signals each with: live brand example, why it works, how to act, sources
- "What I deliberately left out" section
- Next refresh date

---

## /swipe — saving a campaign

**Input (after a deep-dive):**
```
/swipe
```

**Expected behavior:**
- Creates `swipe/` folder if missing
- Writes a card with YAML frontmatter to `swipe/YYYY-MM-DD_kebab-name.md`
- Updates `swipe/SWIPE.md` index with the new entry and rebuilds the "By tag" section
- Confirms with the file paths

---

## Inspiration-transplant — converting research into action

**Input (in conversation, after a deep-dive of Spotify Wrapped):**
```
Now transplant Wrapped's mechanic to my B2B SaaS analytics product.
Audience: marketing ops leaders. Budget: scrappy. Geo: US + UK + EU.
Brand voice: dry, confident, never cute.
```

**Expected output shape:** 5–7 concept cards each with:
- Punchy concept name
- Reference + mechanic line
- Strategic bet (1 sentence)
- The idea (2–4 sentences)
- Lead asset
- Channel architecture (lead / amplifiers / earned hook)
- Why it could work (behavioral or cultural reason)
- Watch-outs (≥2)
- Effort tier (💰 / 💰💰 / 💰💰💰)

Range constraint: at least one scrappy, one product/service change, one earned-first, one paid-led, one contrarian.
