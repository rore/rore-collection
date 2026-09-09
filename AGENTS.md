# Collection repository instructions

This repository owns the collection README, public one-pager, and collection-level
proposals and guidance. Tool implementation and tool-specific roadmaps remain in
Minimap, Agent Workflow, and Pallium's respective repositories.

## Positioning

- These are personal open-source tools and a showcase of the author's AI engineering
  work, not a commercial product or a promise of a supported unified platform.
- Keep the message short, clear, concrete, and free of repetition. The preferred v2
  one-pager in `docs/index.html` is the starting point; preserve it unless asked to
  revise positioning or design.
- Distinguish implemented behavior from proposed integration. Minimap owns work
  state; Agent Workflow governs task execution; Pallium owns session communication
  and history. A collection coordination skill guides the agent using those tools.
- Do not invent adoption, performance, safety, or productivity claims.

## Working here

- Prefer small edits and existing static HTML/CSS. No build system or dependencies
  without a concrete need. README.md owns the repository overview; docs/index.html
  owns the public landing page; feature files own proposed collection work.
- Preserve unrelated changes. Check links, anchors, and narrow behavior affected by
  an edit. Visually inspect page changes at desktop and mobile widths when possible.
- The user wants roadmap/proposal edits committed and pushed by default. Keep their
  scope clear and verify the actual branch/repository rules before shipping.
- `main` and `docs/` are the GitHub Pages publishing source. Page edits pushed to
  main are public. Keep private data, local transcripts, credentials, and internal
  workplace material out of commits.

## Editing and publishing

Edit the static page in `docs/`. Its images are currently embedded, so it has no
build step or package dependencies. Preview it directly in a browser.

GitHub Pages source: `main`, folder `/docs`. Enable it once in
[Settings > Pages](https://github.com/rore/rore-collection/settings/pages) by choosing
**Deploy from a branch**, **main**, **/docs**, then **Save**. After enabling it,
pushing changes there updates the site. Keep internal discussions, credentials,
and private work artifacts out of the published folder and repository.

Keep the public README focused on the collection and its users. Maintenance
instructions, repository layout notes, and draft-version history belong here.
