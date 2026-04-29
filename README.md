# Purple LF

This repository is a publish-ready Zed theme extension containing:

- `Purple Dark LF`
- `Purple Light LF`

These themes were converted from the VS Code extension `vertopolkalf.purple-dark-theme-lf`.

## Local testing

1. Open Zed.
2. Run `zed: install dev extension`.
3. Select this folder:

   `C:\Users\leo20\Documents\Codex\2026-04-29\https-marketplace-visualstudio-com-items-itemname\purple-lf-theme`

4. Run `theme selector: toggle` and choose `Purple Dark LF` or `Purple Light LF`.

## Repository layout

- `extension.toml`: Zed extension manifest
- `themes/purple-lf-theme.json`: bundled theme family
- `LICENSE`: accepted license file for Zed extension publishing
- `PUBLISHING.md`: exact publish checklist for Zed's registry flow

## Before publishing

Update these fields in `extension.toml`:

- `authors`
- `repository`

Then create a GitHub repo and push this folder as its contents.

## Publishing

See [PUBLISHING.md](./PUBLISHING.md) for the exact steps to submit this extension to Zed's registry.

## Notes

- Zed uses syntax captures rather than VS Code TextMate scopes, so syntax highlighting is a best-effort translation.
- The original VS Code theme lists the MIT license.
- Attribution details are in `ATTRIBUTION.md`.

## Sources

- Original VS Code theme: <https://marketplace.visualstudio.com/items?itemName=vertopolkalf.purple-dark-theme-lf>
- Zed extension docs: <https://zed.dev/docs/extensions/developing-extensions>
