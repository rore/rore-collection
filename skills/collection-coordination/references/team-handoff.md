# Team handoff

Use only when the human requests replacement of the manager or team sessions. Do not initiate replacement based on session length. The outgoing manager drives the transfer; the human should not need to copy prompts or recreate developers manually.

## Establish scope and settings

- Use the user's request and current team to determine which sessions to replace. Ask one concise, explained clarification if team membership, replacement scope, or Relay-name takeover is unclear. Do not include unrelated agents or replace developers carrying separate user work without resolving that scope.
- Preserve each session's own exact model and reasoning effort, not a common team setting. Verify from authoritative runtime settings or the human; self-description, role, task title, and defaults are insufficient. If settings cannot be read or reproduced, ask before creating that replacement. Do not silently substitute a model or effort.
- A request to replace the team while preserving its settings authorizes setting those verified values on the new sessions. It does not authorize changing existing sessions, expanding work, or bypassing host approval rules. Use supported chat-creation tools for independent replacements, not temporary subagents. Verify the available tools can preserve the project, host, and actual working checkout; surface any unsupported requirement.

## Prepare and stop safely

- Gather one compact handoff using existing authoritative records: objective and remaining acceptance criteria; team roles and session IDs; verified model/effort; project and exact checkout/branch; dirty work; pending operations, blockers and approvals; relevant PRs/tests; exact work references and Relay names; next action per developer. Keep private operational details out of public repositories. Prefer links and current facts over transcripts or repeated history.
- Ask each outgoing developer to reach a safe stopping point, report unfinished operations, and confirm it will make no further mutations. A queued request or idle indicator is not confirmation. Preserve dirty changes and long-running operations; do not discard, move, or duplicate their worktrees. If a worker cannot confirm, leave that assignment held and explain the blocker.
- Reconcile pending messages and late results with the handoff. Preserve message IDs and distinguish completed actions from outstanding requests. A Relay-name takeover does not transfer old queued deliveries or prove receipt. Follow the Relay skill's claim/ACK rules; do not blindly resend pending instructions.

## Transfer responsibility

- Create the fresh manager with its verified settings, the handoff, this procedure, and the user's authorization and its limits. The outgoing manager remains responsible for transfer until the successor explicitly accepts; the successor must not dispatch developers before the safe-stop conditions are confirmed.
- The successor creates the scoped replacement developers with each predecessor's verified settings and existing checkout, then obtains their acceptance of their specific assignment. New-session defaults must not override the recorded settings. If creation has an uncertain outcome, inspect before retrying; reuse already-created replacements rather than making duplicates.
- Once each predecessor is stopped and its successor has accepted, transfer its Relay name using the supported takeover procedure and the user's authorization. Verify the name resolves to the intended new session. Without Relay, continue through the authorized available channel. Preserve exact work references; successors manage their own associations. Do not reopen completed work merely to recreate presence.
- The outgoing manager stops dispatching when the new manager accepts responsibility. If part of the transfer fails, keep affected assignments paused and identify who owns recovery; do not let both generations work on the same assignment.

## Verify completion

The successor confirms actual settings and checkout for each replacement, accepted assignments, Relay routing where used, and the next action or explicit blocker. Report the new chat links and any unresolved transfer to the human. Do not declare success from chat creation or message delivery alone. Retain old chats for recovery; archive only when authorized. Do not delete worktrees as part of session replacement.
