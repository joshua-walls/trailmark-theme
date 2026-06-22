# Release Notes

This file is for maintainers.

## Local Build

Local helper scripts may create a release zip in `dist/`, but they are not part of the repository. The install zip should contain a `Trailmark` folder with only `manifest.json` and `theme.css`.

Before building a local artifact, update `manifest.json` to the target version.

## Publish a Release

Publishing follows the same release-branch flow as Forge and Lockblock.

```sh
git switch -c release/0.1.6
git add manifest.json theme.css RELEASE.md .github/workflows
git commit -m "release: v0.1.6"
git push -u origin release/0.1.6
```

Open a PR from `release/<version>` into `main`. When that PR is merged, `.github/workflows/tag-release.yml` creates the matching tag, builds `Trailmark-<version>.zip`, attests it, and publishes the GitHub Release.

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
