# Codex + GPT-5.6 defaults

Use these defaults when this skill is running in the Codex harness with GPT-5.6.

## Route by task fit, not role prestige

Use a plausible efficient model for ordinary bounded work. Escalate after an observed gap or when a load-bearing specialist, synthesis, or review risk justifies it. Treat model tier and price as resource labels rather than capability boundaries.

For consequential routing or evaluation design, consult the dated capability map at `~/.codex/model-capabilities/README.md`, refresh fields that may be stale, and run a small canary on the actual task and evaluator. Do not turn this evidence discipline into ceremony for normal work.

Do not assign a stronger model merely because it is the top agent. The top agent should remain a lean decision and integration point; use specialist capability where the task actually needs it.

## Live coordination

In this Codex harness, when exposed for the relevant agents, `send_message` provides noninterrupting bidirectional delivery and `wait_agent` provides passive mailbox waiting; use `list_agents` for passive lifecycle snapshots. Do not assume every child context exposes that full set. Passive observation, a status message, a follow-up or turn transition, interruption, and cancellation remain different operations when only a subset is available. Use `interrupt_agent` only for an explicit, state-changing cancellation.

Keep routine work quiet. A nonblocking informational update may state a fact, milestone, or reply and does not require acknowledgement, pause work, or open an approval gate. A decision request is separate: use it only at a material decision, safety, scope, acceptance, or evidence boundary. When decision-relevant silence follows an actual anomaly, missed task-relative window or milestone, absent expected evidence, changed decision, or accumulating risk, prefer the cheapest reliable probe whose information value exceeds its disruption. Use `send_message` for a one-off status request when available. `followup_task` normally resumes or assigns an idle agent, but can be a one-off minimally disruptive status or turn probe when no cheaper reliable mechanism fits and its turn semantics are safe for the unit. Do not turn either into routine chatter. If a child needs a material upstream decision and the known reciprocal live channel is unavailable or the delay would be long, use a terminal partial return and deliberate resume instead. The absence of that child-to-parent channel does not make parent-to-child liveness probes categorically useless.

Messages, lifecycle state, and terminal agent prose establish coordination facts, not consequential external effects. Establish those effects from task-native evidence on the affected system.

## Bounded session-referenced operations reflection

When a long or agent-heavy run reaches a high-leverage reflection boundary, optionally use `agent-introspect` as a Codex optimization when it is available. For reflection on the top agent itself, establish the invoking parent's exact current-session identity with `agent-introspect whoami --json`, then pass its normalized reference to a fresh read-only observer. For direction inspection of a delegated worker, do not treat that `whoami` result as the child: use an exact normalized worker-session reference already passed or captured by the harness, or resolve the child through lineage or session discovery from the exact parent identity. Never guess a child identity from cwd, workspace, or recency. Start metadata, overview, or an operational span against the selected target, expand only as needed, and do not routinely read or paste a full trace. If no exact worker reference can be established, use another cheap task-native or worker-supplied directional signal rather than inspect a parent trace and label it worker evidence. If the tool or adapter is unavailable, use the smallest suitable harness-native reference mechanism instead; this is not a hard dependency.

Ask the observer to locate the current task phase from the reference, begin with recent operations, and expand backward only when needed. It should assess objective alignment, concrete object-level progress, proportionality of coordination, repeated repair, and closeout readiness. Require a short evidence-grounded assessment and at most one intervention.

The observer does not edit files, manage workers, or become persistent. Invoke it sparsely: before increasing coordination complexity, after repeated unsuccessful repair, or before closing a consequential long run. Session metadata, spans, and trace content support reflection only; they do not prove external task effects, which require task-native evidence. This mechanism cannot detect a top agent that never invokes it and is not a liveness guarantee.

## Execution accounting

For repeated live `codex exec --json` operations, use runtime usage events and elapsed or session telemetry when available. Treat missing terminal usage on timeouts or crashes as unknown, and keep cached-input counters distinct from billing and unique work. Do not enforce an execution lease with token, cost, or latency values authored by the model inside its answer.
