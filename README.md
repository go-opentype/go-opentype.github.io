# go-opentype landing

Hugo source for **<https://go-opentype.github.io/>** — the landing
page of the [`go-opentype`](https://github.com/go-opentype) org.

Preview locally:

```
hugo server
```

Build:

```
hugo --minify
```

The rendered site lives under `public/` (gitignored except when
GitHub Pages is deployed from that directory — see the workflow
under `.github/workflows/deploy-pages.yml`).

Layout is a single-page card grid: header + hero + tagline + pills +
a `.grid` of repo cards driven by `hugo.toml`'s `params.repos` list.
Adding a new sibling repo means adding one `[[params.repos]]` block
to `hugo.toml` and re-running `hugo --minify`.

## License

BSD-3-Clause.

## The design is not here

It comes from the shared Hugo module
[`go-fleettools/landingkit`](https://github.com/go-fleettools/landingkit),
pinned in `go.mod` (Renovate bumps it); `kit.go` keeps `go mod tidy` from
deleting that requirement. `[params.brand]` in `hugo.toml` is read from the logo by
`landingkit brand`. A file under `layouts/partials/` with the name of one of the
kit's would silently override it.
