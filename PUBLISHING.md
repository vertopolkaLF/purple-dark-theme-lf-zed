# Publishing Checklist

This repository is structured for Zed's current extension publishing flow.

## 1. Confirm manifest metadata

Current manifest values already follow the main Zed naming guidance:

- extension id does not contain `zed`, `Zed`, or `extension`
- extension id ends with `-theme`
- this repository contains only a theme extension

## 2. Push this repo to GitHub

Current repository:

- `https://github.com/vertopolkaLF/purple-lf-theme-zed.git`

Push this folder if needed:

```powershell
cd C:\Dev\purple-dark-theme-lf
git add .
git commit -m "Prepare Purple Dark Theme for Zed publishing"
git branch -M main
git remote add origin https://github.com/vertopolkaLF/purple-lf-theme-zed.git
git push -u origin main
```

## 3. Test it locally in Zed

In Zed:

1. Run `zed: install dev extension`
2. Select this repository folder
3. Run `zed: reload extensions` after changes
4. Confirm both `Purple Dark` and `Purple Light` work correctly

## 4. Submit to `zed-industries/extensions`

According to Zed's docs, the publish flow is:

1. Fork and clone `https://github.com/zed-industries/extensions`
2. Add your extension as a submodule under `extensions/purple-dark-theme`
3. Add an entry to the top-level `extensions.toml`
4. Run `pnpm sort-extensions`
5. Open a pull request

Example commands:

```powershell
git submodule add https://github.com/vertopolkaLF/purple-lf-theme-zed.git extensions/purple-dark-theme
git add extensions/purple-dark-theme
```

Example `extensions.toml` entry:

```toml
[purple-dark-theme]
submodule = "extensions/purple-dark-theme"
version = "1.1.3"
```

## 5. PR notes

Mention in the PR that:

- this is a theme-only extension
- the license is MIT
- you tested it locally as a Zed dev extension
