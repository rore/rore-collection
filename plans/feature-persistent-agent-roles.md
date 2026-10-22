---
id: persistent-agent-roles
title: Persistent agent roles with self-improving guidance
status: planned
priority: medium
---

## Outcome

Teach a role a lasting expectation once. A replacement session adopts the same
role, follows its updated guidance, and can retrieve the original discussion.
This is continuity of working responsibilities, not a fictional personality or
another orchestrator. Keep the mechanism simple and usable directly with a human.

## Ownership

- Collection: a separate role skill, small role-file convention, foreground upkeep,
  and minimal discovery/handoff additions to the existing coordination skill.
- [Pallium: persistent role history](https://github.com/rore/Pallium/blob/main/roadmap/features/add-persistent-role-history.md):
  current role association, temporal history capture and exact role-history search.
- No new Minimap or Agent Workflow role feature by default. Existing repository
  editing and approval requirements still apply; do not duplicate their procedures.

## Agreed Behavior

### One identity and a small definition

The Relay name IS the role identity. Do not add another role name, ID or mapping.
One active session holds that name; start with one active role per session. The
definition's pathname is navigation, not identity, so moving it does not create a
new role. Define one simple discovery convention during implementation, with a
small Markdown entry file and optional linked references. Detect duplicate or
conflicting definitions instead of picking one silently.

The entry names the role, purpose, responsibilities, boundaries, working guidance,
expected outputs and when to read references. Shared product/design standards
stay in existing authoritative documents. Role-specific working guidance belongs
in the role file; temporary branches, blockers and next steps stay in task/handoff
records. Provide a short generic example and a simple creation/bootstrap path.

### Adoption and handoff

A session reads current guidance, adopts the role through Pallium's supported
contract, verifies the Relay binding and reports readiness or partial failure.
Do not silently take an occupied name. Name binding, guidance loaded and assignment
accepted are separate facts; reuse existing authorization and handoff procedures.

Coordination carries the role entry path/revision with its existing continuation
packet. The successor reads current guidance and explicitly accepts unfinished
work. Preserve guidance changes and pass any unpublished edits on handoff or
completion. The single role holder handles normal Git/worktree reconciliation;
do not add a dedicated canonical checkout or synchronization system. Shared-file
edits still preserve others' changes. Refresh guidance on adoption/handoff and
when resuming work with known changed guidance; do not imply automatic refresh.

Takeover redirects future sends only. Reuse existing pending-message and safe-stop
handling; do not claim it transfers queued messages, task refs or permissions.
Role membership persists across tasks until explicitly left or transferred.

### Self-improvement is part of the role

The working agent recognizes clear lasting corrections and improves the appropriate
existing guidance during ordinary work, without requiring the human to request
documentation upkeep. At completion/handoff, consider any material lessons still
uncaptured. Briefly tell the human what changed. No separate background process,
review agent, scheduler or per-turn learning ritual.

Distinguish durable expectations from task-local requests: "check phone layouts
before finishing UI work" may be lasting guidance; moving one button normally is
not. Review feedback and proven reusable techniques can inform guidance; transient
tool failures and failed experiments must not become permanent rules.

Correct existing guidance rather than append redundant rules. Put shared standards
in their existing document and link them. Keep useful evidence references when
available, not conversation copies or session diaries. No change is valid when no
lasting lesson exists. Within granted editing authority, make clear corrections;
ask about genuinely ambiguous/contradictory feedback or consequential changes in
responsibilities or policy. Self-improvement never expands permissions. Keep edits
reviewable and reversible through normal repository practices.

### Source history

Use Pallium's role search to recover supporting conversations when useful, not on
every turn. History is evidence, not current instructions or proof of live state.
Preserve access and provenance boundaries. Current guidance must work when history
is unavailable; clearly disclose unavailable association/search rather than claim
full continuity. Do not add another memory store or infer old membership from the
name's current holder. No automatic historical backfill.

## Delivery and Acceptance

1. Agree the small adoption/departure/history contract with Pallium before coding
   dependent instructions. Resolve discovery/bootstrap, explicit rename behavior
   and missing/conflicting references; keep the Relay name as the only identity.
2. Implement the role skill and only necessary coordination discovery/handoff
   links. Keep role procedures in the role skill; managers and direct-user sessions
   load the same guidance. Package/install using existing skill conventions.
3. Test a real role: A adopts -> human gives a durable correction -> A updates the
   correct document -> B takes over with authorization -> B follows the expectation
   on a relevant task without a reminder -> B retrieves A's original discussion.
4. Verify a task-local exception does not become a permanent rule; unrelated
   shared guidance and task refs survive. Check unpublished handoff edits, stale
   guidance, missing references, occupied names and unavailable history. Report
   partial success honestly. Demonstrate direct-user use without a manager.
5. Record actual host support and combined evidence in these existing features.
   Observe a bounded sample of natural corrections and replacements after release:
   did expectations survive, were inappropriate rules added, and did upkeep cost
   more than it saved? Agree the observation window at release; no new tracker or
   background learning service. Qualification alone is not natural adoption.

## Exclusions

No background self-improvement, extra role identity, team runtime, automatic session
creation, guaranteed wake, automatic permissions, mandatory tracker integration,
new synchronized guidance store or exhaustive review of every conversation.

This is planned work. This feature does not authorize live installation changes;
obtain the required scoped approval when delivering installed skills/integrations.
