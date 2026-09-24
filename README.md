# Rore collection

Three local tools for developers working with coding agents. Keep the work useful
beyond a single chat: the plan, the checks, and the context for whoever picks it up next.

**[See the tools in action →](https://rore.im/rore-collection/)**

| Tool | What it brings |
|---|---|
| [Minimap](https://github.com/rore/minimap) | Roadmaps in Markdown and spec review alongside the text. |
| [Agent Workflow](https://github.com/rore/agent-workflow) | Risk-aware planning, verification, and review, with a Work Record beside the code. |
| [Pallium](https://github.com/rore/Pallium) | Communication between agent sessions and searchable history from earlier work. |

Together, they support a practical flow: define a feature in Minimap, carry out
its tasks with Agent Workflow, and use Pallium to share findings between sessions
or recover earlier context. Each tool also works independently.

I built these for my own work and am sharing them in the hope they are useful to
others. They are personal projects, still evolving, with rough edges.

## Install with your coding agent

Copy this prompt into your coding agent:

```text
Read https://github.com/rore/rore-collection/blob/main/INSTALL.md and help me install the tools I need.
```

The [installation guide](INSTALL.md) helps your agent ask which tools you want,
follow their official setup instructions, and verify the result.

## Coordinate a larger objective

Ask your agent to read the optional [collection coordination skill](skills/collection-coordination/SKILL.md)
when assignments, dependencies, or handoffs span tasks. The three tools remain
independently useful.
