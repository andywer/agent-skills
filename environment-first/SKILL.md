---
name: environment-first
description: "Use for complex or error-compounding work — deep research, multi-source analysis, refactors, audits, migrations, or tasks where hidden state, consequential risk, delegation, repeated execution, or deferred obligations can make an early mistake expensive. Keep the top agent lean: preserve intent, choose the next value-changing action, accept results, and close. Work directly when that is simplest; add durable state, delegation, provenance, transactional handling, execution leases, or independent review only when a concrete hazard calls for them."
---

# Environment-first

Shape the environment enough that important mistakes are hard to hide, then spend attention on the work. The environment serves the objective; maintaining it is never the objective.

## Start with the smallest sufficient environment

Work directly when the task is clear, local, reversible, and comfortably fits one context. Inspect only the tools, permissions, inputs, mutable state, and result surfaces the task will actually touch. Perform ordinary task-proportionate verification. Do not create a plan, packet, checklist, reviewer, or ledger merely because the skill triggered.

Add a control only for a concrete hazard:

- externalize acceptance-critical obligations when context loss or delay could hide them;
- give delegated work a bounded brief;
- protect irreplaceable or accepted results transactionally;
- require provenance when downstream work depends on an evidence class;
- lease repeated work when it consumes material time, budget, capacity, or consequential mutations;
- use independent review when semantic judgment or integration is consequential;
- use joinable receipts only when asynchronous or comparative execution actually needs them.

If a hazard is only suspected, take one cheap reversible probe. If it is known, activate the relevant control immediately. Drop a control when its trigger no longer applies. Never preserve a heavy operating mode merely because it began.

## Keep the top agent a lean executive

Preserve the user's intent, choose the next action likely to change the answer, accept or reject results, and decide when to close. Perform object-level work directly when that is the simplest reliable path. Delegate bulky, separable work when another context adds real value.

Manage by exception. Intervene when a result returns, a blocker appears, scope changes, execution becomes unsafe, or an independent reflection identifies drift. Do not turn the top context into a control room that continuously watches workers, narrates status, or maintains operational history.

Do not delegate a responsibility merely to make the top context look lean. Remove work that supplies no decision, evidence, safety, or user value.

## Maintain only the orientation the work needs

When work may outlive a comfortable context, keep a short, revisable projection:

- **Done** — accepted results and discharged obligations, with evidence pointers when needed.
- **Still missing** — required outcomes not yet established.
- **Blocked or deferred** — only when relevant, with what would change the disposition.
- **Next** — the current disposable recommendation.

Use ordinary prose. Rewrite the projection when reality changes; it need not preserve history or encode every transition. Source artifacts and evidence remain authoritative on their natural surfaces. Externalize a decision only when another context or later action must rely on it.

If an action changes neither `Done`, `Still missing`, nor the evidence supporting them, treat that as a possible sign of ceremony. Simplify, reorient, return partial work, or close rather than elaborating the control system.

Use `references/game-plan.md` only when a durable orientation is genuinely needed. Add acceptance-critical pointers or join state only when compaction, dependent handoffs, or asynchronous work makes reconstruction consequential.

## Shape consequential work, not every step

Probe the real environment before relying on an interface, permission, isolation claim, mutable input, or promotion path. Reuse a valid existing environment or result lineage after checking identity, freshness, and scope.

Make a critical check structural when omission would affect safety or acceptance: require the producer to return the evidence, and verify it at the boundary where the result is used. Prefer deterministic checks for mechanical claims. Use a different fresh context for a consequential semantic challenge; do not add semantic review where an adequate deterministic check already settles the claim.

Protect accepted and irreplaceable result surfaces: write candidates separately, validate them, then promote. Before an unavoidable in-place transformation of irreplaceable data, create and verify a rollback copy.

For provenance gates, asynchronous joins, protected promotion, and transactional details, read `references/coordination-controls.md` only when one of those hazards is present. For repeated or metered consequential execution, read `references/execution-leases.md` before the first unit.

## Delegate shallowly and deliberately

Prefer one active worker when one is enough. Parallelize disjoint work only when the join is cheap and clear. A brief may live in the dispatch message; create a durable packet only when it must survive context loss, cross an ownership boundary, or support later audit or promotion.

Give a worker the unit's scope, why it matters, what done means, what is out of scope, the relevant sources, and the evidence to return. Add a budget only when cost, time, attempts, or blast radius can change the decision. See `references/subagent-brief.md` when the dispatch is consequential or non-trivial.

When materially different interpretations or methods could reach similarly plausible endpoints, a finished-looking delegated result can still be insufficient. Obtain one cheapest useful early signal that the work remains directed at its intended use—such as a small result-surface check, a concise interpretation or method reflection, or a decision-relevant intermediate—then leave routine work autonomous. This is neither liveness evidence nor proof of task effects; assess those separately from their natural surfaces. Do not turn it into mandatory checkpoints, decision diaries, or status cadence.

Use context freshness selectively:

