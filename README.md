# go1.21

> **⚠️ ARCHIVED: This repository has been retired**
> 
> Go 1.21 reached End of Life and is no longer receiving updates.
> 
> - **No new builds** will be published
> - **Existing packages** remain available in the APT repository
> - **Security updates** are no longer provided
> - **For current versions**, see: https://github.com/Dockershelf/dockershelf-pipeline
> 
> Retired: 2026-07-07

Debian packaging for Go 1.21: compiles the Go toolchain from the official [golang/go](https://github.com/golang/go) source tree into `golang-1.21-go` packages for enterprise `.deb`-only installs.

## Supported Debian suites

- `trixie`
- `unstable`

Packaging trees live under `debiandirs/<suite>/`. Changelog tracks:

- **mainline** — `changelogs/mainline/<suite>`

## Build (from workspace)

Clone or seed this repo as a sibling of `go-pipeline/`, then from `go-pipeline/`:

```bash
make materialize GO=1.21 DIST=trixie
make build GO=1.21
```

## Layout

| Path | Purpose |
|------|---------|
| `go/` | Go source tree (git submodule from golang/go, `release-branch.go1.21` branch) |
| `patches/` | Quilt series (applied via `gbp pq`) |
| `debiandirs/` | Per-suite Debian packaging (`trixie`, `unstable`) |
| `changelogs/` | `mainline` dch history per suite |
| `.github/workflows/main.yml` | Caller workflow for scheduled CI (seeded per minor line) |
