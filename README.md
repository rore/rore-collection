# Rore collection

Local tools for developers working with coding agents, built by Rotem Hermon.
These are personal open-source projects, shared as working examples of how I build
and use AI tooling. Each tool can be used independently.

[Explore the collection](https://rore.github.io/rore-collection/)

| Tool | What it does |
|---|---|
| [Minimap](https://github.com/rore/minimap) | Keeps roadmaps and spec review beside repository files. |
| [Agent Workflow](https://github.com/rore/agent-workflow) | Guides engineering tasks through risk assessment, planning, verification, and review, with durable Work Records. |
| [Pallium](https://github.com/rore/Pallium) | Connects agent sessions through Relay and makes earlier sessions searchable. |

Use each tool's repository for installation, supported runtimes, and current behavior.
The collection does not have a combined installer or an orchestration runtime.

## This repository

- `docs/index.html`: the collection one-pager, served by GitHub Pages.
- `AGENTS.md`: instructions for agents working on this repository.
- `feature-coordination-recipe.md`: proposed collection-level coordination skill.

The initial one-pager preserves the preferred v2 positioning artifact. Planned
integrations and the coordination recipe are proposals, not shipped capabilities.

## Editing and publishing

Edit the static page in `docs/`. Its images are currently embedded, so it has no
build step or package dependencies. Preview it directly in a browser.

GitHub Pages publishes the `docs/` folder on `main`. Pushing changes there updates
the site. Keep internal discussions, credentials, and private work artifacts out
of the published folder and repository.
