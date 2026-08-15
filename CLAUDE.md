# CLAUDE.md

Starter scaffold from `tiptipid/tiny-tool-template`. This file carries the stable TipTip
conventions that don't change tool-to-tool. For current stack *preferences* — language,
deployment target, auth, database, the things that legitimately shift over time — read them
fresh from TinkerBox's Golden Path (linked below) rather than trusting this file's memory of them.

## Locked stack (do not substitute without a reason)

| Concern | Required choice |
|---|---|
| App framework | SvelteKit 2 + Svelte 5 + TypeScript |
| Package manager / test runner | Bun (`bun install`, `bun run`, `bun test`) |
| Hosting | Cloudflare Pages + `@sveltejs/adapter-cloudflare`, on the TipTip Cloudflare account |
| Repo hosting | `github.com/tiptipid/<slug>` — every TipTip tool repo lives under the `tiptipid` org |
| Auth (only if this tool needs it) | Supabase Auth + Google OAuth (`@supabase/ssr`) |

Env names (exact — only add these if this tool actually uses Supabase):

```bash
PUBLIC_SUPABASE_URL=
PUBLIC_SUPABASE_ANON_KEY=
```

Don't provision a Supabase project or these env vars unless the tool needs auth or a database.
Most TipTip experiments don't.

## Deploy

Cloudflare Pages, on the TipTip Cloudflare account, via `@sveltejs/adapter-cloudflare`:

```bash
bun run build
bunx wrangler pages deploy --project-name=<your-project-name>
```

## Where the rest of the Golden Path lives

This file deliberately does not vendor TipTip's current stack *preferences* — that's TinkerBox's
job to keep current, not this template's job to freeze in place:

- Golden Path (preferences: language, deployment, auth, database): https://tiptip-tiny-tools.pages.dev/golden-path
- Guides (submit a tool, launch standards, get access): https://tiptip-tiny-tools.pages.dev/guides
- Claude Code MCP guide (internal GitLab): https://gitlab.com/tiptiptv/common/aiad-claude/-/blob/main/guides/claude_code_mcp_guide.md?ref_type=heads
- Claude Code skills list (internal GitLab): https://gitlab.com/tiptiptv/common/aiad-claude/-/blob/main/guides/claude_code_skills_list.md?ref_type=heads

## Before you ship

- [ ] Repo lives under `github.com/tiptipid/`
- [ ] `bun test`, `bun run check`, `bun run build` all pass
- [ ] `tool.yaml` in this repo is filled in and copied into a PR against TinkerBox's `tools/`
      directory — see README.md
