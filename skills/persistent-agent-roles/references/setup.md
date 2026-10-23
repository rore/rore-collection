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

Add one trigger to the repository's existing agent instruction file: "This repository uses persistent agent roles. When starting work here, resuming, handing off, or beginning a new assignment, load the persistent-agent-roles skill, verify your current Relay name, and reload its mapped guide." Shared standards remain in authoritative documents; temporary work and blockers belong in task/handoff records. To add agents of one specialty, map distinct authorized Relay names to the shared guide; coordination still owns creation and takeover.

Reject duplicate keys even if a YAML parser would silently keep the last. Accept only a flat map of exact `@name` keys to relative Markdown paths under `roles/`; reject malformed entries, wildcards, absolute or escaping paths, and missing/unreadable files. Missing mapping or no entry is normal opt-out; malformed existing configuration is not. Verify the intended guide revision and preserve concurrent or unpublished edits through normal Git reconciliation.
