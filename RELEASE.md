# Release Notes

This file is for maintainers.

## Local Release Build

Use `release.sh` to update `manifest.json` and create a local install zip. The zip contains a `Trailmark` folder with only `manifest.json` and `theme.css`.

```sh
./release.sh -version 0.1.6
```

The local artifact is written to `dist/Trailmark-<version>.zip`.

## Publish a Release

Publishing follows the same release-branch flow as Forge and Lockblock:

```sh
./release.sh -version 0.1.6 -publish true
```

That creates or updates a `release/<version>` branch, commits the manifest version bump, and pushes the branch. Open a PR from `release/<version>` into `main`. When that PR is merged, `.github/workflows/tag-release.yml` creates the matching tag, builds `Trailmark-<version>.zip`, attests it, and publishes the GitHub Release.

Before publishing a release, confirm that the `version` field in `manifest.json` exactly matches the release branch suffix and final tag. Obsidian community themes expect `0.1.6`, not `v0.1.6`.

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
