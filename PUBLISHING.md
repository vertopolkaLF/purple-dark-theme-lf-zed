# Publishing Checklist

This repository is structured for Zed's current extension publishing flow.

## 1. Finalize manifest metadata

Edit `extension.toml` and replace:

- `authors = ["Your Name <you@example.com>"]`
- `repository = "https://github.com/your-github-username/purple-lf-theme"`

Current manifest values already follow the main Zed naming guidance:

- extension id does not contain `zed`, `Zed`, or `extension`
- extension id ends with `-theme`
- this repository contains only a theme extension

## 2. Push this repo to GitHub

Create a GitHub repository and push this folder:

```powershell
cd C:\Users\leo20\Documents\Codex\2026-04-29\https-marketplace-visualstudio-com-items-itemname\purple-lf-theme
git add .
git commit -m "Prepare Purple LF theme for Zed publishing"
git branch -M main
git remote add origin https://github.com/your-github-username/purple-lf-theme.git
git push -u origin main
```

## 3. Test it locally in Zed

In Zed:

1. Run `zed: install dev extension`
2. Select this repository folder
3. Run `zed: reload extensions` after changes
4. Confirm both `Purple Dark LF` and `Purple Light LF` work correctly

## 4. Submit to `zed-industries/extensions`

According to Zed's docs, the publish flow is:

1. Fork and clone `https://github.com/zed-industries/extensions`
2. Add your extension as a submodule under `extensions/purple-lf-theme`
3. Add an entry to the top-level `extensions.toml`
4. Run `pnpm sort-extensions`
5. Open a pull request

Example commands:

```powershell
git submodule add https://github.com/your-github-username/purple-lf-theme.git extensions/purple-lf-theme
git add extensions/purple-lf-theme
```

Example `extensions.toml` entry:

```toml
[purple-lf-theme]
submodule = "extensions/purple-lf-theme"
version = "0.1.0"
```

## 5. PR notes

Mention in the PR that:

- this is a theme-only extension
- it is a conversion of `vertopolkalf.purple-dark-theme-lf`
- the license is MIT
- you tested it locally as a Zed dev extension
