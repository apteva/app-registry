# Apteva App Registry

Curated registry of [Apteva Apps](https://github.com/apteva/app-sdk).
The dashboard's **Marketplace** view fetches `registry.json` from this
repo's `main` branch and renders one card per entry.

## Adding an app

Open a PR adding a new entry to `apps[]`. Required fields:

- `name` — the manifest's `name` (slug, must match the deployed image)
- `display_name`, `version`, `description`
- `author`
- `repo` — public git URL
- `manifest_url` — the raw URL to `apteva.yaml` in the repo's main branch
- `icon` — square PNG/SVG, 256×256 ideal
- `tags` — discovery hints
- `category` — one of `productivity`, `observability`, `channels`, `tools`, `workflow`, `media`, `other`

Optional:

- `official` — set `true` only on entries the Apteva core team maintains

## Schema

`registry.json` is `apteva-registry/v1`. Breaking changes bump the
schema; the dashboard validates on load.

## Self-hosting a registry

The dashboard's marketplace URL is configurable in Settings → Server.
Point it at your own `registry.json` to ship a private catalogue.
