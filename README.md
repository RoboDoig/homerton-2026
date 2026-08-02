# homerton-2026

Teaching materials for a short Bonsai workshop at Homerton College, Cambridge,
on **4th August 2026**.

The site is built with [docfx](https://dotnet.github.io/docfx/) and published to
GitHub Pages by the [`docs.yml`](.github/workflows/docs.yml) workflow on every
push to `main`.

## Layout

| Path | Contents |
| --- | --- |
| `index.md` | Landing page and workshop schedule. |
| `slides/` | Slides section. Decks themselves are reveal.js pages in `slides/decks/`. |
| `worksheets/` | Hands-on worksheets, plus `template.md` to start new ones. |
| `hobgoblin/` | The Harp Hobgoblin hardware section. |
| `images/` | Figures and workflow screenshots. |
| `workflows/` | Downloadable `.bonsai` workflow files. |
| `template/` | Site-specific CSS overriding the docfx template. |
| `docfx.json` | Build configuration. |

`slides/decks/` is declared as a docfx *resource*, so those HTML files are copied
to the output untouched rather than being processed as content.

## Building locally

```pwsh
dotnet tool update -g docfx
docfx docfx.json --serve
```

Then open <http://localhost:8080>. Use `docfx docfx.json` alone for a one-off
build into `_site/`.

## Enabling GitHub Pages

The deploy workflow needs Pages configured to build from GitHub Actions:
in the repository, go to **Settings → Pages** and set **Source** to
**GitHub Actions**. The first push to `main` then publishes the site.

## Status

The site is a working skeleton — navigation, build and deployment are in place,
and the content is templates. Search for `TODO` and the `[!NOTE]` /
`[!IMPORTANT]` callouts to find everything still to be written; the Hobgoblin
section in particular needs filling in from
[harp-tech/device.hobgoblin](https://github.com/harp-tech/device.hobgoblin).

Modelled on [neurogears/st-andrews-2024](https://github.com/neurogears/st-andrews-2024),
whose NeuroKit section is replaced here by the Hobgoblin section.
