---
id: feature-related-work
title: Connect features to their Work Records and pull requests
status: planned
priority: medium
---

## Outcome

Open a Minimap feature and see the implementation records and pull requests related
to it, without maintaining a second list of links. Changes appear while the server
is running without delaying startup, board reads, editing, or refresh.

## Canonical work and ownership

- [Agent Workflow: source relationships](https://github.com/rore/agent-workflow/blob/main/roadmap/features/add-work-record-source-relationships.md)
  owns the stored relationship, documented format, parser/read contract, capture
  instructions, and checks. A Work Record references its source item(s) and PR(s).
- [Minimap: related work](https://github.com/rore/minimap/blob/main/roadmap/features/show-feature-related-work.md)
  owns background discovery, the disposable reverse lookup, and feature-detail UX.
- Collection owns sequencing and one combined acceptance exercise. Pallium requires
  no changes. This is not an approval inbox, assignment registry, or new task state.

Feature progress and remaining scope still require reviewed judgment. Related
records, PR merges, and session presence do not automatically complete a feature.

## Sequence

1. The two implementers agree on Workflow's smallest supported relationship/read
   contract before implementing independently. Resolve repository/provider/item
   identity, stable record identity, multiple/no source, legacy/invalid data, PR
   references, configurable record locations, and checkout/version provenance.
   Keep the normative contract in Agent Workflow; Minimap links to it rather than
   maintaining a second schema. Do not require Python or execute repository scripts
   merely to render a Minimap board. Choose an interoperable data surface that fits
   both tools' existing packaging.
2. Workflow implements and validates production and reading of that contract.
   Minimap may develop against agreed fixtures, but combined acceptance uses the
   real output. Do not create two independently maintained backlink lists.
3. Minimap implements nonblocking initial discovery, known-change invalidation,
   periodic incremental reconciliation, manual refresh, bounded/coalesced work,
   and explicit loading/stale/error states. Reuse existing refresh facilities.
4. Run the combined exercise below. Link results in the tool features; keep only
   the cross-tool conclusion here. Follow applicable approvals for consumer
   installation changes; roadmap approval alone does not authorize live updates.

## Combined acceptance

Use an isolated representative repository and keep its Minimap server running:

- Create a feature and a real Workflow record with its exact reference; find the
  record from the feature without editing a backlink list.
- Add a PR reference and change recorded state; both appear within the documented
  freshness bound through background reconciliation and manual refresh.
- Modify, remove, and move relationships externally. Old links disappear and new
  links appear without restarting; failures retain a clearly marked last-good view.
- Exercise multiple records per feature, unrelated same-named items, and supported
  worktree views. Conflicting versions remain distinguishable, not silently merged.
- Verify missing Workflow, legacy records, and absent Pallium leave ordinary board
  operation usable and do not invent relationships or current activity.
- Capture and inspect actual browser UI from list and columns at desktop and narrow
  widths. Verify links, recorded-state wording, loading/empty/error behavior, and
  editing during refresh. Fix visual problems before acceptance.
- Measure cold and incremental discovery against a representative large corpus
  while board requests continue. Agree measurable freshness, latency, and IO limits
  in the Minimap feature before implementation; report results and remaining limits.

## Collection changes

No coordination-skill change is required for this feature. Its existing directions
already use authoritative work and tool-owned procedures. Update collection install
guidance only if an actual setup step changes; avoid speculative documentation.
