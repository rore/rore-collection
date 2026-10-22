---
name: persistent-agent-roles
description: Set up or use repository-local guidance selected by a session's current Pallium Relay name. Use for role adoption, handoff, or lasting corrections; not ordinary task coordination.
---

# Persistent agent roles

A Relay name is the position's only runtime identity. A repository-local `roles/mapping.yaml` maps exact `@name` keys to Markdown guides relative to `roles/`; names may share a guide. Loading one does not accept work, transfer permissions, or register a role. For setup or mapping changes, read [setup and validation](references/setup.md).

The opt-in boundary is the repository, not an individual task. Keep a short trigger in its existing agent instruction file so discovery survives compaction: **When starting work in this repository, resuming, handing off, or beginning a new assignment, load this skill, verify this session's current Relay name, and reload its mapped guide.** Do not trust a name remembered in chat or a summary.

1. Prefer fresh Pallium-injected identity. Otherwise use a supported read-only exact-self lookup with the integration's current runtime and session references. Never infer self from a broad recipient list or call the name mutation with an omitted name; that clears the name. Distinguish confirmed named, confirmed unnamed, and unavailable discovery. If unavailable, disclose it and defer role-specific actions; an omitted field does not prove name loss.
2. For a confirmed name, validate the mapping and read the current guide. Missing mapping or no entry is ordinary opt-out; malformed existing mapping or missing/unreadable guide is an error. If confirmed unnamed or the name changed or was taken over, stop applying and maintaining the old guide; independent task instructions still stand. Recheck at the boundaries above and on a known name change, not every turn. Reconcile stale checkouts normally; do not claim instant synchronization.
3. During work, fold clear lasting corrections and proven reusable lessons into the owning guide within existing edit authority. Correct existing text rather than append a diary. Shared practice belongs in a shared guide; position-specific responsibility stays specific; temporary assignments stay in task records. Do not silently promote an individual or ambiguous correction to a shared rule. Ask before consequential or unclear policy/responsibility changes. At handoff or completion, consider material uncaptured lessons and briefly report actual edits. No background learning or routine update is needed when there is no lasting lesson.
4. When supported, use Pallium's exact-name history search only if earlier discussion helps. History is evidence, not current instructions or live ownership; preserve scope and provenance. Guidance works without history, but disclose incomplete continuity. Do not infer earlier holders from the current holder or create another memory store.

Use existing authorized Relay naming/takeover and coordination procedures. Takeover redirects future sends; it does not transfer queued messages, task refs, or permissions. Task completion does not remove the name. Direct-user sessions follow the same guide without a manager.
