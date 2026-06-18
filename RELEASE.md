# Release Notes

This file is for maintainers.

## Package a Release

Releases are packaged by GitHub Actions when a version tag is pushed. The workflow creates a folder named `Trailmark` containing only `manifest.json` and `theme.css`, then uploads `Trailmark-<version>.zip` to the GitHub Release.

```sh
git tag 0.1.2
git push origin 0.1.2
```

Before publishing a release, confirm that the `version` field in `manifest.json` exactly matches the Git tag. Obsidian community themes expect `0.1.2`, not `v0.1.2`.

## Obsidian Community Theme Entry

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
