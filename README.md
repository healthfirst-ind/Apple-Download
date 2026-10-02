# Apple-Client downloads

Public download surface for **IndiaMart Automation Tool** on macOS.

This repository intentionally contains no application code. The build is produced from
the private source repository [`healthfirst-ind/Apple-Client`](https://github.com/healthfirst-ind/Apple-Client)
and published here as a GitHub Release.

- **Releases:** https://github.com/healthfirst-ind/Apple-Download/releases
- **Supported hardware:** Apple Silicon (arm64)

## How a release is made

Push a `v*` tag, or run the **Release Mac** workflow manually from the Actions tab:

```bash
# in the Apple-Client checkout
git tag v1.0.0
git push origin v1.0.0
```

The workflow resolves the source, builds an ad-hoc signed `.dmg`, and publishes it as a
release on this repo. `package.json`'s `version` is rewritten to match the tag at build
time, so the tag is the single source of truth for the shipped version number.

## Required repository secret

`SOURCE_TOKEN` — a classic PAT with `repo` scope, or a fine-grained token with
**Contents: read** access to `healthfirst-ind/Apple-Client`. The workflow's built-in
`GITHUB_TOKEN` is scoped to this repo and cannot read the private source repo.

Add it under: **Settings → Secrets and variables → Actions → New repository secret**

## Signing status

Builds are ad-hoc signed and **not notarized** (no Apple Developer ID). This prevents the
"app is damaged" failure, but Gatekeeper still shows a one-time first-launch prompt. On
macOS 15/26 that prompt is cleared in **System Settings → Privacy & Security → Open
Anyway**; Apple removed the older right-click → Open shortcut. See the release notes
for the full steps. Only a paid Apple Developer ID + notarization removes the prompt
entirely.
