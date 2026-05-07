# Session Notes — 2026-05-07

A summary of everything we did in my first Claude Code session.

## 1. Explored the `.claude` config folder
- Listed the contents of `C:\Users\yotamtr\.claude\` and learned what each subfolder is for (`settings.json`, `.credentials.json`, `projects/`, `backups/`, `sessions/`, `shell-snapshots/`, `plugins/`).
- Realized it's a *hidden* dot-folder — Windows File Explorer hides it by default. Enable **View → Show → Hidden items** to see it.

## 2. Created a first notes file
- Wrote a short summary of Claude Code into `.claude\my-notes.md`.
- Got a code review on it: the intro was redundant ("CLI" + "from the terminal"), "Where it runs" contradicted the CLI-only framing, and the doc was missing the actual interaction model.

## 3. Got 3 suggestions for organizing `.claude`
- Set up a real `settings.json` (currently `{}`) with permission allowlists and hooks.
- Build a personal slash command or skill — highest-leverage Claude Code customization.
- Clean up old `backups/` and `shell-snapshots/`, ideally with a scheduled prune task.

## 4. Almost made a serious mistake
- Asked Claude to `git init` and push `.claude` to GitHub.
- Claude refused — that folder contains credentials, full conversation transcripts, and MCP auth state. **Anything pushed to GitHub should be considered permanently leaked**, even if the repo is later deleted.

## 5. Created the real project
- New folder: `C:\Users\yotamtr\Documents\my-first-claude-project\`
- Wrote a `README.md` with what I learned.
- `git init -b main`, committed README.

## 6. Wrestled with GitHub CLI
- Confused GitHub Desktop (GUI app) with GitHub CLI (`gh`) — they're different tools.
- Installed `gh` via `winget install --id GitHub.cli`, but PATH didn't refresh in the running terminal.
- `gh auth login` flow didn't complete cleanly — no auth config file on disk despite multiple attempts.

## 7. Switched to plain `git`
- Created the repo manually at https://github.com/new (private, empty — no README/gitignore).
- Added the remote: `git remote add origin https://github.com/yotamtr-collab/my-first-claude-project.git`
- `git push -u origin main` — succeeded on the first try (Git Credential Manager handled auth).
- Repo is live at https://github.com/yotamtr-collab/my-first-claude-project

## Takeaways
- **Audit before you commit.** Hidden folders often hold secrets.
- **Restart your terminal after installing CLI tools** so PATH is current.
- **Plain git + manual repo creation** is a perfectly fine fallback when `gh` is being uncooperative.
- **Claude Code can plan, edit, run shell commands, and push to GitHub** — but checks in on irreversible actions before doing them.
