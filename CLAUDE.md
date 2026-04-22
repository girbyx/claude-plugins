# girbyx Claude Code Plugin Marketplace

Personal plugin marketplace consumed via `/plugin marketplace add girbyx/claude-plugins` in Claude Code.

## Repo Layout

```
.claude-plugin/marketplace.json   Single source of truth — the plugin index
README.md                         Human-readable listing
```

## Adding a Plugin

1. Add an entry to the `plugins` array in `marketplace.json`:
   ```json
   {
     "name": "plugin-name",
     "source": { "source": "github", "repo": "girbyx/plugin-name" },
     "description": "...",
     "version": "1.0.0",
     "author": { "name": "girbyx", "url": "https://github.com/girbyx" },
     "homepage": "https://github.com/girbyx/plugin-name",
     "repository": "https://github.com/girbyx/plugin-name",
     "license": "MIT",
     "keywords": ["..."]
   }
   ```
2. Add a row to the "Available plugins" table in `README.md`.

## Updating a Plugin Version

Bump the `"version"` field in the plugin's entry in `marketplace.json`. Users pull the update via `/plugin marketplace update girbyx` — updating the marketplace propagates the new plugin version.

## PR Process

Fork → branch → PR to `master`. Don't add plugins you don't own or maintain.
