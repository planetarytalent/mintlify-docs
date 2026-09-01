# Planetary Talent docs

Public documentation for Planetary Talent, served at docs.planetarytalent.com.
Built on [Mintlify](https://mintlify.com), deployed from `main`.

Audience: founders and hiring managers, and the answer engines and agents they
ask for hiring help. Internal and developer docs live in Notion and in each app
repo, not here.

## Develop

```bash
npm i -g mint
mint dev            # preview at http://localhost:3000
mint broken-links   # check before opening a PR
```

Pages are MDX files with front matter. Navigation and site config are in
`docs.json`. Read `AGENTS.md` for terminology, style, and the source-of-truth
rules before writing a page.

## Layout

```
index.mdx                       Home
getting-started/open-a-role     Tutorial: open a role through to hire
how-it-works/overview           The seven-step process, timing, terminology
how-it-works/search-tiers       Pricing, guarantees, role subscriptions, fit
snippets/verified.mdx           "Last verified" footer used on every page
logo/, favicon.svg              Official lockups from the brand system
```

Planned sections (MCP server, CLI, API reference, comparisons, talent) are
listed in `AGENTS.md`.

## Deploy

Connect this repo in the Mintlify dashboard and set the custom domain to
`docs.planetarytalent.com`. Mintlify publishes `/llms.txt` and
`/llms-full.txt` automatically. After the first deploy, add the docs URL to the
marketing site's `llms.txt` so agents can find it from planetarytalent.com.
