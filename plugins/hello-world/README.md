# hello-world

A placeholder Claude Code plugin — useful as a starting template for building your own plugins.

## What it does

Provides a single `/hello` slash command that greets the user by name.

## Installation

Add this plugin via the marketplace:

```
/plugins install https://github.com/lou-k/calude-plugins
```

Or install directly from the plugin source:

```
/plugins install https://github.com/lou-k/calude-plugins/tree/main/plugins/hello-world
```

## Commands

| Command | Description |
|---------|-------------|
| `/hello [name]` | Greet the user. Optionally pass a name (default: "World"). |

## Usage

```
/hello
```
→ Hello, World! 👋

```
/hello Claude
```
→ Hello, Claude! 👋

## License

MIT
