# Trailmark

Trailmark is an Obsidian theme built from a restrained outdoor-industrial palette with focused dark and light mode styling.

Repository: <https://github.com/joshua-walls/trailmark-theme>

## Install manually

1. Download the latest release zip.
2. Unzip it into your vault's `.obsidian/themes/` folder.
3. In Obsidian, open Settings, then Appearance, then Themes.
4. Select `Trailmark`.

The installed folder should contain:

```text
Trailmark/
  manifest.json
  theme.css
```

## Package a release

Releases are packaged by GitHub Actions when a version tag is pushed. The workflow creates a folder named `Trailmark` containing only `manifest.json` and `theme.css`, then uploads `Trailmark-<version>.zip` to the GitHub Release.

```sh
git tag 0.1.1
git push origin 0.1.1
```

Before publishing a release, confirm that the `version` field in `manifest.json` exactly matches the Git tag. Obsidian community themes expect `0.1.0`, not `v0.1.0`.

## Submit to Obsidian community themes

For wider distribution, host this as a public GitHub repository, create a tagged release, then submit the repository to `obsidianmd/obsidian-releases` as a community CSS theme.

The theme repository should keep `manifest.json`, `theme.css`, and this README at the repository root.

Suggested entry for `community-css-themes.json`:

```json
{
  "name": "Trailmark",
  "author": "Joshua Walls",
  "repo": "joshua-walls/trailmark-theme",
  "screenshot": "screenshot.png",
  "modes": ["dark", "light"]
}
```
