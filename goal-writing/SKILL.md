---
name: codex-goal-writing
description: Use when drafting a /goal for Codex or OpenCode autonomous work, especially when the goal must be concise but self-contained, preserve important context, reference supporting documents, and steer an agent without relying on conversation history.
---

# Codex Goal Writing

Draft goals that are self-contained work contracts for Codex or OpenCode. Match the goal's size to the user's intended autonomy horizon: sometimes the right goal is one bounded task, and sometimes it is a session charter that lets an agent work through multiple leases, pivots, and evidence branches without relying on conversation history. Include the critical constraints, intended behavior, verification expectations, and key artifact paths directly in the goal.

## First Size The Goal

Before drafting, decide two things:

1. Work type: implementation, validation, investigation, review, planning, cleanup, decision support, or outcome selection.
2. Autonomy horizon: bounded task or autonomous-session charter.

Use a bounded task goal when the user wants one clear unit of work.

Use an autonomous-session charter when the user asks for a big/high-level goal, an autonomous session, a 30-45 minute run, hours/days of work, or a mission objective that may require multiple leases, research passes, implementation fixes, reruns, or frontier switches.

Do not inflate ordinary tasks into session charters. But when the user wants a session charter, do not let the first frontier, first artifact, first failed check, or first successful decision define completion. State how the agent should continue after a path is killed, exhausted, blocked, or lower-value than another path.

For session charters, make the finish line feel like a real session close, not the first useful waypoint. A lease that changes confidence is usually a new signpost: re-rank the frontier and keep moving. End only when the agent can defend the requested session-level judgment, when the next best lease is not worth its budget, or when budget/access prevents the next decision-changing move.

Do not default to implementation just because the user asks for a `/goal`. Treat recent conclusions as evidence to re-check, not constraints to preserve. A good `/goal` should encode the next highest-value autonomous outcome at the right granularity, not the smallest cleanly completable task.

## Workflow

1. Identify the autonomous outcome and horizon: what would make the next task or session genuinely complete?
2. Pull in only the essential context from current docs, code, lessons, and recent findings; cite volatile findings through artifact paths rather than freezing them as conclusions.
3. State the default harness when relevant. Do not hard-code an OpenCode model unless the task is explicitly about comparing or overriding models; the project default should choose DeepSeek v4 Flash through local config/auth/env:

```sh
opencode run --agent build
```

4. Include links to deeper docs only as backup, not as the primary source of truth.
5. Name required artifacts, telemetry, tests, and stop conditions.
6. For task goals, keep completion tied to the bounded unit of work. For session charters, include continuation criteria and mission-level stop conditions.

## Goal Shape

Prefer this compact structure:

```md
/goal <Do the next concrete autonomous task>.

Use <default harness/tooling> unless blocked.

Do <core behavior>. Preserve <critical constraints>. Persist <artifacts/telemetry>. Verify with <tests or smoke run>.

See `<supporting-doc.md>` for details if needed.
```

For empirical or decision-oriented work, prefer a shape like:

```md
/goal Validate whether <concept/system> works under <conditions> before adding new machinery.

Use <default harness/tooling> unless blocked.

Run <existing workflow or study>. Compare against <baselines>. Preserve <hard constraints>. Make only minimal fixes required to complete the study. Persist <artifacts/evidence>. Conclude with <decision label or next action>.

See `<supporting-doc.md>` for details if needed.
```

For uncertain-path work, use this shape sparingly:

```md
/goal Find the lowest-cost reliable way to resolve <uncertainty/problem>, then execute that approach.

Use <default harness/tooling> unless blocked.

Compare plausible paths, choose the one with the best decision-relevant confidence gain within the available budget, carry it out deeply enough to change, bound, or retire the uncertainty, and persist the reasoning, evidence, artifacts, telemetry, and final recommendation. Allow code changes only when they are needed for the chosen path.

See `<supporting-doc.md>` for details if needed.
```

For uncertain-path goals, optimize for decision-relevant confidence gain within the available budget, not for the cheapest satisfiable artifact. A lean local check is good when it can change, bound, or retire the uncertainty; if it cannot, choose a stronger bounded path or state that the next decision-changing move needs more budget, access, or approval.

For autonomous-session charters, prefer a shape like:

```md
/goal Advance <mission/objective> through a bounded autonomous session. Start from <first frontier/path/artifact>, but do not treat that starting point as the whole scope.

Use <default harness/tooling> unless blocked.

Run an incremental loop: inspect current evidence, choose the highest-value frontier, execute bounded leases, update confidence, and re-rank after each material result. Treat useful findings as signposts, not finish lines. Continue until the requested session-level judgment is defensible, the next best lease is not worth its budget, or budget/access blocks further decision-changing work.

Persist evidence, decisions, telemetry, intermediate artifacts, and a final mission-level recommendation. Verify code changes with <tests>.
```

## Quality Bar

- The goal should be understandable without reading the prior thread.
- Include all non-obvious constraints that would be costly to rediscover.
- Distinguish hard requirements from optional refinements.
- Mention budget/resource behavior when the task touches agentic processing.
- Avoid vague instructions such as "improve", "make robust", or "think carefully" unless paired with concrete mechanisms.
- For session charters, completion should be mission-level; the first successful or failed lease is evidence for the next decision, not automatically the end of the goal.
- Do not write the goal to a file unless the user explicitly asks.
