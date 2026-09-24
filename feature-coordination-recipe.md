---
id: collection-coordination-recipe
title: Coordinate multi-task work across the collection
status: in_progress
priority: high
---

## Outcome

Provide a collection-level skill that helps a lead agent turn a larger objective
into bounded delivery tasks, select ready work, coordinate existing sessions, and
verify the combined result. Start with an agent recipe over the existing tools,
not a new scheduler, agent runtime, or mandatory fourth product.

## Why

The collection supplies work tracking, per-task execution rules, session messaging,
and history. It does not yet tell a lead agent how to use them together across a
larger objective. That decision-making sits above Agent Workflow's individual task
lifecycle. The lead agent may also implement work directly; pure dispatch is not a
required operating style.

## Ownership

| Tool or layer | Responsibility |
|---|---|
| Minimap | Canonical work items, dependencies, status, and roadmap views. |
| Agent Workflow | Each task's scope, risk, plan, verification, review, and recovery record. |
| Pallium | Session discovery and work associations, exact-target communication, and eligible historical context. |
| Coordination recipe | Decomposition, selecting ready candidates, choosing participants, resolving coordination blockers, and assessing the combined outcome. |

The agent makes coordination decisions. A skill instruction is not a deterministic
scheduler or resource-lock implementation. Do not copy task state into another
ledger or make any tool dependent on the entire collection.

## Intended Flow

1. Establish the overall outcome, acceptance criteria, constraints, and allowed
   delegation/model budget. Inspect existing work and current capabilities before
   creating anything; avoid decomposing a task that one session can handle cheaply.
   When using Minimap, designate one shared roadmap checkout for the objective;
   otherwise use the existing authoritative work source.
2. Propose independently verifiable delivery slices, their prerequisites, and the
   context each needs. Prefer working outcomes over untestable implementation layers.
   Record canonical items and references using Minimap's supported contract.
3. Identify candidates with satisfied prerequisites. Ready does not prove that
   specifications are complete or concurrent execution is safe. Check shared files,
   databases, ports, running services, test state, and external environments.
4. Select useful parallel work within the user's cost and execution constraints.
   Find existing sessions through Pallium and choose exact recipients explicitly,
   but do not infer availability from idle/dormant state, participant membership,
   or an empty work-reference list. Inspect known current work and ask. If no
   suitable session is available, work serially or expose the limitation. Relay
   does not create agents; launching one requires a separately available and
   authorized runtime mechanism.
5. Send a non-preempting offer that already contains the complete bounded assignment:
   objective, canonical item/Work Record links, scope, acceptance criteria,
   constraints, dependencies, and expected result evidence. Ask for one explicit
   response: `accept`, `defer`, or `decline`. Do not attach work on the receiver's
   behalf.
6. The receiver preserves its current user assignment and inspects its actual work
   before replying. Existing ad hoc work still counts when it has no supported
   canonical reference; report it without inventing an identifier. On `accept`, the
   receiver attaches or reuses the authoritative exact work reference when supported
   and follows the repository's applicable workflow, including its exemptions and
   required human approvals, before implementation. Acceptance is not permission to
   bypass those gates. `defer` and `decline` change no task state or association.
   Do not require another lead confirmation unless scope or dependencies changed.
   Workers implement in isolated checkouts and report the exact feature reference,
   revision, result evidence, and blockers to the lead. They attach their own session
   to the exact work reference through Pallium when available.
7. On a result or blocker, inspect the reported revision, evidence, and unresolved
   findings. Relay delivery/ACK, wake, participant presence, and work association mean
   neither task acceptance nor completion, correctness, or agreement. Silence is not
   failure. Relay transport does not enforce non-preemption; the receiver must preserve
   current work.
8. The lead updates the shared roadmap at assignment acceptance and on reported
   progress or blockers. A sole developer makes those updates itself. Mark completion
   only after the applicable verification/review gates pass. Recalculate ready
   candidates as results change. Do not dispatch duplicate work after timeout,
   session restart, or a repeated completion message.
9. On handoff, the new receiver accepts and attaches itself before starting. The old
   receiver detaches only after it actually leaves the work, and only the finished
   explicit association it successfully attached; structural and unrelated references
   remain. Completion uses the same exact cleanup rule.
10. Verify that the delivered slices work together against the original outcome.
   Finish with evidence and remaining limitations in existing canonical records.
   If interrupted, leave a resumable pointer to current items, decisions, pending
   assignments, and the next action; do not rely on hidden conversation history.

## Initial Scope and Dependencies

- Define the recipe and one anonymized worked example before building automation.
- Inspect current shipped behavior in all three tools at implementation time.
  Distinguish available primitives from roadmap promises; document fallbacks and
  blocked capabilities rather than inventing tool commands or metadata fields.
- Shipped foundations are Pallium's exact work associations, Minimap's optional
  participant view and authoritative item references, and Agent Workflow's receiver
  readiness, handoff, evidence, and targeted-review guidance. Minimap dependency
  support remains version-dependent: use it only when the installed version exposes
  it, otherwise keep prerequisites explicit in the existing canonical item.
