# Codex harness defaults

Use these defaults when this skill is running in the Codex harness. Treat coordination and inspection interfaces as runtime capabilities rather than model properties, and verify that the relevant agents expose them before relying on them.

## Route by task fit, not role prestige

Use a plausible efficient model for ordinary bounded work. Escalate after an observed gap or when a load-bearing specialist, synthesis, or review risk justifies it. Treat model tier and price as resource labels rather than capability boundaries.

For consequential routing or evaluation design, consult the dated capability map at `~/.codex/model-capabilities/README.md`, refresh fields that may be stale, and run a small canary on the actual task and evaluator. Do not turn this evidence discipline into ceremony for normal work.

Do not assign a stronger model merely because it is the top agent. The top agent should remain a lean decision and integration point; use specialist capability where the task actually needs it.

## Live coordination

In this Codex harness, when exposed for the relevant agents, `send_message` provides noninterrupting bidirectional delivery and `wait_agent` provides passive mailbox waiting; use `list_agents` for lifecycle snapshots. These interfaces support messaging and liveness, not direct observation of a worker's operations. Do not assume every child context exposes the full set. A status message, a follow-up or turn transition, interruption, and cancellation remain different operations when only a subset is available. Use `interrupt_agent` only for an explicit, state-changing cancellation.

Supervise operation-level alignment through an exact session reference, trace, span, or activity stream when the harness exposes one. Do not replace this with lifecycle snapshots or result-artifact inspection. When no direct operational view exists, use `send_message` or another noninterrupting mechanism for bounded polling about the worker's current interpretation, actions, blockers, and verification. This fallback is necessary for supervision, but it can distract the worker and makes the accuracy and truthfulness of its self-report another failure mode; keep requests decision-relevant and corroborate material claims when possible. `followup_task` normally resumes or assigns an idle agent, but can be a minimally disruptive polling fallback when no cheaper reliable mechanism fits and its turn semantics are safe for the unit. If a child needs a material upstream decision and the known reciprocal live channel is unavailable or delay would be long, use a terminal partial return and deliberate resume instead.

Messages, lifecycle state, and terminal agent prose establish coordination facts, not consequential external effects. Establish those effects from task-native evidence on the affected system.

## Bounded session-referenced supervision and reflection

Use `agent-introspect` or the smallest suitable harness-native mechanism for direct worker supervision when it is available. Use an exact normalized worker-session reference already passed or captured by the harness, or resolve the child through lineage or session discovery from the exact parent identity. When lineage lookup requires that identity, establish it with `agent-introspect whoami --json`. Never guess a child identity from cwd, workspace, or recency. Start with metadata, overview, or an operational span and expand only as needed; do not routinely read or paste a full trace. If no exact worker reference can be established, use bounded polling rather than inspect a parent trace and label it worker evidence.

For reflection on the top agent itself at a high-leverage boundary, establish the invoking parent's exact current-session identity with `agent-introspect whoami --json`, then pass its normalized reference to a fresh read-only observer. This reflective use remains optional and sparse.

Ask the observer to locate the current task phase from the reference, begin with recent operations, and expand backward only when needed. It should assess objective alignment, concrete object-level progress, proportionality of coordination, repeated repair, and closeout readiness. Require a short evidence-grounded assessment and at most one intervention.

The observer does not edit files, manage workers, or become persistent. Invoke it sparsely: before increasing coordination complexity, after repeated unsuccessful repair, or before closing a consequential long run. Session metadata, spans, and trace content support reflection only; they do not prove external task effects, which require task-native evidence. This mechanism cannot detect a top agent that never invokes it and is not a liveness guarantee.

## Execution accounting

For repeated live `codex exec --json` operations, use runtime usage events and elapsed or session telemetry when available. Treat missing terminal usage on timeouts or crashes as unknown, and keep cached-input counters distinct from billing and unique work. Do not enforce an execution lease with token, cost, or latency values authored by the model inside its answer.
