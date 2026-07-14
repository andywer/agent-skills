---
name: exploration-map
description: Structured recursive decomposition of complex, open-ended questions into a persistent map with scored branches, evidence tracking, and contradiction handling. Use when multiple plausible answers or approaches must be compared, especially for decisions under uncertainty, strategy, research, prioritization, complex debugging or multi-hypothesis root-cause analysis, conflicting artifacts, or pushback on an initial answer. Skip straightforward implementation, lookup, routine debugging, or small decisions.
---

# Exploration Map

Use a recursive map to make the search process visible: seed adjacent branches, deepen the most valuable frontier, track evidence and contradictions, revise the current answer, and switch to validation when more abstraction is no longer useful. Scores steer attention; they are not evidence.

## Start and working state

Activate this skill only when the question deserves recursive exploration. At activation, create a task-local `MAP.md` before substantive exploration and persist it through the end of the task. Compact and full modes change density, not whether `MAP.md` exists. If the task is too small for a map, do not activate this skill.

Use compact mode for a genuinely map-worthy question with few branches and one or two expected iterations; keep every section terse. Use full mode when branches survive scrutiny, evidence may conflict, the decision is hard to reverse, or the question needs repeated frontier work.

Start solo. Do not estimate complexity in advance to choose orchestration. Escalate only when observed runtime pressure shows either:

- the live frontier contains disjoint assignments that are each valuable; or
- the source or state load can no longer be handled reliably in one context.

Treat `MAP.md` as the authoritative working state across compaction or restart. Source artifacts remain authoritative evidence. After compaction or restart, re-read `MAP.md` and every referenced source artifact before continuing. The main agent is the sole writer of `MAP.md`; workers return deltas for the main agent to synthesize.

Do not add dispatch directories, JSON protocols, fixed critique cadences, separate budget files, or other orchestration machinery. Revisit defaults only after the same failure recurs across comparable runs, not after one anomaly.

## Build the map

Create `MAP.md` with these sections, in this order. Keep every section; write `none yet` rather than omitting one.

1. **Root question** — quote the user's question verbatim, then record constraints and the analysis as-of date. Never paraphrase the root question.
2. **Current Best Answer** — one provisional paragraph with confidence and the specific finding that would change it.
3. **Tree** — recursive nodes with stable hierarchical IDs.
4. **Evidence register** — each load-bearing claim with type, level, source, and as-of date.
5. **Contradiction ledger** — conflicts between evidence or conclusions, open or resolved.
6. **Gaps** — unexplored or unresolved angles.
7. **Iteration log** — one line per iteration describing the selected frontier and the change.
8. **Appendix: archived branches** — pruned nodes and their kill reasons; never reuse IDs.

Seed the first adjacent nodes, such as options, affected parties, success criteria, root problems, capabilities and limits, candidate solutions, and validation paths. Give important nodes children or an explicit terminal reason. Use the node format below and keep the tree relational rather than a flat list:

```markdown
- [N2.3] Title (P:4 A:2 | frontier)
  rationale: P4 because X versus sibling N2.1; A2 because blocked on Z
  risk: downside=med, reversible=yes, deadline=none
```

Use stable IDs such as `N1`, `N1.2`, and `N1.2.1`. Score Promise (P) and Actionability (A) from 0–5, with a one-line rationale comparing a named sibling. Add risk fields for decisions. Keep evidence level separate from promise and actionability; a promising branch may still be unvalidated or blocked. See [scoring.md](references/scoring.md).

## Explore and update

For each iteration:

1. Select one frontier item by value of information: likely change to the Current Best Answer per unit effort. Break ties by deadline, then downside if wrong. Do not select by raw promise alone.
2. Choose `breadth` when alternatives may be missing, `depth` when one branch needs mechanism or risks, or a `sidecar` when the next uncertainty needs bounded evidence, validation, or an artifact.
3. Expand the selected node, gather or verify evidence, or resolve a contradiction. Label claims as `fact`, `inference`, or `hypothesis`.
4. Update the tree, evidence register, contradiction ledger, score revisions, Current Best Answer, gaps, and one iteration-log line. Never silently overwrite a score or conclusion.
5. Run the anti-flatness check: each iteration must deepen, reconcile, or reframe the map, not merely append siblings.

Before promoting a sidecar, record required data, the direct access path, credible proxy evidence, and the condition that blocks progress. A decision-relevant frontier should end in a state such as `validated enough to pilot`, `needs proxy evidence`, `blocked pending access`, `defer / switch branch`, or `handoff artifact ready`. If further abstraction is lower-value, switch to the sidecar, proxy check, data request, pilot plan, prototype, or other concrete artifact instead of stopping early. See [sidecars.md](references/sidecars.md).

When workers are justified, give each only the verbatim root question, one branch, and relevant evidence. Require findings, evidence items, contradictions, score changes with rationales, and blockers. Synthesize once in `MAP.md`; do not paste worker output wholesale. See [escalation.md](references/escalation.md).

## Stop, switch, and review

Stop abstract expansion when new branches mostly repeat existing ones, the ranking is stable after challenge, the remaining uncertainty is empirical, or the leading branch is blocked and no credible proxy move is available. Continue in execution mode whenever a runnable validation or handoff artifact remains.

Stop the whole loop only when the Current Best Answer is stable, no open contradiction could change it, every material gap is explored or explicitly accepted, and the next required action is unavailable or the validation-enabling artifact exists. If the deciding evidence is unavailable, state `blocked` and why; do not turn an assertion into a confident answer.

For ordinary solo work, perform one lightweight final self-challenge: steelman the strongest rival, invert the most fragile load-bearing assumption, and identify the weakest or stalest load-bearing evidence. Record any finding in `MAP.md` before finalizing.

Use a fresh reviewer only when multiple agents contributed to a load-bearing conclusion, the decision is high-downside or irreversible, material evidence remains disputed or stale, or the user requests independent verification. The reviewer returns one verdict: `ACCEPT`, `REPAIR`, `REOPEN`, or `BLOCKED`. A localized defect permits one bounded repair followed by re-review; a structural gap reopens exploration.

## Limits

Use practical limits of at most 12 iterations and 40 active nodes unless the user supplies different limits. When the active-node cap is reached, archive the weakest branch with a rationale before adding more. If a run hits a limit, report the current answer and open items rather than continuing silently.

Before delivery, check that high scores have comparative rationales, load-bearing claims have evidence levels and dates, contradictions are not silently resolved, sidecars have a concrete next action or blocked condition, and the final answer is derived from `MAP.md`.

## References

- [scoring.md](references/scoring.md) — Promise, Actionability, evidence levels, staleness, and risk fields.
- [sidecars.md](references/sidecars.md) — verification, adversarial, reframe, and frame-escape moves.
- [example.md](references/example.md) — compact worked map and conflicting-artifact variant.
- [escalation.md](references/escalation.md) — optional delegation and fresh-review guidance.
