---
name: exploration-map
description: "Use for complex, open-ended questions requiring comparison of alternatives: strategy, research, prioritization, decisions under uncertainty, complex debugging or multi-hypothesis root-cause analysis, conflicting artifacts, and challenged conclusions. Also reconstruct exploration maps from prior discussions, session logs, or artifacts. Organizes branches, evidence, and contradictions to guide the inquiry. Skip routine implementation, lookup, debugging, small decisions, and ordinary summaries."
---

# Exploration Map

Use a map to retain competing explanations or options, the evidence that distinguishes them, and what would change the answer. It is a guiding representation for an inquiry: it can live in working memory, appear inline in conversation, or be saved in a note. The map serves the decision; producing or maintaining a document is not progress by itself.

For retrospective reconstruction, use [reconstruction.md](references/reconstruction.md) instead of inventing new exploration. Preserve recorded uncertainty and distinguish later analysis from the historical inquiry.

## Keep the useful reasoning recoverable

Start with the actual question, plausible alternatives, relevant evidence and uncertainty, and the next observation likely to change the answer. Choose the map's lifetime and location for the work. Keep it ephemeral when the active context is sufficient. Persist the useful parts when the user requests an artifact or when handoff, coordination or later resumption needs a durable account. Reuse a relevant decision note or save a focused note for that inquiry; `MAP.md` is an optional filename, not a required central project asset. Separate inquiries can have separate maps, with links to shared evidence where useful. Do not create a file merely because this skill is active.

Use ordinary prose or bullets to show how alternatives, subquestions, evidence and objections relate. Deepen a branch when its mechanism or assumptions matter; preserve that relationship in the map. Avoid a flat topic list that loses the reasoning, but do not add hierarchy merely to fill a tree. Fixed sections, node IDs, numeric scores, evidence enums, iteration logs and separate registers are optional: use one only when a concrete navigation, comparison or recovery need cannot reasonably be met more simply. Preserve existing IDs when other material links to them.

Keep the user's question and constraints faithful; quote exact wording when it matters. Link load-bearing claims to the evidence supporting them and distinguish observations from explanations. Keep unresolved contradictions and meaningful rejected alternatives visible, without copying the full history into each update.

The map is working state, not primary evidence. Before a handoff or context-loss boundary, preserve the reasoning needed to continue if it is not already recoverable from the conversation or maintained artifacts. After compaction or restart, recover the relevant map from the available context or notes, re-read governing documentation, and inspect the source material needed for the next decision or conflict. Do not assume ephemeral context survived or reread every linked artifact automatically. Integrate worker findings into the inquiry's current map; a shared file is needed only when it helps coordination.

## Investigate what could change the decision

Choose the next comparison, probe or source read by its likely effect on the answer. Explore another alternative when the current framing may be incomplete; examine a mechanism when it explains a concrete observed failure. Do not invent branches merely to make the tree deeper or wider.

For design and review, test necessity as well as correctness: what tangible contribution does each proposed or existing component, specification, rule, helper or format make, and could the objective reasonably be achieved without it or with something simpler? Demonstrate a claimed defect on an in-scope case before optimizing its repair. Keep untested concerns as hypotheses.

When remaining uncertainty is empirical, run the appropriate bounded check rather than expand the map. Establish needed access and permissions, but record a separate access plan only if coordination or later recovery needs it. See [sidecars.md](references/sidecars.md) for optional ways to challenge or verify an answer.

Update the working map when evidence changes the answer, an important alternative, or the next action; update a saved note when that change needs to survive the current inquiry. Preserve consequential reversals and their reasons; do not log each tool call or score revision. Use [scoring.md](references/scoring.md) only if explicit scoring would materially improve comparison.

## Delegate and review when they add value

Work directly unless separate context or parallel work provides a concrete benefit. Follow the user's delegation instructions. Workers need the question, one bounded assignment and relevant sources; their return can be findings, evidence and remaining uncertainty in ordinary prose. See [escalation.md](references/escalation.md).

Challenge the answer with a credible rival or an observation that could falsify it. Use an independent reviewer when unresolved judgment or integration risk could materially change the decision, or when required by the user. Delegation alone does not require another reviewer. A review should explain any defect and its consequence; it needs no fixed verdict vocabulary or automatic re-review cycle.

Stop exploration when the evidence is adequate for the decision in scope, or when the missing evidence cannot currently be obtained. State the material uncertainty and next action; do not require every imaginable gap to be closed. Continue authorized execution when it is the useful next step. Respect task budgets and stop when further investigation has little decision value; do not create node or iteration accounting merely to manage the map.

## References

- [reconstruction.md](references/reconstruction.md) — recover a prior inquiry without rewriting its history.
- [scoring.md](references/scoring.md) — optional comparative scoring and evidence judgment.
- [sidecars.md](references/sidecars.md) — concrete verification and challenge moves.
- [example.md](references/example.md) — a short map with competing explanations.
- [escalation.md](references/escalation.md) — bounded delegation and independent review.
