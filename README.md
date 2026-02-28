# calude-plugins

A collection of [Claude Code](https://code.claude.com) plugins, published as a plugin marketplace.

## Marketplace

This repo is a Claude Code plugin marketplace. Add it to Claude Code with:

```
/plugins marketplace add https://github.com/lou-k/calude-plugins
```

Claude Code will discover all plugins listed in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json).

## Plugins

| Plugin | Description |
|--------|-------------|
| [hello-world](plugins/hello-world/) | A placeholder plugin that greets the user — useful as a starting template. |

## Adding a plugin

1. Create a new directory under `plugins/` named after your plugin (kebab-case).
2. Add a `.claude-plugin/plugin.json` manifest inside it.
3. Add your commands, agents, skills, or hooks.
4. Register the plugin in `.claude-plugin/marketplace.json`.

See the [hello-world](plugins/hello-world/) plugin for an example.
