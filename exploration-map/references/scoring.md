# Scoring rubrics

Scores are relative within the map, not absolute. A rationale that does not name a sibling is incomplete.

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

The Current Best Answer needs L2+ support for load-bearing claims. A branch with `downside=high` and `reversible=no` needs L3+ before it can support the answer.

## Staleness and risk

Give every evidence item an `as-of` date and a half-life: `stable`, `quarters`, `weeks`, or `days`. Mark it **STALE** when one half-life has passed relative to the analysis date. Stale evidence keeps its level but cannot be the sole support for a load-bearing claim.

For decisions, record:

- `downside`: `low`, `med`, or `high` if wrong
- `reversible`: `yes` or `no`
- `deadline`: a date or `none`

These fields affect frontier selection and the minimum evidence needed. Score revisions must state the node, field, old and new values, and the evidence or contradiction that caused the change. Re-read both affected branches before accepting a revision that changes the Current Best Answer.
