# Codex + GPT-5.6 defaults

Use these defaults when this skill is running in the Codex harness with GPT-5.6.
The orchestrator agent should preferrably run `gpt-5.6-sol` or similar, due to its critical role, at least for complex tasks and tasks with a large blast radius.

## Default subagent assignments

- Worker subagents: `gpt-5.6-luna` at high reasoning.
- Reviewer subagents: `gpt-5.6-luna` at high reasoning; `gpt-5.6-sol` at high reasoning for the final review if the task's blast radius is substantial.
- Research subagents: `gpt-5.6-luna` at medium reasoning.

## Specialist consultation

Workers and reviewers may consult a `gpt-5.6-sol` subagent at high reasoning when their assigned unit turns on a complex question or decision. The delegating agent remains responsible for the worker result or reviewer verdict.

## Codex execution accounting

For repeated live `codex exec --json` operations, use runtime usage events and
elapsed/session telemetry when available. Treat missing terminal usage on
timeouts or crashes as unknown, and keep cached-input counters distinct from
billing and unique work. Do not enforce an execution lease with token, cost, or
latency values authored by the model inside its answer.
