# scoop-kandev

A [Scoop](https://scoop.sh) bucket for [kandev](https://github.com/kdlbs/kandev) — manage tasks, orchestrate agents, review changes, and ship value.

## Install

```powershell
scoop bucket add kandev https://github.com/kdlbs/scoop-kandev
scoop install kandev
```

Then run `kandev` to start.

## Update

```powershell
scoop update kandev
```

## What gets installed

The kandev CLI bundle, from the official release asset `kandev-windows-x64.tar.gz`. The package creates a single shim, `kandev`, and sets `KANDEV_BUNDLE_DIR` and `KANDEV_VERSION` so the launcher can locate its runtime. The bundled `agentctl` and its remote helpers are installed but deliberately not shimmed.

Node.js is not required to install or launch kandev. It is required for the agent CLIs that kandev installs through its own UI.

## Updating on a new release

Three fields change: `version`, the `url` and the `hash`. The hash is the one already published as `kandev-windows-x64.tar.gz.sha256` next to the release asset, so there is nothing to compute.

The `checkver` and `autoupdate` blocks in the manifest are there so this doesn't have to be hand-edited — Scoop's checkver tooling reads the newest kandev release, rewrites the URL for it and pulls the hash from the published `.sha256`.

## License

kandev is AGPL-3.0-only. See the [upstream repository](https://github.com/kdlbs/kandev) for the full text.
