---
id: collection-coordination-recipe
title: Coordinate multi-task work across the collection
status: proposed
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
2. Propose independently verifiable delivery slices, their prerequisites, and the
   context each needs. Prefer working outcomes over untestable implementation layers.
   Record canonical items and references using Minimap's supported contract.
3. Identify candidates with satisfied prerequisites. Ready does not prove that
   specifications are complete or concurrent execution is safe. Check shared files,
   databases, ports, running services, test state, and external environments.
4. Select useful parallel work within the user's cost and execution constraints.
   Find existing sessions through Pallium; choose exact recipients explicitly.
   If no suitable session is available, work serially or expose the limitation.
   Relay does not create agents. Launching a new session requires a separately
   available and authorized runtime mechanism, outside the initial recipe.
5. Send a bounded assignment: objective, canonical item/Work Record links, scope,
   acceptance criteria, relevant constraints, and expected result evidence. Attach
   applicable work references through supported interfaces. Each executing session
   follows Agent Workflow, including its exemptions and required human approvals.
6. On a result or blocker, inspect the reported revision, evidence, and unresolved
   findings. Relay delivery/ACK means context admission, not task acceptance,
   completion, correctness, or agreement to an assignment. Silence is not failure.
7. Update canonical task state only after the applicable verification/review gates
   pass. Recalculate ready candidates as results change. Do not dispatch duplicate
   work after timeout, session restart, or a repeated completion message.
8. Verify that the delivered slices work together against the original outcome.
   Finish with evidence and remaining limitations in existing canonical records.
   If interrupted, leave a resumable pointer to current items, decisions, pending
   assignments, and the next action; do not rely on hidden conversation history.

## Initial Scope and Dependencies

- Define the recipe and one anonymized worked example before building automation.
- Inspect current shipped behavior in all three tools at implementation time.
  Distinguish available primitives from roadmap promises; document fallbacks and
  blocked capabilities rather than inventing tool commands or metadata fields.
- Relevant planned foundations: Minimap `add-work-item-dependencies` and
  `add-pallium-work-item-participants`; Pallium
  `add-relay-session-work-associations`. Participant UI is optional for an
  agent-led trial. Manual named-recipient coordination can test the recipe earlier.
- Reuse Agent Workflow's existing handoff, separate-review, and evidence rules.
  Receiving-session readiness and targeted behavioral review are proposed narrow
  improvements, not assumed shipped requirements or duplicate collection gates.
- Keep assignments bounded and recovery explicit. Use existing records and Relay
  message/endpoint identifiers where available; do not introduce an assignment
  service merely to represent orchestration in code.
- Cross-repository work uses exact repository/item/revision references. Missing
  dependency information or unavailable repositories remain explicit uncertainty.
  Respect configured checkout versions and each tool's scope/visibility rules.

## Out of Scope

A DAG execution engine, agent launcher, provider/model selection service, resource
lock manager, automatic polling/chasing, stacked-PR automation, new message semantics,
mandatory cross-model review, and a coordinator that is forbidden from coding.

## Validation and Done When

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

This file preserves the proposed collection feature. No implementation or automatic
orchestration is claimed.
