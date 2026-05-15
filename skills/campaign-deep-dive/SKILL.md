---
name: campaign-deep-dive
description: Reverse-engineer a single marketing campaign — its brief, insight, strategy, creative idea, channel architecture, execution, and verifiable results. Use when the user names a specific campaign ("analyze Spotify Wrapped", "break down AXA Three Words", "what made Liquid Death's launch work", "anatomy of Dove Real Beauty"), pastes a campaign URL, or wants to understand WHY a famous campaign succeeded.
---

# Campaign Deep-Dive

You take one campaign and produce a forensic anatomy of it. Not a recap. Not a press release in different words. A structured breakdown that lets the user reuse the underlying mechanic on their own work.

## What you're producing

A single document, ~600–1200 words, structured in 8 sections. Same skeleton every time. The user should be able to scan it in 60 seconds and absorb it in 5 minutes.

## Workflow

Read `${CLAUDE_PLUGIN_ROOT}/reference/analysis-frameworks.md` once before starting your first deep-dive in a session. It defines the strategic lens (insight → tension → idea → mechanic → execution → effect) you should apply consistently.

### Step 1 — Identify the campaign unambiguously

If the user names a campaign that has multiple variants or a multi-year arc (Dove Real Beauty has run since 2004 across dozens of executions), confirm which specific entry/year/market they want. Don't guess.

### Step 2 — Source the truth

Pull from primary sources, in this order:

1. **The award case study** — Cannes Lions, Effie, WARC, D&AD case write-ups are the single best source. They're fact-checked by judges.
2. **The agency's own case page** — usually has the strategic intent, but treat results claims with mild skepticism (agencies puff their numbers).
3. **The brand's investor or press materials** — if results were significant enough to mention to shareholders, the numbers are real.
4. **Independent trade press analysis** — Contagious, AdAge, Adweek, WARC editorial. These often add critical perspective the agency case omits.
5. **Effectiveness research** — IPA Databank, Effie Index, Effective Marketing Hall of Fame, the Ehrenberg-Bass Institute publications.

If the campaign is recent (last 90 days) and award case studies don't exist yet, lean harder on trade press and the brand newsroom — and flag in the output that effectiveness data is preliminary.

### Step 3 — Build the deep-dive

Use this exact 8-section structure:

```
# [Campaign Name]
**Brand:** [Brand]  ·  **Agency:** [Agency, City]  ·  **Year:** [Year]  ·  **Market:** [Country/Region]
**Awards:** [list specific awards with categories]

## 1. The brief (in one sentence)
What was the brand actually trying to do? Sales? Reposition? Defend against a challenger? Recruit a new buyer? State it as a brief, not as marketing-speak.

## 2. The insight
The human truth the campaign is built on. Insights are observations about how people actually behave, not platitudes. "Women feel insecure about beauty" is a platitude. "Women describe themselves more harshly than strangers describe them" (Dove Real Beauty Sketches) is an insight.

## 3. The tension / cultural moment
What was happening in the world or category that made this campaign land at this exact moment? (Spotify Wrapped works because of social-media identity performance. AXA Three Words works in a moment of increased domestic violence visibility post-pandemic.)

## 4. The strategic idea
The one-sentence proposition the campaign rests on. Not the tagline. The strategic bet. (Old Spice 2010: "Reposition as the brand women buy for their men, not the brand men reluctantly buy for themselves.")

## 5. The creative mechanic
What did they actually DO that no one had done before — or done in this combination? Be concrete. Include the channel architecture (lead asset, supporting assets, paid/owned/earned mix, tech enablers).

## 6. Execution highlights
2–4 specific, observable details that show the craft. ("They responded to ~180 individual tweets with custom-shot videos in 48 hours, with the same actor.") Not adjectives.

## 7. Results — with sources
Use this format:
- **[Metric]:** [number] *(source: [where])*

Distinguish:
- ✅ Verified business outcomes (sales lift from Nielsen / brand internal data disclosed publicly)
- 🟡 Brand metrics (awareness, consideration, NPS) — usually agency-reported
- 🟠 Earned media / vanity metrics (impressions, views, PR pieces) — least rigorous

If a number doesn't have a source, don't include it.

## 8. The transferable lesson
2–4 bullets — what *mechanic* (not "be brave" platitude) can be lifted and applied to other categories? The reader should be able to point at this and say "I could do a version of this for [their brand]."
```

### Step 4 — End with a prompt

Close with one of:
- "Want me to transplant this mechanic to your brand? (use the inspiration-transplant skill)"
- "Want this saved to your swipe file? (use the swipe-file-builder skill)"

## Anti-puff rules

1. **No adjective stacking.** "Iconic, groundbreaking, era-defining campaign that revolutionized…" — cut all of it. The campaign's facts make the case.
2. **Sources for every number.** No unsourced "300% lift" claims. If the source is the agency's own case study, say so.
3. **Distinguish strategy from tactics.** The strategic idea is a sentence. The mechanic is the execution. Don't confuse them.
4. **Be honest about scam ads.** If credible reporting (e.g. AdAge investigation, IPA flagging, Storyboard18 coverage) suggests a campaign was a scam ad — created mostly to win awards rather than to run as a real client engagement — surface that. Famous example: ongoing investigations into select DM9 / DDB Brazil work.
5. **Be honest about misses.** If the campaign won awards but flopped commercially (Pepsi Refresh Project being a famous case), say so. If it succeeded creatively but ethical concerns later emerged (Dove "racist soap" controversy adjacent to Real Beauty work), note the context.

## When the campaign is too new

For campaigns < 90 days old: deliver the deep-dive but mark Section 7 as "Preliminary — full effectiveness data not yet available; revisit at WARC Q+ release / next Effie cycle." Don't fake numbers.

## When you can't verify the campaign

If you genuinely cannot find primary-source confirmation that the campaign exists as described, stop and tell the user: "I can't verify this campaign from a primary source. Did you mean [closest match]?" Better to look uninformed for 5 seconds than to invent a fake case study.
