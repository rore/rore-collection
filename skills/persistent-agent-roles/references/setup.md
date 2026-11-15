# Set up a role

Create `roles/mapping.yaml` in the consumer repository and short Markdown guides under `roles/`. Each key is one exact Relay name; several names can select one guide:

```yaml
"@backend1": backend.md
"@backend2": backend.md
"@frontend1": frontend.md
```

A guide can start with purpose, responsibilities, boundaries, working guidance, expected outputs, and links to references when relevant. For example, `roles/backend.md`:

```markdown
# Backend developer
Purpose: Keep the backend reliable and maintainable.
Responsibilities: Implement assigned backend changes and verify caller-visible behavior.
Boundaries: Do not change shared policy or another team's ownership without approval.
Working guidance: Read repository architecture and test instructions when relevant.
Outputs: Report the change, evidence, and remaining risk to the task owner.
```

Add one trigger to the repository's existing agent instruction file: "This repository uses `persistent-agent-roles`. At start, resume, after compaction or context recovery, at handoff, and on a new assignment, reload the skill, verify this session's current Relay name, and reread the mapping, selected role guide and linked shared guidance before role-specific work. A summary or remembered role is not a substitute." Install or expose the separate persistent-agent-roles skill through the host’s supported skill discovery; roles/mapping.yaml selects guidance files and does not install the skill. When upgrading, refresh existing repository triggers through their normal workflow too; syncing the skill alone does not update those instructions. Shared standards remain in authoritative documents; temporary work and blockers belong in task/handoff records. To add agents of one specialty, map distinct authorized Relay names to the shared guide; coordination still owns creation and takeover. Reuse an appropriate existing guide; a temporary assignment does not create a new role. Add a guide only when enduring responsibilities materially differ.

Reject duplicate keys even if a YAML parser would silently keep the last. Accept only a flat map of exact `@name` keys to relative Markdown paths under `roles/`; reject malformed entries, wildcards, absolute or escaping paths, and missing/unreadable files. Missing mapping or no entry is normal opt-out for an ordinary Relay name. For an assigned standing role, report the missing setup once and continue independently authorized work without claiming persistent guidance is active; this does not authorize creating a role or taking over a name. Malformed existing configuration or a missing/unreadable referenced guide is an error. Verify the intended guide revision and preserve concurrent or unpublished edits through normal Git reconciliation.

## Verify compaction recovery

In a separately authorized controlled session, record its verified Relay name and
trusted runtime/session/container binding, then compact its context. Before its
first role-specific action, verify that the host supplies the durable discovery
instruction again and the agent reloads the skill, checks current identity, and
reads the current mapping, selected guide and linked shared guidance from files.
A summary saying those files were loaded is not evidence of a fresh read.

With unchanged ownership and binding, the Relay name should remain registered.
An unexpected unnamed lookup needs binding/registration investigation, not an
automatic rename or a claim that compaction clears names. For an authorized
takeover, verify that recovery stops applying the former role's guide. If host
re-entry or identity cannot be verified, report that coverage gap; syncing files
or passing static checks does not prove recovery or guarantee future compliance.
