# The game plan

The game plan is the one artifact the top agent maintains instead of remembering. It holds the live state of the work: where you are, what's next, what's deferred, and what must be true to finish. It is coordination state, not the work product and not a full project plan.

Keep it small. It should be the minimum a fresh context needs to answer: *what is happening right now, what happens next, and what still has to happen before this is done?* If it grows past what you'd want to re-read on every step, it's carrying detail that belongs in the result surface or a subagent brief instead.

Store it wherever it will survive and be re-read — a file next to the result surface, a scratch file in the working directory, or, for compact full-mode runs, a maintained section of the top agent's own working notes. What matters is that it is a single authoritative place, not scattered reminders.

## Shape

```md
# Game plan: <objective in one line>

## Objective
<the concrete outcome, not just the activity — one short paragraph>
Result surface: <where the real work lands: repo / doc / dataset / deliverable path>

## Constraints
- <macro-environment limit found in the survey: missing tool, sandbox boundary, guardrail, access gap> — implication for the work

Preflight receipt: <exact runtime/interface and compatibility; authoritative inputs; mutable state; candidate and accepted result paths; permissions; promotion and rollback semantics; inherited context/state when isolation matters>

For work that triggers the compact-index rule, add only the fields needed by that task: `Frontier: <current unit, status, next action, blocker, acceptance-critical pointers, and relevant provenance/environment state>` and, when asynchronous joins are material, `Attempts/joins: <unit and attempt identifiers, required completion evidence, and unresolved/unavailable fields>`. Do not add these fields to a short direct task. The index is not a semantic completeness proof; rebuild from artifacts when it is stale or incomplete.

Decision frontier, only when later work depends on an unresolved result or an execution lease is triggered: <next decision; load-bearing prerequisite; cheapest safe evidence that can change it>

## Now
<the single concrete step in progress, expanded enough to act on>
Budget / return contract if this is a live dispatch: <bound + what must come back>
Execution lease, only when triggered: <operational proving unit; decision pilot when needed; continuation question; result-stop policy or none + reason; batch order/size; accounting source; cumulative cap; spent; operational stop signals; renewal owner; latest health/spend/decision renewal>

## Next
- <high-level next step>
- <high-level next step>
(prose-level; expand one into "Now" when it becomes active)

## Deferred / backlog
- <action noticed but not yet due> — why it matters, what makes it relevant
- <deferred action>

## Decisions
- <choice made during the run that later units must stay consistent with> — one-line rationale

## Conditional coordination

Use receipt and join detail only when asynchronous delegation, dependent promotion, protected-boundary risk, or an explicit need for comparative or joinable execution evidence makes it useful. Otherwise a normal dispatch note, result pointer, and proportionate review are enough. Where instrumentation is enabled, distinguish retries from duplicate events, record unpaired or unavailable states, and use verified polling if the harness cannot join events. Update the index at natural state changes rather than on every status tick.

## Closeout checklist
- [ ] <thing that must be true / done before declaring done>
- [ ] <deferred action promoted here once it's an exit condition>
- [ ] fresh-context final check passes

## Open questions / missing inputs
- <fact, access, or decision not yet resolved> — what would close it

## Done / dropped
- <completed step> — evidence: <pointer to real artifact>
- <dropped step> — reason
```

Not every section is always needed. A short run may have only Objective, Now, Next, and the closeout checklist. Add sections when the work produces content for them, not preemptively.

## When to update

Update at the natural moments, not on a timer:

- a step completes (move it to Done with an evidence pointer);
- a deferred action appears (write it to Deferred immediately — this is the point of the artifact);
- a deferred action becomes an exit condition (promote it to the closeout checklist);
- a macro constraint is discovered (write it to Constraints — a limit that stays in your head is the failure this skill removes);
- a decision is made that later units must honor (write it to Decisions, so briefs can point at it instead of leaking conversation);
- the plan turns out wrong (revise Next; if the *objective* was wrong, stop and rewrite Objective explicitly);
- before closeout (see the rebuild rule).

If result artifacts change while the game plan does not, stop new dispatches and reconcile the plan from the artifacts before continuing.

Recording a dispatch counts as an update: when you send a unit to a subagent, write it into "Now" or "Next" with its budget and return contract *at dispatch time*, so an abandoned or floundering unit stays visible instead of vanishing.

## The rebuild rule

The game plan is a projection of reality, not the source of truth. It will drift.

Before closeout — and periodically on long or high-risk runs — reconstruct the current state from the durable artifacts alone: the result surface, produced files and evidence, and review verdicts, which live on disk *outside* this plan precisely so this rebuild can use them. Do the reconstruction *without* using the existing game plan as input, then compare against the plan. A divergence in what's done, what's open, or what the evidence shows is a finding — including a unit the plan says was dispatched with nothing on disk to show for it, which is how an abandoned dispatch gets caught. Reconcile before proceeding, and treat the fact that it drifted as information about how closely you've actually been tracking.

## Keep it lean

If the plan is getting long, compress finished and future work to one line each and keep only the active part in detail. A game plan you dread re-reading is one you'll stop maintaining — and an unmaintained plan is worse than none, because it looks authoritative while lying.
