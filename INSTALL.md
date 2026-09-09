# Install with your coding agent

Give your coding agent this prompt:

```text
Read https://github.com/rore/rore-collection/blob/main/INSTALL.md and help me install the tools I need.
```

## Instructions for the agent

Help the user choose and install tools for their environment. This guide routes
you to each tool's maintained installation procedure; it is not a combined installer.
Do not install anything merely because you read this file.

### 1. Choose tools with the user

Explain the options briefly:

| Tool | Useful when you want | Installation source |
|---|---|---|
| Minimap | Repository roadmaps and spec review with agents. | [Install](https://github.com/rore/minimap#install) |
| Agent Workflow | Risk-aware engineering tasks, verification/review, and durable Work Records. | [Quick start](https://github.com/rore/agent-workflow#quick-start) and [integration guide](https://github.com/rore/agent-workflow/blob/main/docs/INTEGRATION.md) |
| Pallium | Messages between agent sessions and searchable earlier session history. | [Getting started](https://github.com/rore/Pallium/blob/main/docs/getting-started.md) |

Ask which tools the user wants. If they already selected tools, use that selection
without asking again. All three are optional and independently useful. If the user
is unsure, recommend the smallest selection for their stated need and confirm it.

### 2. Establish the installation context

Inspect what is already available, then ask only for missing choices:

- operating system and coding runtime(s) to connect;
- target repositories, and personal versus repository installation scope where
  the selected tool supports that choice;
- existing installations, versions, services, skills, hooks, and configuration.

Read the current official instructions for each selected tool before running its
commands. Check prerequisites and supported paths there. Do not assume one runtime's
skill directory, shell commands, hook support, or wake behavior applies to another.
If instructions are unavailable or the runtime is unsupported, explain that specific
limitation rather than inventing an installation path. Continue independent selected
installs where possible.

### 3. Install the selected tools

Follow each official procedure in an environment-appropriate shell. Preserve existing
configuration and data; reuse a healthy installation rather than replacing it. Explain
any required upgrade or conflicting setup before changing it. Keep credentials out of
chat and committed files. Observe each tool's installation approvals and repository
rules; selection of a tool does not authorize unrelated governance changes.

- **Minimap:** use its packaged installation instructions and supported skill scope.
  If enabling roadmap use in a repository, follow its setup contract and preserve
  existing planning files. Spec review and roadmap usage are separate choices.
- **Agent Workflow:** bootstrap in the selected consumer repository, using its official
  packaged skill and integration procedure. Keep required CI/review approval steps;
  never silently change branch protection or CODEOWNERS. Reuse or upgrade existing
  installations through the documented path rather than restarting bootstrap blindly.
- **Pallium:** follow the service guide, then the selected runtime guide:
  [Codex](https://github.com/rore/Pallium/blob/main/docs/codex-integration.md),
  [Claude Code](https://github.com/rore/Pallium/blob/main/docs/claude-code-integration.md),
  or [OpenCode](https://github.com/rore/Pallium/blob/main/integrations/opencode/README.md).
  Keep any checkout referenced by the installation in a stable location. Use current
  instructions for service lifecycle, scope, and session identity. Hook installation
  and hook trust are different steps; report user-required approval/restart steps
  explicitly and never bypass trust. Leave optional derived memory off unless requested.

If multiple tools are selected, install and verify them individually. There is no
required collection-wide installation order. Do not configure proposed work-item
bindings, dependency features, or the coordination recipe as if they already ship;
confirm availability in the selected tool version first.

### 4. Verify and hand back

Use each tool's documented installation checks, rather than treating copied files
or a successful installer exit as proof of a working integration:

- **Minimap:** confirm the skill is discoverable and use the documented lifecycle
  script to open the intended roadmap or a user-selected spec. Verify the target URL.
- **Agent Workflow:** confirm the packaged skill/configuration and required checker
  artifacts are present; follow bootstrap's verification of CI and outstanding user
  steps. Do not manufacture a completed engineering task just to test installation.
- **Pallium:** verify service health and runtime integration as documented. Confirm
  context/hooks and tool availability. Use a user-approved recipient or controlled
  test session for messaging checks; do not send test messages to unrelated sessions.
  Distinguish passive delivery from qualified active wake. Never mix hook receiving
  with MCP receiving in the same session.

Report each selected tool as working, installed but awaiting a user step, or blocked.
Include the location/scope, version or revision when available, checks performed,
remaining actions, and one short example of how to use it. Do not claim a restart,
hook approval, CI setup, or end-to-end check happened unless it actually did.
