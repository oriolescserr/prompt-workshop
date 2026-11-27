# Check the host's plugins

The plugins that count are those of **the host that will run the prompt**, on this machine, not those of the session writing it.

Look them up fresh every time. Do not save a list or notes, and do not rely on one from earlier work.

## List what is enabled

List the enabled plugins for this run: global, plus the target project when there is one. Ignore marketplace entries that are not installed.

- **Claude Code.** From the target project directory, or the current one when there is no project, run `claude plugin list --json`. Keep rows with `enabled: true`. `user` is global; `project` and `local` are that repo; `skills-dir` and `synced` count. If the command fails, read `enabledPlugins` in `~/.claude/settings.json`, `<project>/.claude/settings.json`, and `<project>/.claude/settings.local.json`. A later file overrides the same id. Install paths are in `~/.claude/plugins/installed_plugins.json`.
- **Cursor.** Read `plugin.json` name and description under `~/.cursor/plugins`, and skill descriptions in the target project's `.cursor/skills`. User skills Cursor loads count as global.
- **Codex.** Read `~/.codex/plugins` and `~/.codex/skills`, plus plugin config in the target project. Do not invent a list command.
- **Any other host.** Search that product's config and plugin folders. If you cannot find them, ask. Do not guess a path.

## Pick the ones that help

Go by names and descriptions. For each plugin or skill that might cover part of the task, read its manifest and skill descriptions before deciding. Take what it does from those texts, not from its name.

## Use them in the prompt

If a plugin covers part of the task, name it in the prompt and tell the model to use it. Do not copy its steps into the prompt. Leave other plugins out. When the prompt depends on a plugin, say so next to where to paste it.
