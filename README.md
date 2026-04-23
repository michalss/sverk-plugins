# Sverk Plugins

Plugin registry for [Sverk CMS](https://github.com/michalss/sverk-crm).

This repository hosts the `index.json` that Sverk installs read to discover
available plugins. Every plugin ZIP is uploaded as a GitHub Release asset —
releases are the source of truth for downloads, this repo just points to them.

## Use from a Sverk install

1. Open the admin → **Plugins → Settings**.
2. Add the registry URL:
   ```
   https://raw.githubusercontent.com/michalss/sverk-plugins/main/index.json
   ```
3. Switch to the **Marketplace** tab — every plugin listed below is installable with one click, with SHA-256 integrity verification.

## Contributing a plugin

See the [publishing guide](https://github.com/michalss/sverk-crm/blob/main/docs/plugins/registry/publishing.md) in the main repo.

## Bundled plugins

`index.json` is generated from the plugins in [`sverk-crm/plugins/`](https://github.com/michalss/sverk-crm/tree/main/plugins). To regenerate after a plugin changes:

```bash
# In the sverk-crm checkout
npm run plugins:pack -- --base https://github.com/michalss/sverk-plugins/releases/download/<tag>
```

Upload the ZIPs from `dist/plugin-registry/zips/` as a GitHub Release in this repo, then push the updated `index.json`.
