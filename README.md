# My First Claude Project

Notes from my first day exploring Claude Code.

## What I learned today

### Claude Code basics
- Claude Code is Anthropic's official coding agent — available as a CLI, desktop app, web app, and IDE extensions.
- It can read, write, and edit files; run shell commands; search codebases; and integrate with git and GitHub.
- You interact with it conversationally: it proposes changes, executes tools, and you can review the results.

### The `.claude` config folder
- Claude Code stores its config in `C:\Users\yotamtr\.claude\` on Windows.
- It's a *hidden* dot-folder, so File Explorer won't show it by default — enable **View → Show → Hidden items**.
- Key contents:
  - `settings.json` — global settings (permissions, env vars, hooks)
  - `.credentials.json` — auth tokens (**never commit this**)
  - `projects/` — full transcripts of past conversations
  - `backups/` — periodic backups of the global config
  - `sessions/`, `shell-snapshots/` — session and shell state
  - `plugins/` — custom plugins and the blocklist

### Customization surfaces
- **Hooks** — shell commands triggered on events (e.g. on stop, on tool use)
- **Slash commands / skills** — reusable workflows you can invoke with `/name`
- **MCP servers** — connect external tools (Figma, Slack, Gmail, etc.)
- **Subagents** — specialized agents for focused tasks (Explore, Plan, etc.)

### Git & safety lessons
- Don't `git init` inside your `.claude` folder — it contains credentials and full conversation transcripts.
- Anything pushed to GitHub should be considered permanently leaked, even if you delete the repo afterward.
- Always exclude `.credentials.json`, `.env`, and similar files from commits.

## Next steps
- Set up a real `settings.json` with permission allowlists and hooks
- Build my first custom slash command
- Clean up old backups and shell snapshots
