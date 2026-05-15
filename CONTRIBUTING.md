# Contributing to Campaign Atlas

Thanks for considering a contribution. The goal of this plugin is to be the cleanest, most-cited tool for marketing campaign research inside Claude Code. Contributions that move it toward that goal are welcome.

## Highest-leverage contributions

In rough priority order:

1. **Regional source coverage** — `reference/source-list.md` and `reference/awards-taxonomy.md` lean a bit Western. PRs that add APAC, LATAM, African, and MENA sources / awards (with authority URLs) are gold.

2. **Edge-case coverage in skills** — found a case where `campaign-scout` hallucinates, or `campaign-deep-dive` misses an obvious framing? Open an issue with a reproducer and a proposed fix.

3. **Frontend examples** — show how you used Campaign Atlas in a real project. Drop a markdown file in `examples/` (anonymized if needed).

4. **Anti-puff rules** — if you spot Claude using marketing-deck adjective stacking when running these skills, flag it. The rules in each SKILL.md should evolve to suppress it.

5. **Localization** — the skills are English-only. PRs translating SKILL.md descriptions and reference docs to other languages are welcome.

## What we will NOT merge

- Fabricated campaigns or unverified case studies in the reference files
- Vendor-promoting content (e.g., "use [our marketing tool]" placements)
- AI slop — we read every PR
- Changes that loosen the anti-hallucination guards
- Changes that add tracking, analytics, or telemetry to the skills

## Development workflow

1. Fork → clone:
   ```bash
   git clone https://github.com/YOUR_USERNAME/campaign-atlas.git
   cd campaign-atlas
   ```

2. Symlink your fork into your local Claude Code plugins folder so you can test changes live:
   ```bash
   ln -s "$(pwd)" ~/.claude/plugins/campaign-atlas
   ```

3. Restart Claude Code. Run a smoke test:
   ```
   /find-campaigns Cannes 2026 Direct Lions winners
   ```

4. Make your changes. Edit any of:
   - `skills/<skill-name>/SKILL.md`
   - `reference/*.md`
   - `agents/*.md`
   - `commands/*.md`
   - `.claude-plugin/plugin.json` (bump `version` if changing behavior)
   - `.claude-plugin/marketplace.json` (bump `version` if changing behavior)

5. Test against your own real-world brief. Don't ship if you haven't actually run the modified skill end-to-end at least twice.

6. Open a PR with:
   - What changed and why (1–3 sentences)
   - Test transcript: paste the input and Claude's output before-and-after if behavior changed
   - Updated `CHANGELOG.md` entry under `## [Unreleased]`

## Code-of-conduct shorthand

Be sharp. Be honest. No personal attacks. PRs get critiqued on the work, not the contributor. Maintainer (you, after merging) keeps the final call on style/scope.

## License

By contributing, you agree your contributions are licensed under the MIT License (same as the project).
