# Design Decisions — Campaign Atlas

This file documents *why* Campaign Atlas is built the way it is. Useful if you're forking, contributing, or just curious.

## North-star outcome

> "I'm a marketer, founder, or strategist. I open Claude Code. In 90 seconds I have a sourced shortlist of world-elite campaigns for my exact brief. In 5 minutes I have a forensic deep-dive on one of them. In 15 minutes I have 5–7 concrete concepts for *my* brand based on its mechanic. And it's all saved in my local swipe file for next time."

Every design decision is judged against that outcome.

## Why a plugin (not a single skill)

A skill is a single SKILL.md file. It can't be installed standalone, can't bundle reference docs cleanly, and can't ship with slash commands or subagents.

The user wanted "public for use" and "easy to install." Only a Claude Code plugin satisfies both — installable from a GitHub URL with one command, distributes skills + agents + commands + reference docs as a single bundle.

## Why five skills, not one mega-skill

Single mega-skills lose to focused skills in two ways:
1. They have less precise triggering — Claude has to guess which sub-task you want.
2. They're harder to evolve — every change risks regressions in other modes.

The five skills here have **mutually exclusive trigger phrases**, which means low ambiguity for Claude's skill router. Each one does one thing.

## Why a separate `campaign-research-scout` subagent

Web search is expensive in context. A skill that does 20 WebSearch calls in the main loop pollutes the context window with raw search output, leaving less room for synthesis.

The subagent does the searching in its own fresh 200K-token context, then returns a distilled briefing (~500–800 words) to the parent. Parent context stays clean. This is the GSD pattern — research happens in subagents.

## Why reference files instead of stuffing everything into SKILL.md

Two reasons:
1. **Skills stay readable.** A 2,000-line SKILL.md no human can audit is worse than a 200-line one with explicit `Read` calls to reference docs.
2. **Reference files are version-controlled separately.** Updating the awards taxonomy doesn't require touching every skill.

The cost: skills must remember to `Read` the reference files. The skills' opening paragraphs make this explicit.

## Why anti-hallucination is the most-repeated rule

LLMs make up marketing case studies. They confabulate "campaigns" that have plausible names but never existed, and they invent results numbers. For a tool that's supposed to surface *real* world-class work, that's fatal.

So every skill repeats the rule: **no campaign without a primary-source URL.** It costs 5 seconds of "I couldn't verify that" honesty in exchange for never embarrassing the user with a fake citation in their deck.

## Why region-balance and recency-balance are forced defaults

Default LLM behavior on "best marketing campaigns" produces ~80% US/UK examples from the last 18 months. This systematically underweights:
- Award powerhouses in Brazil, India, Japan, Korea, MENA, LATAM
- Timeless reference work (Dove Real Beauty, Old Spice, Apple "1984") that the user *should* know
- Non-English-language craft (Japanese print, Brazilian film, Korean integrated)

Forcing balance by default produces a more honest map of the world. Users can override.

## Why "modern channels" is a separate reference doc

Marketing analysis written from a 2017 mental model (TV-led, paid-social-driven, banner-ad-aware) is increasingly wrong in 2026. Retail Media Networks, creator-co-owned brands, gen-AI native creative, agent-mediated commerce — these are first-class now.

The `modern-channels.md` doc anchors Claude in current reality. It's the file most likely to need quarterly updates.

## Why MCP support is optional, not required

Public-use plugins fail when they require API keys at install. The first 30 seconds of friction kills 80% of adoption.

So Campaign Atlas works fully out of the box with `WebSearch` and `WebFetch` (no keys). MCP servers (Brave, Perplexity, Tavily) are a *bonus* layer that the skills detect silently and use if present. Users who want premium depth can wire them up later.

## Why the swipe file is local Markdown, not a database

Markdown survives. Database files don't. The user owns their swipe file; they can grep it, version-control it, share it, port it to Notion/Obsidian/Roam, fork it across teams.

YAML frontmatter on each card makes it machine-parseable for the index re-build, without requiring any new tooling.

## Why "transplant" is its own skill, separate from "deep-dive"

Deep-diving and transplanting are cognitively different jobs:
- Deep-dive = analyze (descriptive)
- Transplant = generate (constructive)

Combining them makes both worse: the analysis becomes shallow because the model is also brainstorming, and the brainstorm becomes generic because the model didn't fully ground in the reference.

Splitting them lets the user run analyze-then-think-then-transplant, which mirrors how good strategists actually work.

## Why no co-authored-by Claude in commits

Per project owner instruction. Commits are clean.

## What we deliberately didn't build (and why)

- **Image / video generation** — Claude Code doesn't ship image gen; users who want it should connect a separate MCP. Not our problem to solve.
- **Pricing / budgeting calculators** — too brand-specific to be useful as a general tool.
- **A live award-show news ticker** — that's what `/trend-radar` ad-hoc is for. A ticker would create maintenance burden with low payoff.
- **An auto-PR or auto-press-release writer** — out of scope; risks low-quality output at brand-damaging scale.
- **Performance benchmarking against the user's own KPIs** — connect a data MCP for that.

## Versioning policy

- Patch (1.0.x) — copy edits to skills, reference files, README, INSTALL
- Minor (1.x.0) — new skill, new command, new reference file, behavior changes that users would notice
- Major (x.0.0) — breaking change to install path, plugin name, or directory structure

Always bump `version` in **both** `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json` together.
