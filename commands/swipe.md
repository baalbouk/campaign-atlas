---
description: Save a campaign (or shortlist) to your local swipe file as a structured card.
argument-hint: [campaign name, URL, or "all" to save the current shortlist]
allowed-tools: Read, Write, Edit, Glob
---

# /swipe

Use the **swipe-file-builder** skill to save the campaign(s) to the user's local `swipe/` folder.

Target: **$ARGUMENTS**

Behavior:
- If `$ARGUMENTS` is empty and there's an active deep-dive in conversation → save that one.
- If `$ARGUMENTS` is "all" and there's an active shortlist → save all (confirm count first).
- If `$ARGUMENTS` is a campaign name → run a brief deep-dive then save.
- If `$ARGUMENTS` is a URL → fetch, extract, save.

Always update both the per-campaign card and `SWIPE.md` index. Confirm the save with the file paths and offer the next moves (transplant / find similar).
