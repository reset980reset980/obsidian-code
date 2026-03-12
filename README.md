# Claude Code for Windows

Windows-first Obsidian plugin for using Claude Code inside your vault.

This repository is a Windows-adapted fork of the original `reallygood83/obsidian-code` project. The original plugin content and workflow were taken as the base and changed for Windows usage, so this README only documents the Windows version.

## What It Does

- Chat with Claude from the Obsidian sidebar
- Read and edit files in your vault
- Run Claude Code tools and agent workflows
- Attach notes and folders as context
- Use inline edit flows directly inside notes
- Configure MCP servers, slash commands, and safety rules

## Requirements

You need Claude Code CLI installed on Windows.

```powershell
npm install -g @anthropic-ai/claude-code
```

Then authenticate once in a terminal:

```powershell
claude
```

If your subscription token expires, run:

```powershell
claude auth login
```

## Install

### BRAT

1. Install `BRAT` from Obsidian Community Plugins.
2. Run `BRAT: Add a beta plugin for testing`.
3. Paste:

```text
https://github.com/reset980reset980/obsidian-code
```

4. Select the latest release.
5. Enable `Claude Code for Windows` in Community Plugins.

### Manual

Clone into your vault plugin folder:

```powershell
cd "C:\path\to\your\vault\.obsidian\plugins"
git clone https://github.com/reset980reset980/obsidian-code.git claude-code-win
cd claude-code-win
npm install
npm run build
```

Then enable `Claude Code for Windows` in Obsidian.

## Windows Notes

- The plugin auto-detects Claude CLI on common Windows install paths.
- If detection fails, set `Claude Code CLI path` manually in plugin settings.
- A native installer path such as `C:\Users\<you>\.local\bin\claude.exe` is valid.
- For npm-style installs, use the real CLI entry path, not `claude.cmd`.

## Troubleshooting

### `Claude Code CLI not found`

Run:

```powershell
where.exe claude
```

Then paste the returned path into `Settings -> Claude Code for Windows -> Claude Code CLI path`.

### `401` or `OAuth token has expired`

Your Claude CLI login has expired. Re-authenticate:

```powershell
claude auth login
```

On recent versions of this plugin, you can also launch authentication from the plugin settings.

## Credits

- Original project and base content by [`reallygood83/obsidian-code`](https://github.com/reallygood83/obsidian-code)
- Windows adaptation and fork by [`reset980reset980/obsidian-code`](https://github.com/reset980reset980/obsidian-code)

Thanks to the original author for the plugin this Windows version was adapted from.

## License

[MIT](LICENSE)
