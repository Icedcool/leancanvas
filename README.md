# Lean Canvas

A light, single-page Lean Canvas you can fill out fast, then export to **Markdown** or a
**Product Requirements Document (PRD)**. No build step, no dependencies, no account — it's
one self-contained `index.html`.

## Features

- All nine Lean Canvas blocks plus the sub-fields **Existing Alternatives**,
  **High-Level Concept**, and **Early Adopters**.
- **Auto-save** to your browser's `localStorage` — refreshing never loses your work.
- **Download Markdown** — the filled canvas as a clean `.md` file.
- **Download PRD** — a deterministic mapping of the canvas into a 10-section PRD, with any
  blank blocks surfaced under *Open Questions*.
- **Copy Markdown** to the clipboard, and **Reset** to start over.
- Print / save-as-PDF friendly (`Cmd/Ctrl + P`).

## Run locally

Just open the file — no server needed:

```sh
open index.html
```

Or serve it (handy for testing on a phone on your network):

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to Vercel

`index.html` sits at the repository root, so it deploys as a static site with **no
configuration**:

- Import the repo at [vercel.com/new](https://vercel.com/new), or
- run `vercel` from this directory.

## Later: turning it into an app

The UI is driven entirely by the `SCHEMA` array in `index.html`. Each block (key, title,
help text, placeholder, optional sub-field) is one entry, and the same array feeds both the
layout and the export builders — so migrating into React/Vue later is mostly a matter of
lifting `SCHEMA` and the `buildMarkdown` / `buildPRD` functions into components.
