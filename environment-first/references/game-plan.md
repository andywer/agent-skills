# Minimal durable orientation

Use this reference only when the work may outlive a comfortable context, has acceptance-critical deferred obligations, or must survive a handoff. Do not create an orientation file for a short direct task.

The orientation is a compact projection, not an event history, orchestration dashboard, or semantic completeness proof. Its job is to let the current or next context answer: what is established, what remains required, what is blocked, and what action is most likely to move the answer?

## Default shape

```md
# <objective in one line>

## Done
- <accepted result or discharged obligation> — evidence: <pointer when needed>

## Still missing
- <required outcome not yet established>

## Blocked or deferred
- <item> — reason; what would change the disposition

## Next
<one disposable recommendation>
```

Omit empty sections. Add the authoritative result surface or an acceptance criterion only when another context would otherwise be unable to reconstruct them.

Do not add a roster, complete backlog, narrated history, status ticks, review transcript, or speculative branch tree. Keep detailed evidence, source content, and work products on their natural surfaces. When asynchronous or dependent execution requires joinable attempt or lineage state, follow `coordination-controls.md` and add only the fields the join actually consumes.

## Update moments

Update the orientation when:

- an accepted result changes `Done`;
- a required obligation opens, closes, blocks, or is deliberately deferred;
- evidence changes what can be claimed;
- the current next action stops being the best route;
- a handoff or imminent compaction requires a current projection.

Do not update it for every tool call, worker status, or intermediate observation. Rewrite stale prose instead of preserving superseded wording for audit value.

## Reconstruction

The orientation is a projection of reality, not the source of truth. If it appears stale, if the result surface changed without an orientation change, or if another context must take over, reconstruct `Done` and `Still missing` from the objective, accepted artifacts, evidence, and any consequential verdicts. Compare once, repair the projection, and continue or close. Do not create a parallel reconstruction ledger.

If maintaining the orientation takes attention comparable to the object-level work, shrink it. If an action changes neither `Done`, `Still missing`, nor their evidence, reconsider whether that action is useful.
