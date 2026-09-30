# Scoring rubrics

Use these rubrics only when explicit scoring materially improves comparison; ordinary prose is sufficient otherwise. Scores are relative within the map, not evidence or acceptance gates. Explain the tradeoff when it changes the choice; no named-sibling rationale is required for every score.

## Promise (P)

How much would this branch matter if it worked?

- **5** — would settle the root question or dominate the decision
- **4** — major contributor; resolving it could change the Current Best Answer
- **3** — meaningful but partial; shifts confidence
- **2** — minor refinement
- **1** — weakly connected
- **0** — dead, contradicted by L2+ evidence, or out of scope; archive it

Score Promise assuming the branch pans out. Put uncertainty about whether it pans out in the evidence level.

## Actionability (A)

How cheaply can progress be made now?

- **5** — resolvable this iteration with material in hand
- **4** — resolvable with one cheap probe
- **3** — needs moderate cross-referencing or a small model
- **2** — blocked on something obtainable, such as requested data
- **1** — blocked on slow or external work
- **0** — not resolvable within the session; mark blocked, do not prune

Keep Actionability separate from Promise. A high-promise branch can be blocked.

## Evidence ladder (L0–L4)

- **L0 — asserted:** stated without a source; useful for scaffolding, never load-bearing for the Current Best Answer
- **L1 — single-source:** traced to one artifact, document, or dataset
- **L2 — cross-verified:** confirmed by at least two independent sources
- **L3 — reconciled:** conflicting sources were logged and resolved, or retained as an explicit range
- **L4 — tested against reality:** supported by an experiment, held-out check, or observed real-world outcome

These labels can describe existing maps, but their numbers are not a universal ranking of evidence strength. Judge what the actual source and method establish: a direct measurement may settle a question that several correlated summaries cannot. Require evidence adequate to the claim and consequence, not a fixed source count or ladder level.

## Staleness and risk

Check dates when the facts may have changed. Reverify consequential stale information or qualify the conclusion; do not assign artificial half-lives to every source.

When they affect the decision, these optional fields may help:

- `downside`: `low`, `med`, or `high` if wrong
- `reversible`: `yes` or `no`
- `deadline`: a date or `none`

Use these considerations to choose the next useful check and the evidence needed. Preserve reasons for consequential changes in the answer; do not maintain a log of every score revision.
