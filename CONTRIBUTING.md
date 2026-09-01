# Contribute to the docs

1. Read `AGENTS.md` for audience, terminology, style, and the source-of-truth
   rules. Numbers come from the marketing site's `llms` files, never from
   memory.
2. Branch from `main`, edit or add MDX pages, and add new pages to
   `docs.json` navigation.
3. Run `mint dev` to preview and `mint broken-links` to check links.
4. Update the `<Verified date=... />` line on any page whose facts you touched.
5. Open a pull request. Merging to `main` deploys.

Commit messages follow `type: short description` in lowercase
(`docs: add cli install page`).
