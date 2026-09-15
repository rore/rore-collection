# Collection coordination queue

This note preserves cross-tool sequencing and handoff state. Canonical feature and
execution status remains in each tool's linked roadmap item or Work Record. This is
not a scheduler, task registry, ownership record, or availability signal.

## Queue

| # | State | Work and canonical references | Owner | Next action | Depends on |
|---|---|---|---|---|---|
| 1 | **Active — bounded residuals** | Pallium Relay reliability: [wake-first Relay](https://github.com/rore/Pallium/blob/main/roadmap/features/add-wake-first-relay-delivery.md) and [residual acceptance](https://github.com/rore/Pallium/blob/main/.agent-workflow/tasks/relay-residual-acceptance.md). Collision diagnostics ([PR #186](https://github.com/rore/Pallium/pull/186)), readiness warnings ([PR #188](https://github.com/rore/Pallium/pull/188)), MCP recovery guidance ([PR #189](https://github.com/rore/Pallium/pull/189)), correlated wake-timeout recovery ([PR #198](https://github.com/rore/Pallium/pull/198)), and bounded manager-side acceptance ([PR #200](https://github.com/rore/Pallium/pull/200)) are shipped. | `relaydev` owns fresh post-fix Pallium regressions and remaining platform qualification. Exact recipient/task operators own natural-turn consumption; explicit user/product decisions own historical disposition. | Keep recent backlog with exact recipients; explicitly resume or disposition dormant active-health rows and decide dormant unreachable or collision rows without blind retargeting. Complete interruption/restart, macOS, and OpenCode qualification in the linked roadmap. Reopen wake-timeout diagnosis only on fresh correlated evidence. | None. |
| 2 | **Open — validation incomplete** | Validate all eight optional Pallium/Minimap/Agent Workflow combinations. Agent Workflow's resolver shipped in [PR #28](https://github.com/rore/agent-workflow/pull/28); Pallium's [combined coordination Work Record](https://github.com/rore/Pallium/blob/main/.agent-workflow/tasks/combined-ref-association-discovery.md) still records the resolver as open and needs reconciliation. The trusted Pallium exact scoped adapter for custom/resumed Work Records remains open. | Unassigned. | Reconcile the stale Work Record, implement the smallest trusted scoped adapter, then run the eight-combination matrix without making any tool mandatory. | 1. |
| 3 | **Proposed — paused** | Package the collection coordination skill and run its bounded trial from the approved [coordination recipe](feature-coordination-recipe.md). | Unassigned. | Start only after communication is reliable and combined instruction behavior is verified. | 1, 2. |
| 4 | **Prepared — unmerged** | Optional Minimap/Pallium participation installation guidance is prepared as commit `b7a20de`; current public source is [INSTALL.md](INSTALL.md). | Unassigned. | Integrate the prepared change after combined verification confirms the documented behavior. | 2. |
| 5 | **Queued** | Broader [Session History search improvement](https://github.com/rore/Pallium/blob/main/roadmap/features/improve-session-history-search-quality.md). Response-local navigation shipped; broader search-quality work remains. | Unassigned; no active next-slice owner. | Select the smallest evidence-backed search slice without repeating completed diagnostics. | Schedule after 1. |
| 6 | **Queued report** | WSL/native-Windows worktree-wrapper compatibility evidence remains a separate report from Agent Workflow's merged [guidance PR #29](https://github.com/rore/agent-workflow/pull/29) and [runtime-parity Work Record](https://github.com/rore/agent-workflow/blob/main/.agent-workflow/tasks/runtime-parity.md). | Unassigned. | Publish a concise compatibility report; do not reopen or duplicate the merged guidance change. | Public-safe evidence review. |
| 7 | **Proposed — incomplete** | Repeatable usability/process-feedback wording should build on Agent Workflow's [field-feedback contract](https://github.com/rore/agent-workflow/blob/main/.agent-workflow/tasks/field-feedback-contract.md) and Pallium's [upstream-feedback Work Record](https://github.com/rore/Pallium/blob/main/.agent-workflow/tasks/upstream-field-feedback-loop.md). | Unassigned. | Align the smallest common wording across the three tools without expanding normally loaded context. | Schedule after 1. |
| 8 | **Evidence only** | Host approval/review friction has supporting observations but is not a proven collection defect and has no public feature record. | Unassigned. | Retain public-safe evidence; report upstream only after the behavior is repeatable, pointable, and owned by that upstream product. | Additional evidence. |
| 9 | **Cleanup pending** | A completed recipe-review association could not be detached because the supported Pallium MCP operation was unavailable. See the [work-association contract](https://github.com/rore/Pallium/blob/main/docs/agent-relay.md#associate-sessions-with-exact-work). | Collection coordinator. | When the supported detach operation is available, remove only that explicit finished-work association. Do not use HTTP or shell fallback. | 1. |

## Shipped anchors

These are stable foundations, not evidence that the unfinished queue above is done:

- Minimap participant links: [v0.3.3](https://github.com/rore/minimap/releases/tag/v0.3.3) and [PR #17](https://github.com/rore/minimap/pull/17).
- Pallium work-item deep links: [PR #184](https://github.com/rore/Pallium/pull/184).
- Pallium endpoint-collision diagnostics: [PR #186](https://github.com/rore/Pallium/pull/186).
- Agent Workflow Work Record resolver: [PR #28](https://github.com/rore/agent-workflow/pull/28).
- Agent Workflow receiver-readiness and targeted-review guidance: [PR #29](https://github.com/rore/agent-workflow/pull/29).
- Collection coordination proposal: [commit `55c1428`](https://github.com/rore/rore-collection/commit/55c1428bb2a9736533a09fb9e886b6f5fe72bacc).

Update this note only when a linked canonical record changes the cross-tool order,
owner, dependency, or next action. Do not copy tool-local implementation detail here.
