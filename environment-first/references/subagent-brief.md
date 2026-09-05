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

Add a budget only when cost, time, attempts, or blast radius can change continuation. If repeated or metered consequential execution is allowed, attach the relevant execution lease. For a consequential atomic one-shot that can fan out, materially consume a scarce cap, resist safe retry, or leave consequential partial state, attach the reference's bounded-authorization rule instead. A worker's prose budget does not constrain an external operation it launches.

When different interpretations, methods, or workarounds could produce similarly plausible endpoints, ask the worker to surface material changes that could make the result unusable; ordinary choices remain the worker's. Supervise the operations at points where drift could change acceptance rather than judging only the finished artifact.

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

Keep routine narration quiet. Prefer a direct trace, session span, or activity stream for supervision; lifecycle state and produced artifacts answer different questions. When no direct operational view exists, bounded polling becomes vital. Ask only for the current interpretation, actions, blockers, or verification needed for the next judgment. Because polling can distract the worker and makes its self-report another truthfulness and accuracy risk, use the minimum useful cadence, stop when the decision is informed, and corroborate material claims when possible. Treat observation, status requests, follow-up or turn transitions, interruption, and cancellation as distinct operations. Cancel only an explicit authorized stop. If a worker repeatedly drifts or fails, reconsider the unit or approach before retrying.

## Consequence-bounded review

Use a separate fresh reviewer when the result crosses a consequential boundary: irreversible action, protected evidence, high-blast-radius synthesis, difficult semantic judgment, or integration that can introduce new errors. Prefer deterministic verification for mechanical claims.

The reviewer checks the result against the task and evidence, then returns `accept`, `revise`, or `reject` with specific support. It does not produce the fix. Keep the verdict on a durable surface only when later contexts, promotion, or audit must rely on it; otherwise a bounded chat verdict is sufficient.

Do not stack reviews unless each one addresses a distinct live risk. A repair needs re-review of the defect and changed surface, not a ritual replay of every settled question.
