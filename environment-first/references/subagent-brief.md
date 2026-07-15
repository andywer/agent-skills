# The subagent brief

A dispatch is a small environment you build for a subagent. The brief is what shapes it. A good brief makes the work doable from empty context and the review easy; a bad brief leaks your conversation into the subagent and hides drift. This file is the contract for both the top agent (who writes briefs) and the subagent (who works or reviews under one).

## What a brief must contain

Whether the unit is production or review, the brief is self-contained:

- **Scope** — one specific thing to do, bounded. Not a direction ("look into caching") but a unit ("determine whether the read path caches X, and cite where").
- **Why it matters** — the relevant slice of the objective and how the result will be used. If the unit's instructions seem to conflict with this intent, the subagent flags it rather than guessing.
- **Done condition** — what must be true for the unit to count as complete: acceptance criteria and the checks a reviewer will apply.
- **Return contract** — the exact shape of what comes back: direct edits, a proposal, an answer plus sources, plus any evidence the unit must emit (test transcript, diff, schema-valid file, quoted source). Contracts that force reflection beat "return the answer."
- **Out of scope** — what not to touch. This is how the top agent keeps units from silently growing.
- **Budget** — a bound in units the worker can count: files touched, attempts, tool calls, sources read. Hitting it is a return trigger, not a failure. The top agent may separately enforce an elapsed-time or token ceiling it can observe; label that as an external guard with an explicit accounting basis rather than assigning it to the worker. If the unit may launch repeated, externally metered, materially long-running, or consequential operations, attach an execution lease from `execution-leases.md` to that operation or explicitly prohibit it. A worker budget does not bound the downstream operation it can launch.
- **Fan-out grant** (only when the unit is legitimately wide) — explicit permission for one level of sub-workers: "map over these N items; return only the reduction plus per-item evidence pointers." Absent this grant, no sub-workers.
- **Relevant state** — the specific files or artifacts to read. Not "see the conversation" — name them.

For a repair, name the immutable defect-delta handoff and its verified input/result index. Include only the prior verdict, provenance status, ownership boundary, acceptance checks, and retry/attempt state that the unit needs. The worker retains access to every authorized source required for reasoning; the handoff is not a substitute for that evidence.

If a brief can't be made self-contained without pasting the whole conversation, either the unit is wrong or the needed context is trapped in conversation. Externalize it first: accumulated decisions belong in the game plan's decisions log, where a brief can point at them. Split or re-scope only if the unit still doesn't cohere. Don't fix it by leaking context.

## Empty context by default

Workers and reviewers start from empty context and work only from the brief and the files it names. The value of a fresh context is that it hasn't anchored on anyone's conclusion — that's exactly what makes a review worth having. So:

- Don't hand a worker your reasoning as ambient truth; hand it the task.
- Don't hand a reviewer the worker's rationale, confidence, or a desired verdict as background. If those claims need checking, pass them as **explicitly labeled artifacts to review**, not as briefing.
- Warm continuation is optional and harness-supported, not the default. Permit it only for the same named unit when objective, stage, required/observed provenance, input and artifact identities, model/system instructions, runtime/tool state, mutable environment, ownership boundary, and acceptance contract are unchanged and attestable. Otherwise use a fresh worker. A warm worker cannot review or promote its own work, and any local retirement threshold must be justified by the harness experiment.

## Worker contract

You produce the assigned result; you do not own the plan. A different agent will review your output. Make that review easy.

- Work from the brief and its named files. If the brief is missing something you need, **say so** — that's a brief problem, not something to patch with a guess.
- Produce what the return contract asks for, plus a short summary of what you did and any evidence you generated.
- For an instrumented repair unit, return the unit and attempt identifiers, defect delta addressed, inputs/artifacts consumed, observed provenance, files touched, acceptance results, unresolved mismatches, and any unavailable required field. Cite the immutable handoff; do not rewrite it. For uninstrumented direct work, retain the existing proportionate return contract.
- **Do not expand the unit.** If you find something out of scope, note it as a side finding and let the top agent decide. Don't make broad unrequested edits.
- Anchor claims to observables — the failing check, the quoted source, the exact error — not to introspection about what you think is true.
- When a granted execution lease applies, return the observed accounting basis, units attempted and completed, stop signals, renewal decisions, and unknown counters. Do not substitute self-reported estimates for harness counters.

### When you can't finish

Return early with a **partial result** when you're blocked (a missing fact, an uncooperative environment, a decision only the user can make) or when the unit is simply too big for its budget. Name precisely what's done, what remains, and what would unblock it.

If the unit is too large, **do not promote yourself to orchestrator.** Unless your brief carries an explicit fan-out grant — in which case stay within the granted level and return only the reduction plus per-item evidence pointers — return the partial plus a **decomposition proposal**: how you'd split the remaining work into units. The top agent holds the map and decides whether to split, re-scope, or escalate. A precise partial plus a clean proposal is a good result, not a failure.

### On a revise

A revise verdict names specific things to change. Address each one explicitly, or say why you can't. Don't silently redo the work — that discards the review's signal. Never edit the review verdict; produce repaired or superseding work for a reviewer to assess in a new verdict.

## Reviewer contract

You check a result before the top agent accepts it. You do not produce work product and you do not integrate; you issue a verdict.

- You are a *different* agent from the worker, on a fresh context. If you helped produce the result, recuse.
- You receive: the produced result (edits, diff, proposal, answer, artifacts), the brief that governs it, and the current result surface. You do **not** receive the worker's rationale as truth.
- Walk the done condition. For each criterion: pass, fail, or n/a, with one line of evidence (a path, a quote, an artifact, a command result). Check internal consistency, fit with scope, and whether the required evidence actually exists and actually supports the claim — verify the residue rather than re-deriving it, unless it's missing or suspect.
- Rank evidence honestly: a machine-checked artifact (a passing run, a diff, a validation) outranks your own reading. Your fresh context removes anchoring on the worker's conclusion — it does not remove the blind spots you share with the worker as instances of the same model.
- Issue one verdict: **accept** (sound, ready), **revise** (specific fixable issues — list every one; a revise without a list is hand-waving), or **reject** (fundamentally unsound: wrong scope, bad method, decisive contrary evidence).
- Don't produce the fix yourself, don't soften a verdict to keep things moving, and don't invent issues on a sound result. Put the verdict on disk — not only in chat, and not inside the game plan: closeout rebuilds state from verdicts *without* using the plan, so verdicts must exist independently of it. Treat prior verdicts as append-only evidence; write a new verdict for a repaired result.
