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
- [Pallium: history by Relay name](https://github.com/rore/Pallium/blob/main/roadmap/features/add-persistent-role-history.md):
  historical Relay-name attribution and exact name-based history search.
  Pallium does not interpret role files or register roles.
- No new Minimap or Agent Workflow role feature by default. Existing repository
  editing and approval requirements still apply; do not duplicate their procedures.

## Agreed Behavior

### One runtime identity, mapped guidance

The Relay name identifies a persistent position and its history. A repository-local
`roles/mapping.yaml` selects that position's Markdown guidance; it is configuration,
not another runtime identity or registration. Use one exact name-to-file entry per
position, with paths relative to `roles/`:

```yaml
"@backend1": backend.md
"@backend2": backend.md
"@frontend1": frontend.md
```

Several names can select the same file. No wrapper file per name is required;
no wildcard matching or inheritance engine. Moving a guidance file requires updating
its mapping but does not change Relay identity or historical attribution. Validate
the mapping without silently accepting duplicate names, invalid configuration or
missing/unreadable referenced files. Missing mapping or no entry is normal opt-out;
malformed existing configuration is an error, not opt-out.

The entry names the role, purpose, responsibilities, boundaries, working guidance,
expected outputs and when to read references. Shared product/design standards
stay in existing authoritative documents. Role-specific working guidance belongs
in the role file; temporary branches, blockers and next steps stay in task/handoff
records. Provide a short generic example and a simple creation/bootstrap path.

The role skill guides setup of multiple agents of one specialty: reuse the shared
guide, choose distinct Relay names through existing authorized procedures, and add
mapping entries. Coordination owns agent creation/approval. Their routing, history
and replacement continuity remain separate.

### Adoption and handoff

Persistent roles are a repository-level opt-in, not a task-level switch. The
repository's existing agent instructions carry the short discovery trigger.
In an opted-in repository, discover the session's current Relay name and resolve
its mapping in the project. If mapped, read and follow the file; if unmapped, the name
remains an ordinary Relay name with no role-specific guidance. No separate role
adoption, registration or departure call. Report unavailable name discovery rather
than guess. No definition is normal; an existing unreadable or conflicting
definition is an error to surface. Reuse existing naming and authorized takeover;
loading guidance does not itself accept work or expand permissions.

Coordination carries the mapping and guidance path/revision with its existing continuation
packet. The successor reads current guidance and explicitly accepts unfinished
work. Preserve guidance changes and pass any unpublished edits on handoff or
completion. Agents handle normal Git/worktree reconciliation;
do not add a dedicated canonical checkout or synchronization system. Shared-file
edits still preserve others' changes. Recheck the current Relay binding on skill
entry, resume, handoff and starting a new assignment, including after another
session takes over the name; do not trust a name cached in conversation. Recheck
the mapping and applicable guidance at those boundaries and on a known name change.
Refresh applicable linked shared guidance even without a
change notification; use normal Git reconciliation if the checkout is stale,
without claiming automatic cross-worktree synchronization. If ownership was lost, stop using
and maintaining the former role's guidance. Unavailable discovery is not proof of
continued ownership; disclose uncertainty and defer role-specific actions until
resolved. This does not revoke independent task instructions or shared standards.
Mapping edits do not instantly change an already-running agent's behavior; there
is no per-turn polling or automatic interruption to refresh guidance.

Keep a short durable discovery instruction: when using roles, use freshly supplied
Relay identity to find guidance, including after compaction. Prefer Pallium's
existing injected context over an extra lookup. Distinguish a confirmed name,
confirmed no name, and unavailable lookup; omission or an old summary proves
neither ownership nor loss. If recovery needs a lookup, use a supported read-only
surface, never the naming mutation with an omitted name (which clears the name).
Do not add another persistence mechanism or rely on the role skill remaining in
conversation memory. Verify the host's actual discovery/re-entry behavior.

Takeover redirects future sends only. Reuse existing pending-message and safe-stop
handling; do not claim it transfers queued messages, task refs or permissions.
Task completion does not remove the Relay name or its role guidance. On a name
change, stop applying the former role's guidance and resolve the new definition.
There is no separate role membership or lifecycle state to maintain.

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

Correct existing guidance rather than append redundant rules. Choose the owning
document without making the human route each lesson: shared practice (for example,
checking tenant isolation when changing queries) belongs in the shared guide;
lasting position-specific responsibility (such as owning billing) must remain
position-specific; temporary assignments belong in task records. Never silently
promote a correction aimed at one named agent into shared guidance. Ask when its
intended scope is unclear. If distinct lasting guidance is needed, map that position
to a specific Markdown file linking the common guide rather than change everyone's
instructions or add a new identity. Preserve concurrent edits
through ordinary Git reconciliation. Put shared standards in their existing
document and link them. Keep useful evidence references when
available, not conversation copies or session diaries. No change is valid when no
lasting lesson exists. Within granted editing authority, make clear corrections;
ask about genuinely ambiguous/contradictory feedback or consequential changes in
responsibilities or policy. Self-improvement never expands permissions. Keep edits
reviewable and reversible through normal repository practices.

### Source history

Use Pallium's history lookup by Relay name to recover conversations when useful, not on
every turn. History is evidence, not current instructions or proof of live state.
Attribute a turn to its validated start-of-turn Relay name, retaining that label for
delayed capture or retry even if takeover occurs mid-turn; it does not prove current
ownership or permission to keep using the former role guide.
Preserve access and provenance boundaries. Current guidance must work when history
is unavailable; clearly disclose unavailable name lookup/history rather than claim
full continuity. Do not add another memory store or infer historical names from the
name's current holder. No automatic historical backfill.

## Delivery and Acceptance

1. Reuse existing Relay name discovery and takeover. Agree only the name-based
   history lookup contract with Pallium. Resolve file discovery/bootstrap and
   missing/invalid mappings; keep the Relay name as the only runtime identity.
2. Implement the role skill and only necessary coordination discovery/handoff
   links. Keep role procedures in the role skill; managers and direct-user sessions
   load the same guidance. Package/install using existing skill conventions.
3. Test a real role: A holds a name and reads its mapped file -> human gives a durable correction -> A updates the
   correct document -> B takes over with authorization -> B follows the expectation
   on a relevant task without a reminder -> B retrieves A's original discussion.
   Then resume A without a local rename: A discovers the externally caused name
   loss and stops applying/updating that role's guidance, without reclaiming the
   name or disturbing B. Earlier history and unrelated task refs remain intact.
   Repeat after compaction, both with unchanged ownership and after external
   takeover. Cover next-turn recovery and compaction within an ongoing turn;
   verify fresh identity and guidance recovery rather than assuming a hook ran.
4. Verify a task-local exception does not become a permanent rule; unrelated
   shared guidance and task refs survive. Check unpublished handoff edits, stale
   guidance, missing mapping/no entry, duplicate names, malformed configuration,
   missing referenced files, name changes, occupied
   names and unavailable history. Verify no role-registration call is required. Report
   partial success honestly. Demonstrate direct-user use without a manager.
5. Two differently named agents map to one shared guide. A lasting correction from
   one updates that guide once; the other resumes and applies the updated guidance
   without a separate notification or human reminder. Verify position-specific
   guidance stays separate, temporary task instructions do not become shared rules,
   concurrent edits are preserved, and messages/history retain their individual names.
   Change a mapping and verify adoption at the next defined refresh boundary,
   without claiming an immediate switch in an ongoing turn. An ambiguous or
   individual correction must not silently alter the shared guide.
6. Record actual host support and combined evidence in these existing features.
   Observe a bounded sample of natural corrections and replacements after release:
   did expectations survive, were inappropriate rules added, and did upkeep cost
   more than it saved? Agree the observation window at release; no new tracker or
   background learning service. Qualification alone is not natural adoption.

## Exclusions

No background self-improvement, extra role identity or registration, team runtime, automatic session
creation, guaranteed wake, automatic permissions, mandatory tracker integration,
new synchronized guidance store or exhaustive review of every conversation.
Specialty-wide history search (for example, all past backend developers) is outside
this slice; search remains by individual Relay name, with no new Pallium concept.

This is planned work. This feature does not authorize live installation changes;
obtain the required scoped approval when delivering installed skills/integrations.
