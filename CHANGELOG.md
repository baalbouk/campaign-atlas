# Changelog

All notable changes to Campaign Atlas will be documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
This project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] — 2026-05-15

### Added
- Five core skills:
  - `campaign-scout` — find world-elite campaigns by brief
  - `campaign-deep-dive` — 8-section forensic anatomy of a single campaign
  - `trend-radar` — last-90-days scan of what's working
  - `swipe-file-builder` — local structured swipe library
  - `inspiration-transplant` — translate elite mechanics into 5–7 brand concepts
- One specialist subagent: `campaign-research-scout` for parallel deep web research
- Four slash commands: `/find-campaigns`, `/analyze`, `/trend-radar`, `/swipe`
- Four reference files Skills auto-load:
  - `awards-taxonomy.md` — Tier-1/2/3 award classification with authority URLs
  - `analysis-frameworks.md` — strategic vocabulary (insight → tension → idea → mechanic), Binet & Field, Sharp/Ehrenberg-Bass
  - `modern-channels.md` — current channel landscape with what's actually moving in 2025–2026
  - `source-list.md` — ranked source trust tiers including regional trade press
- Anti-hallucination guards in every skill (no campaign without primary source)
- Region-balance enforcement (forced non-Western inclusion when brief allows)
- Recency-balance enforcement (mix of timeless + current work)
- Scam-ad surfacing rules (flag credible investigations)
- Optional MCP search server auto-detection (Brave / Perplexity / Tavily)
- Single-repo marketplace install via `/plugin marketplace add`

## [Unreleased]

### Planned for v1.1
- Auto-generated creative brief output from `inspiration-transplant` selections
- Per-skill `examples/` test transcripts
- A `/campaign-of-the-week` command that returns a curated featured campaign
- Optional live HTML dashboard artifact ("Campaign of the Week" view that refreshes)

### Planned for v1.2
- Localization: SKILL.md descriptions in FR, ES, PT-BR, AR
- Specialty award coverage: Cannes Health Lions deep-dive flow for pharma marketers
- "Effectiveness only" filter mode for Effie / IPA-trained users
