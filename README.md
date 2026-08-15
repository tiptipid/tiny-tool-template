# My Tool

Scaffolded from [`tiptipid/tiny-tool-template`](https://github.com/tiptipid/tiny-tool-template).

## Quickstart

```bash
bun install
bun run dev
```

Build and preview a production build:

```bash
bun run build
bun run preview
```

## Deploy

Cloudflare Pages, on the TipTip Cloudflare account:

```bash
bun run build
bunx wrangler pages deploy --project-name=<your-project-name>
```

## Submit this tool to TinkerBox

1. Fill in `tool.yaml` in this repo with this project's real values.
2. Open a PR against `tiptipid/tiny-tools-market` adding `tools/<slug>.yaml` (copy the filled-in
   `tool.yaml` content — filename must match the `slug` field exactly).
3. `repository_url` must start with `https://github.com/tiptipid/`.
4. A maintainer merges after CI is green — see the full checklist at
   https://tiptip-tiny-tools.pages.dev/guides/submit-your-tool.

## Owner

<Name / team — who to ping if this breaks>
