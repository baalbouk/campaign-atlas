# Installation Guide — Campaign Atlas

Three ways to install. Pick the one that matches your setup.

---

## ✅ Option 1 — One-line marketplace install (recommended)

This is the cleanest path. Works on Claude Code v2+ on macOS, Linux, and Windows.

### Steps

1. Open Claude Code in any project.

2. Add the marketplace:
   ```
   /plugin marketplace add baalbouk/campaign-atlas
   ```

3. Install the plugin:
   ```
   /plugin install campaign-atlas@campaign-atlas
   ```

4. (If commands don't appear immediately) restart Claude Code.

5. Verify:
   ```
   /plugin list
   ```
   You should see `campaign-atlas` in the enabled list.

6. Test it:
   ```
   /find-campaigns Cannes 2026 Direct Lions winners
   ```
   You should get a sourced shortlist within 30–60 seconds.

### Updating

```
/plugin marketplace update baalbouk/campaign-atlas
/plugin update campaign-atlas
```

### Uninstalling

```
/plugin uninstall campaign-atlas
/plugin marketplace remove baalbouk/campaign-atlas
```

---

## 🛠 Option 2 — Manual git clone (for forking, customizing, or air-gapped setups)

If you want to fork, modify the reference files, or you don't have outbound access to the GitHub marketplace flow.

### Steps

1. Clone into your Claude Code plugins directory.

   **macOS / Linux:**
   ```bash
   mkdir -p ~/.claude/plugins
   git clone https://github.com/baalbouk/campaign-atlas.git ~/.claude/plugins/campaign-atlas
   ```

   **Windows (PowerShell):**
   ```powershell
   New-Item -Path "$env:USERPROFILE\.claude\plugins" -ItemType Directory -Force
   git clone https://github.com/baalbouk/campaign-atlas.git "$env:USERPROFILE\.claude\plugins\campaign-atlas"
   ```

2. Restart Claude Code.

3. Verify with `/plugin list` and `/find-campaigns test`.

### Updating (manual)

```bash
cd ~/.claude/plugins/campaign-atlas
git pull
```

Then restart Claude Code.

---

## 📦 Option 3 — Workspace-local install (only for one project)

If you want this plugin available **only** in one specific project, not globally:

1. Inside that project root:
   ```bash
   mkdir -p .claude/plugins
   git clone https://github.com/baalbouk/campaign-atlas.git .claude/plugins/campaign-atlas
   ```

2. Add `.claude/plugins/` to your `.gitignore` if you don't want it tracked:
   ```bash
   echo ".claude/plugins/" >> .gitignore
   ```

3. Restart Claude Code in that project.

---

## Optional — Connect a search MCP for deeper research

Campaign Atlas works fully with Claude Code's built-in `WebSearch` and `WebFetch`. **You don't need any of this to start.**

If you want premium-tier research depth, install one of these MCP servers (any one is enough):

### Brave Search
```
/plugin install brave-search@anthropic
```
Get an API key at https://brave.com/search/api — paste into Claude Code settings.

### Perplexity
Install via `npx @perplexity-ai/mcp-server` per Perplexity docs. API key from https://docs.perplexity.ai/.

### Tavily
Install via `npx tavily-mcp` per Tavily docs. API key from https://tavily.com/.

Campaign Atlas auto-detects whichever you have configured and uses it for deeper crawls. **Zero config needed on Campaign Atlas's side.** It silently falls back to `WebSearch` if no MCP is present.

---

## Troubleshooting

### `/plugin marketplace add` returns "marketplace not found"
- Ensure you have outbound HTTPS to `github.com` and `raw.githubusercontent.com`.
- Try the manual git-clone path (Option 2).

### Slash commands don't appear after install
- Fully quit and relaunch Claude Code (Cmd-Q on macOS, then reopen).
- Run `/plugin list` and confirm `campaign-atlas` is enabled (not just installed).
- If it's installed but disabled, run `/plugin enable campaign-atlas`.

### `/find-campaigns` runs but returns no results
- Check that your Claude Code has WebSearch enabled (Settings → Tools).
- Try a more specific brief — `"campaigns about X"` is too vague; `"B2B SaaS launch campaigns 2024-2026"` works.

### "I don't have web access to GitHub from my network"
Use Option 2's manual clone over a corporate proxy or pre-fetched zip:

```bash
# On a machine with internet access
git clone https://github.com/baalbouk/campaign-atlas.git
zip -r campaign-atlas.zip campaign-atlas

# Transfer the zip to the air-gapped machine, then:
unzip campaign-atlas.zip -d ~/.claude/plugins/
```

### Permission issues on macOS Sequoia / Sonoma
If Claude Code can't write to `~/.claude/plugins/`:
```bash
chmod -R u+rwX ~/.claude/plugins/
```

### Windows: long path errors
Enable long paths:
```powershell
git config --system core.longpaths true
```

---

## Verify everything works

Run this 30-second smoke test after install:

```
1. /plugin list                          → see campaign-atlas enabled
2. /find-campaigns Cannes 2026 winners   → shortlist appears with sources
3. /analyze AXA Three Words              → 8-section deep-dive appears
4. /trend-radar B2B SaaS                 → trend signals appear with named brand examples
5. /swipe                                → swipe/ folder created in cwd
```

If all five pass, you're shipped.

---

## Need help?

Open an issue at https://github.com/baalbouk/campaign-atlas/issues with:
- Your OS + Claude Code version (`claude --version`)
- The exact command you ran
- The exact error / output you saw

PRs welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).
