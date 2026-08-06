# Bounded subagent briefs

Use a subagent when separate context adds real value: the work is bulky, self-contained, independently verifiable, or needs an unanchored challenge. Work directly when the brief would cost as much context as the unit saves.

A brief may be an inline dispatch message. Make it durable only when it must survive compaction, cross an ownership boundary, support later promotion, or remain auditable.

## What the worker needs

Give the worker:

- **Scope** — one bounded result to produce.
- **Intent** — why it matters and how the result will be used.
- **Done** — the acceptance condition and evidence that must return.
- **Boundaries** — what not to touch or decide.
- **Sources** — the exact files, artifacts, interfaces, or links needed.

Add a budget only when cost, time, attempts, or blast radius can change continuation. If repeated or metered consequential execution is allowed, attach the relevant execution lease; a worker's prose budget does not constrain an external operation it launches.

Do not require a schema, packet file, receipt, or full conversation reconstruction unless a real downstream consumer needs it.

## Context freshness is a tool

Keep a worker warm for repair of the same bounded unit when the objective, sources, result surface, permissions, and acceptance condition remain materially unchanged. Give it the specific defect and required correction; do not rebuild the whole packet merely to preserve ceremony.

Use a fresh context when independence is the point: consequential review, frame challenge, or materially different work. A fresh reviewer receives the governing task, current result, relevant result surface, and evidence. Do not provide the producer's confidence or desired verdict as ambient truth.

Freshness does not compensate for missing sources, an incoherent unit, or a weak verification rule.

## Worker return

Return:

- the requested result or edits;
- the evidence named by the brief;
- a short statement of what remains uncertain or blocked.

Stay inside scope. Return a partial result when the unit cannot finish, naming what is done, what remains, and what would unblock it. Do not silently become an orchestrator. Fan out only when the brief explicitly permits bounded, disjoint sub-work and names the reduction expected back.

Keep routine coordination quiet. A nonblocking informational update may state a fact, milestone, or reply; it neither needs acknowledgement nor pauses work or creates an approval gate. A question that needs a decision is a decision request, not an informational update. Continue ordinary work after it; stop only at a material decision, safety, scope, acceptance, or evidence boundary.

When an observed fact makes a brief boundary conflict with its intent, a material workaround or scope expansion would be required, or two reasonable readings would produce materially different accepted results, stop safely before proceeding. A worker that needs an upstream decision may use a live decision request only on an already-known capability set that provides noninterrupting bidirectional delivery and passive waiting; otherwise, including a terminal-only or unconfirmed interface or a long delay, return `AWAITING_ORCHESTRATOR` as a terminal partial. Include only the conflicting instruction and observation, the smallest viable options and consequences, the safe partial state, and a recommendation.

The parent answers or revises the brief, then resumes the same worker and context when the objective, sources, result surface, permissions, and acceptance condition remain materially unchanged. Otherwise return the partial as blocked and re-dispatch deliberately. Do not pause for routine status, optional refinements, questions already answered by the brief, or ambiguity that does not change acceptance, blast radius, or verification.

On repair, address the named defects or explain precisely why one cannot be addressed. Do not edit an independent verdict; produce repaired or superseding work.

## Management by exception

Await ordinary work without mandatory updates. Treat passive observation, a lightweight status request, a follow-up or turn transition, interruption, and cancellation as distinct operations. When silence becomes decision-relevant through an actual anomaly, missed task-specific window or milestone, absent expected evidence, changed decision, or accumulating risk, use the cheapest reliable probe whose information value plausibly exceeds disruption; a one-off status message or minimally disruptive follow-up can be appropriate. Observe passively when the environment supports it; observation does not pause or cancel the worker. Cancel only an explicit, authorized stop, not a status check. Do not infer that an unavailable child-to-parent decision channel makes a parent-to-child liveness probe useless. Avoid heartbeat and repeated polling loops. If a worker fails repeatedly on the same issue, reconsider the unit, evidence, or approach before retrying again.

## Consequence-bounded review

Use a separate fresh reviewer when the result crosses a consequential boundary: irreversible action, protected evidence, high-blast-radius synthesis, difficult semantic judgment, or integration that can introduce new errors. Prefer deterministic verification for mechanical claims.

The reviewer checks the result against the task and evidence, then returns `accept`, `revise`, or `reject` with specific support. It does not produce the fix. Keep the verdict on a durable surface only when later contexts, promotion, or audit must rely on it; otherwise a bounded chat verdict is sufficient.

Do not stack reviews unless each one addresses a distinct live risk. A repair needs re-review of the defect and changed surface, not a ritual replay of every settled question.
