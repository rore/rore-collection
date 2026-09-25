# Collection coordination queue

This note preserves cross-tool sequencing and collection-owned commitments. Tool-local
status and owners remain in the linked roadmap items or Work Records. This is not a
scheduler, task registry, ownership record, or availability signal.

## Queue

| Work | Remaining action | Dependency or canonical home |
|---|---|---|
| Optional-tool combinations | Validate all eight Pallium/Minimap/Agent Workflow combinations in the [coordination recipe](feature-coordination-recipe.md), without making any tool mandatory. | Reconcile Pallium's [combined Work Record](https://github.com/rore/Pallium/blob/main/.agent-workflow/tasks/combined-ref-association-discovery.md) with Agent Workflow's shipped [resolver](https://github.com/rore/agent-workflow/pull/28), then settle the trusted exact-scope adapter. Pallium [Relay qualification](https://github.com/rore/Pallium/blob/main/roadmap/features/add-wake-first-relay-delivery.md) applies where wake is exercised. |
| Coordination trial | Use the shipped [skill](../skills/collection-coordination/SKILL.md) and [recipe](feature-coordination-recipe.md) to collect real handoff and combined-trial evidence. Reuse the recorded two-tool lifecycle result; do not count it as the whole matrix. | Participant board badges are optional; broader combination validation is above. |
| Installation guidance | Integrate prepared commit `b7a20de` into [INSTALL.md](../INSTALL.md) only after combined verification supports its optional Minimap/Pallium participation claims. | Optional-tool combinations. |
| Compatibility report awaiting placement | Preserve the separate WSL/native-Windows worktree-wrapper report until its owner records it canonically; do not reopen Agent Workflow's merged [guidance PR #29](https://github.com/rore/agent-workflow/pull/29). | Ask the Agent Workflow owner for a canonical issue or report if repo-owned; the existing [runtime-parity Work Record](https://github.com/rore/agent-workflow/blob/main/.agent-workflow/tasks/runtime-parity.md) does not track this report. |
| Finished association cleanup | Detach only the coordinator's explicit completed recipe-review association through the supported [Pallium operation](https://github.com/rore/Pallium/blob/main/docs/agent-relay.md#associate-sessions-with-exact-work), after confirming its exact reference. | One-time cleanup; no HTTP or shell fallback. |

Update this note only when a linked canonical record changes a cross-tool dependency
or collection next action. Do not copy tool-local implementation detail here.
