# attune-gui Plugin

A Claude Code plugin that launches the [attune-gui](https://github.com/Smart-AI-Memory/attune-gui)
living-docs dashboard in the Cowork preview pane with a single skill invocation.

## Requirements

- Claude Code with Cowork (preview pane support)
- [uv](https://docs.astral.sh/uv/) on your PATH
- `attune-gui` installed (`pip install attune-gui`) or the repo cloned locally

## Install

Add the marketplace source to `~/.claude/plugins/known_marketplaces.json`:

```json
"attune-plugins": {
  "source": {
    "source": "github",
    "repo": "Smart-AI-Memory/attune-gui-plugin"
  },
  "installLocation": "~/.claude/plugins/marketplaces/attune-plugins",
  "lastUpdated": "2026-05-02T00:00:00.000Z"
}
```

Then install the plugin:

```
/plugin install attune-gui@attune-plugins
```

## Usage

```
/attune-gui
```

The skill:
1. Detects your attune-gui project path (current directory or `./attune-gui/` subdirectory)
2. Writes `.claude/launch.json` with the correct `uv run` configuration (idempotent)
3. Calls `preview_start` — Cowork starts the sidecar and opens the dashboard in the preview pane

## License

Apache-2.0