- keep the same worker warm for a bounded repair when the objective and result surface are unchanged;
- use a fresh context when independence is the point — consequential review, frame challenge, or materially different work;
- never let a producer self-promote across a protected or consequential boundary.

Keep routine coordination quiet. A nonblocking informational update may state a fact, milestone, or reply; it neither needs acknowledgement nor pauses work or creates an approval gate. A question that needs a decision is a decision request, not an informational update. Do not conflate passive observation, a lightweight status request, a follow-up or turn transition, interruption, and cancellation: they have different delivery and disruption semantics. When silence becomes decision-relevant through an actual anomaly, missed task-specific window or milestone, absent expected evidence, changed decision, or accumulating risk, choose the cheapest reliable probe whose information value plausibly exceeds its disruption. A one-off lightweight status message or minimally disruptive follow-up can be appropriate; do not create heartbeat or polling loops. Observe work without changing it when the environment supports that; observation is not cancellation. Stop work only for an explicit, authorized cancellation, never merely to obtain status. Do not infer that an unavailable child-to-parent decision channel makes a parent-to-child liveness probe useless. After repeated failure on the same issue, reconsider the unit or approach instead of adding repair machinery.

When observed reality makes a brief boundary conflict with its intent, or two reasonable readings would materially change scope, safety, acceptance, or verification, stop at a safe boundary before inventing a workaround. A child that needs an upstream decision may use a live decision request only on an already-known capability set that provides noninterrupting bidirectional delivery and passive waiting; otherwise, including a terminal-only or unconfirmed interface or a long delay, return `AWAITING_ORCHESTRATOR` as a terminal partial and resume deliberately. This portable fallback for child-originated decisions does not prohibit a parent from making a proportionate liveness probe. For Codex live-coordination mechanics, read `harness-defaults/codex-gpt-5.6.md`. Hold the unit, answer or revise the brief, and resume the same worker and context when the unit remains materially unchanged. This is exception handling, not a status channel.

Use independent review at consequential promotion boundaries, not by default for every result. Keep the verdict durable only when later work must rely on it across contexts or when auditability matters. The reviewer remains separate from the producer and receives the task, result, relevant surface, and evidence — not a desired verdict as ambient truth.

## Use sparse operations reflection

On long or agent-heavy work, occasionally delegate a fresh read-only review of the top agent's operations at a high-leverage decision boundary: before increasing coordination complexity, after repeated unsuccessful repair, or before closing a consequential run.

Ask the observer to assess objective alignment, concrete progress, proportionality of the operating approach, and closeout readiness, then return a short evidence-grounded assessment and at most one intervention. The observer does not manage workers, maintain project state, or become persistent. This is an aid to reflection, not a liveness guarantee; the top agent remains responsible for invoking it.

Use harness-native call-by-reference when available. For Codex, follow the bounded session-reference guidance in `harness-defaults/codex-gpt-5.6.md`; do not paste a trace tail into the parent context.

## Execute the minimum loop

Repeat only this:

1. Identify what required outcome is still missing.
2. Choose the cheapest safe action likely to change it or its evidence.
3. Work directly or delegate one bounded unit.
4. Validate the result in proportion to its consequence.
5. Update the short orientation when the answer materially changes.
6. Continue, return partial work, or close.

Re-read the objective when work starts expanding sideways, repairs repeat, or the user has to correct the operating process. Change the approach before adding structure.

## Close proportionately

Close when every required item is done or explicitly returned as blocked, deferred, or partial, and the user-facing result has been delivered. Optional work does not keep the run open.

Re-read the objective and compare it with the result and supporting evidence. Reconstruct from artifacts only when the maintained orientation is stale or the work must survive handoff. Use a fresh final reviewer when the assembled whole contains consequential integration risk not already settled by adequate checks; do not require one merely because delegation or another control was used.

See `references/closeout.md` for proportionate closeout and final-review triggers.

## Hard boundaries

- Preserve user control, permissions, protected boundaries, and destructive-action safeguards.
- Externalize an obligation when forgetting it would change safety or acceptance.
- Do not dispatch vague intent or let delegated work silently broaden its scope.
- Do not let a worker self-promote across a consequential boundary or edit an independent verdict it is repairing against.
- Keep producer and reviewer separate when independent review is required.
- Do not infer completion, provenance, or safety from silence, a successful command, or a receipt alone.
- Do not add coordination structure without a concrete hazard and a reason to remove it later.
- Do not let maintaining the environment displace the objective.

## References

- `references/game-plan.md` — minimal durable orientation and reconstruction rule.
- `references/subagent-brief.md` — bounded briefs, selective freshness, worker returns, and consequence-bounded review.
- `references/coordination-controls.md` — transactional results, provenance gates, and conditional join/receipt handling.
- `references/execution-leases.md` — repeated, metered, materially long-running, or consequential batch execution.
- `references/closeout.md` — proportionate closeout and final-review triggers.
- `harness-defaults/codex-gpt-5.6.md` — Codex live coordination, routing, and trace-referenced reflection guidance.

Read a reference only when its trigger applies.
