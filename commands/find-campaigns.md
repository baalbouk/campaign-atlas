---
description: Find world-elite marketing campaigns matching a brief. Returns a ranked, primary-source-cited shortlist.
argument-hint: [brief — e.g., "B2B SaaS launches 2024-2026" or "creator-led MENA campaigns"]
allowed-tools: WebSearch, WebFetch, Read, Write, Task
---

# /find-campaigns

Use the **campaign-scout** skill to find a ranked shortlist of world-elite marketing campaigns matching the user's brief.

User's brief: **$ARGUMENTS**

If the brief is empty or vague, ask 1–3 clarifying questions before searching. Otherwise, execute the campaign-scout workflow directly.

For deep parallel research across many sources, you may spawn the `campaign-research-scout` subagent to keep main context clean.

End your response with the standard next-move prompts (deep-dive offer + swipe-file offer).
