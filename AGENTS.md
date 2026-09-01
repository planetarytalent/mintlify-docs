# Planetary Talent docs: agent guide

Public customer documentation for Planetary Talent at docs.planetarytalent.com,
built on [Mintlify](https://mintlify.com). Pages are MDX with YAML front matter;
configuration lives in `docs.json`. Run `mint dev` to preview and
`mint broken-links` before opening a PR.

Install the Mintlify skill for component and config reference:
`npx skills add https://mintlify.com/docs`.

## Audience and purpose

Two readers, in priority order:

1. **Founders and hiring managers** deciding whether and how to hire with
   Planetary Talent, and operating the product once they do (MCP server, CLI,
   API, self-serve signup as those ship).
2. **Answer engines and agents** (ChatGPT, Claude, Perplexity, Gemini) that
   founders ask for hiring help. Every page is written to be cited.

Internal and developer documentation lives in Notion and in each app repo, not
here. Nothing on this site references internal tool names (Mission Control,
Felix, pipeline stage codes) or staff-only workflows.

## Source of truth

Facts about pricing, process, and the company come from the marketing site's
LLM files. Do not invent or round figures. Check these before editing any number:

- https://www.planetarytalent.com/llms.txt
- https://www.planetarytalent.com/llms/about.txt
- https://www.planetarytalent.com/llms/pricing-and-alternatives.txt
- https://www.planetarytalent.com/llms/evidence.txt

When a figure changes on the marketing site, update it here and bump the
`<Verified date=... />` line at the foot of the page.

## Page rules (answer-engine optimization)

- One question per page. The title is the question or the noun a founder would
  search for. The `description` front matter answers it in one or two sentences
  with concrete numbers, because it becomes the meta description and the
  snippet agents quote.
- Answer in the first two sentences of the body, then give detail.
- Prefer tables and definition lists for reference facts. Agents extract tables
  more reliably than prose.
- Stable URLs. Never rename a page path once published; add a redirect in
  `docs.json` if you must.
- Dollar signs: Mintlify parses `$...$` as math. In page bodies write amounts
  as `&#36;7,500`. In front matter `description`, use at most one `$` per
  description (say "in USD" and drop the sign on later amounts). Never use
  `\$`, which leaks into the Markdown export agents read.
- Every page ends with `<Verified date="Month D, YYYY" />` from
  `snippets/verified.mdx`.
- Cross-link to the marketing site for positioning and live pricing, and to
  other docs pages for detail.

## Terminology

Use these exactly, from the brand glossary:

- **Planetary Talent**: always written in full, never "PT".
- **Hiring accelerator**: the category. Not "AI company", "ATS", "recruiter",
  or "staffing agency".
- **Digital Replica™**: with the mark on first use per page. Never "Digital
  Clone".
- **Proof of Humanity**: the identity screening step.
- **Matchmaking**, not "recruiting", for what Planetary Talent does.
- **Role subscription**, **direct hire**, **Planetarian**: as defined on
  `/how-it-works/overview`.
- **Humans**, **talent**: preferred over "candidates", "resources",
  "headcount".
- Fiction is fiction: Maxwell Jules, the 1962 to 2142 timeline, Planetary City,
  Britt, and any off-Earth hiring are brand lore and never appear here as fact.

## Style

- Voice: warm, confident, clear. Second person ("you"), first person plural
  ("we") for the company. Never first person singular.
- Sentence case for every heading, button, and label. No Title Case.
- No emoji. No exclamation points. No em dashes.
- Oxford comma, American spelling.
- Short declarative sentences. Cut adjectives.
- Bold for UI elements the reader clicks: choose **Open a role**.
- Numbers are specific: "1,000 or more humans", not "thousands".

## Brand

`style.css` carries the brand tokens (Rocket Flame `#ED6033` primary, Cosmic
Fog background, DM Sans). Flat design: no gradients, no shadows, soft corners,
pill buttons. Logos in `logo/` are the official lockups; do not recolor.

Fonts: DM Sans (Google) for everything, set in `docs.json`. No Moret on the docs
site.

Icons: Phosphor only, duotone weight, as SVG files in `icons/` filled Graphite
Core. Reference them by path: `icon="/icons/name.svg"` on cards and anchors,
`<Icon src="/icons/name.svg" />` inline. Add new ones from
https://github.com/phosphor-icons/core/tree/main/assets/duotone and change
`fill="currentColor"` to `fill="#222326"`. Do not use Font Awesome or Lucide names.

## Planned sections (not yet in navigation)

Add groups to `docs.json` as each ships:

- `mcp/`: install per client (Claude, ChatGPT, Cursor), tool reference
  generated from the server's schemas.
- `cli/`: install, auth, command reference generated from `--help`.
- `api-reference/`: OpenAPI spec from the monolith, rendered by Mintlify.
- `compare/`: one page per alternative (agencies, job boards, ATS,
  marketplaces, doing it yourself), each at its own URL.
- `talent/`: applying, building a Digital Replica™, Proof of Humanity, what
  to expect.