- Participant UI is optional for an agent-led trial. Manual named-recipient
  coordination can test the recipe without making any tool mandatory.
- Keep assignments bounded and recovery explicit. Use existing records and Relay
  message/endpoint identifiers where available; do not introduce an assignment
  service merely to represent orchestration in code.
- Cross-repository work uses exact repository/item/revision references. Missing
  dependency information or unavailable repositories remain explicit uncertainty.
  Respect configured checkout versions and each tool's scope/visibility rules.

## Optional Tool Fallbacks

| Unavailable tool | Continue with |
|---|---|
| Minimap | Existing authoritative issue, Work Record, or file links. Keep readiness in that source; do not create a shadow ledger. |
| Pallium | An authorized runtime communication channel and the same explicit receiver decision. Do not infer participants or associations. |
| Agent Workflow | The repository's native planning, risk, verification, and review process. Do not claim a Work Record or gate that is absent. |

## Optional-tool validation matrix

| Minimap | Agent Workflow | Pallium | Trial pass condition |
|---|---|---|---|
| No | No | No | Pick up and complete work in an existing authoritative source. |
| Yes | No | No | Start, block, and complete an item in one shared roadmap checkout. |
| No | Yes | No | Apply required task gates without inventing a roadmap item. |
| No | No | Yes | Offer work to an exact recipient; accept without inventing a work ref. |
| Yes | Yes | No | Keep item state and any required Work Record distinct through review. |
| Yes | No | Yes | Receiver attaches an exact feature ref; participant view and detach agree. |
| No | Yes | Yes | Receiver attaches an exact existing record ref when one exists. |
| Yes | Yes | Yes | Run the pickup, participant, pause/handoff, and completion trial below. |

## Bounded live trial

Use real agent sessions and synthetic public work items. Record exact references,
revisions, participant evidence, and the final reviewed state; do not count Relay
delivery alone as acceptance.

1. A lead picks up a roadmap objective in its designated shared checkout, with task
   B dependent on verified evidence from A. It inspects canonical state and current
   associations before offering either task.
2. One candidate has no work references but reports an ad hoc user task, so it
   replies `defer`. The lead does not preempt it or attach A on its behalf.
3. A second candidate receives the complete A offer, checks its current work,
   replies `accept`, attaches A's authoritative reference when supported, and starts
   in an isolated checkout without another confirmation round trip. The lead records
   the accepted assignment; the participant view, when enabled, shows that session.
4. Delivery and association are recorded, but the lead keeps B blocked until A's
   reported revision and evidence pass the applicable review.
5. During B, the worker reports a blocker and pauses. The lead records the blocked
   state. A handoff receiver explicitly accepts and attaches B before continuing in
   its own checkout. The first worker detaches only its explicit B association after
   leaving; unrelated or structural references remain.
6. The handoff receiver reports B's exact feature reference, revision, and evidence.
   The lead verifies the result, updates the shared roadmap to complete, and checks
   the original objective. With no lead, the sole developer performs these updates.

## Out of Scope

A DAG execution engine, agent launcher, provider/model selection service, resource
lock manager, automatic polling/chasing, stacked-PR automation, new message semantics,
mandatory cross-model review, and a coordinator that is forbidden from coding.

## Initial skill acceptance

- The skill validates structurally, is discoverable on demand, and keeps all three
  tools optional without inventing references or bypassing repository gates.
- Use this accepted collection assignment for the real pickup, isolated work,
  review, and completion path. Record participant and handoff steps as untested
  until real sessions perform them; a message or simulated result is not evidence.
- Check saved-but-unaccepted delivery, a busy candidate, absent optional tools,
  insufficient result evidence, and duplicate delivery with controlled cases.
- An independent reviewer checks the skill, and a fresh coordinator can recover
  the active assignment and next action from canonical files without chat history.

## Broader validation and done when

1. A lead agent can follow the recipe for a small objective with two independent
   tasks and one dependent integration task, using canonical files and existing
   session tools. Record actual revisions and evidence, not a successful-looking
   conversation transcript. Use a bounded predeclared model/turn budget.
2. The trial covers a shared-resource conflict, an unavailable participant, an
   explicit blocker, insufficient completion evidence, duplicate delivery, and a
   coordinator restart. These must not cause silent completion or duplicate dispatch.
   Use controlled/replayed cases for expensive failure paths.
3. A fresh coordinator can identify ongoing work and the next action from the
   canonical records and linked artifacts. History supplements missing detail but
   does not silently replace required task state.
4. Per-task risk/review gates still hold, and integration evidence establishes the
   overall outcome. A successful child task alone does not complete the objective.
5. Document what the trial improved, its coordination cost, and remaining gaps.
   Simplify or drop steps whose overhead exceeds their demonstrated value. Only
   repeated concrete failures justify new runtime machinery or tool features.

## Open Decisions for Pickup

Choose the smallest trial objective, the minimum supported capability set, and how
existing parent/work records reference assignments across tasks. Settle these from
actual repository conventions; do not introduce a universal schema in advance.

The initial [collection coordination skill](skills/collection-coordination/SKILL.md)
is in review. The bounded trial and combined acceptance remain open; no automatic
orchestration is claimed.
