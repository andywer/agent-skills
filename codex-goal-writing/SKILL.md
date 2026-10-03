---
name: codex-goal-writing
description: Draft or revise /goal statements at the requested level—high-level objectives, bounded task contracts, or autonomous-session charters—while keeping essential success conditions and constraints self-contained.
---

# Codex Goal Writing

A goal states what should become true. It is not automatically a plan, runbook,
or prompt containing every useful instruction. Make it self-contained enough to
preserve the user's intent without prescribing mechanics that do not define
success.

## Choose the Kind of Goal

Before drafting, distinguish three independent questions:

1. **Abstraction:** Does the user want the desired outcome, or an operational
   contract for pursuing it?
2. **Work type:** Is the work implementation, validation, investigation,
   review, planning, cleanup, decision support, or outcome selection?
3. **Autonomy horizon:** Is this one bounded task or a longer autonomous
   session that may need pivots and continuation?

Do not use one answer as a proxy for another. In particular, “big” or
“high-level” normally describes the scope or abstraction of the objective; it
does not by itself request a detailed autonomous-session charter.

Use the lightest form that matches the request:

- **High-level objective:** State the desired end state and the condition by
  which success can be recognized. Include only indispensable scope or
  authorization boundaries. Avoid methods, commands, delegation, intermediate
  artifacts, telemetry, and procedural stop rules unless one of them actually
  defines the outcome.
- **Bounded task contract:** State the outcome, relevant constraints, and proof
  of completion for one unit of work. Add tooling or artifacts only when the
  user specified them or consistency is load-bearing.
- **Autonomous-session charter:** State the mission-level outcome, meaningful
  boundaries, proof boundary, and continuation or stopping conditions needed
  for an agent to work across multiple attempts without relying on conversation
  history. Use this form when the user asks for an autonomous run, a time-boxed
  session, or continued work through pivots—not merely because the objective is
  large.

If the user explicitly says to describe the goal rather than how to reach it,
write a high-level objective.

## Drafting

1. Identify what would make the requested task or mission genuinely complete.
2. Include the success condition or decision boundary at the same level of
   abstraction as the request.
3. Preserve hard constraints whose omission could materially change the work,
   such as scope, privacy, external permissions, destructive-action limits, or
   an unavailable proof gate.
4. Pull in only context that is costly to rediscover. Link supporting documents
   when they carry detail that does not belong in the goal.
5. Add methods, harnesses, models, delegation, artifacts, telemetry, tests,
   budgets, and continuation rules only when the user requested an operational
   contract or when a particular item is essential to the outcome or proof.

Follow explicit user and project routing when tooling belongs in the goal. Do
not establish a global model, provider, harness, or command default in this
generic skill.

Treat recent conclusions as evidence to re-check, not constraints to preserve.
Do not default to implementation merely because the user asks for a `/goal`.

Before making verification a completion condition, ask whether it actually
proves the goal and whether it is locally available. If proof depends on live
credentials, private-data authorization, device access, or another external
gate, mention that gate only when it changes what completion means.

## Useful Shapes

For a high-level objective:

```md
/goal <Make the desired end state true>. Success means <observable outcome or
decision boundary>. <Essential constraint, if any>.
```

For an empirical objective:

```md
/goal Determine whether <claim> holds under <relevant conditions>, reaching a
defensible <decision or verdict> before <consequential next step>.
```

For a bounded task contract:

```md
/goal <Complete the bounded outcome>. Preserve <load-bearing constraints>.
Verify completion with <proof that actually closes the task>.

See `<supporting-doc.md>` for details if needed.
```

For an autonomous-session charter:

```md
/goal Advance <mission> until <mission-level judgment or outcome> is
defensible, the next decision-changing step is not worth its budget, or a real
access boundary prevents further progress.

Preserve <hard boundaries> and persist <evidence needed across attempts>.
Treat intermediate results as evidence for the next choice rather than as
automatic completion.
```

These are shapes, not mandatory fields. Omit clauses that do not earn their
place in the requested kind of goal.

## Quality Bar

- The goal should be understandable without the prior conversation, but
  self-contained does not mean exhaustive.
- The level of prescription should match the request: an objective describes
  the destination; a contract may also describe load-bearing execution rules.
- Success should be recognizable without inventing incidental proxy metrics.
- High-level wording may be concise and abstract, but should not collapse into
  vague aspirations such as “improve” or “make robust.”
- Do not encode uncertain current facts as fixed instructions. Verify them when
  they are decision-critical, or express the uncertainty in the goal.
- Distinguish implementation progress from proof of completion and hard
  requirements from optional refinements.
- Mention budget or resource behavior only when it materially bounds the work.
- Do not write the goal to a file unless the user explicitly asks.

Before returning the draft, test it against the request: if the user asked only
for the outcome, remove any sentence that primarily tells the agent how to get
there.
