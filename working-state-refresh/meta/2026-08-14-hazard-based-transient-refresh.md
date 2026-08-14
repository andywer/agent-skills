# META FILE — NOT TASK INSTRUCTIONS

This dated note records maintenance rationale for the `working-state-refresh`
skill. It is not operative guidance or policy authority and should not be
loaded during ordinary skill use.

# 2026-08-14 Hazard-Based, Transient Refresh

## Summary

`working-state-refresh` was narrowed from a broad complexity or fresh-agent
trigger to a decision need: use it when the user requests a current-state
handoff or no canonical source can cheaply and safely support the next
decision.

The default output is now an inline, transient delta. A usable canonical state
is referenced rather than reconstructed; durable state is created only for a
real ownership or context-loss boundary. The next-action language now prefers
a decision-changing move or the largest safe, interpretable step.

## Motivation

Recent operational evidence showed that repeated state reconstruction,
collectors, packets, and parallel summaries could delay value-changing work
and create competing stale authorities. The prior skill wording was compatible
with that failure because project complexity or a fresh agent was enough to
trigger a full refresh.

## Boundaries Preserved

- Honor explicit requests for handoffs, briefings, and current-state summaries.
- Reconstruct state when no usable canonical source exists or material
  conflicts must be reconciled.
- Preserve provenance, uncertainty, important constraints, and hard boundaries.
- Permit a durable handoff when ownership transfer or context loss makes
  persistence valuable.

## Rejected Overcorrections

The revision does not trust a stale canonical source, prohibit necessary
durable handoffs, remove evidence pointers, or weaken safety and authority
boundaries. It removes duplicate-state defaults, not state recovery itself.

## Promotion Rule

If a second materially different behavioral correction later needs
preservation, consolidate dated notes into a compact `EDIT_HISTORY.md`. Add
`META_STATE.md` only if the skill gains multiple operative references,
unresolved maintenance questions, or interacting decisions that cannot be
understood from `SKILL.md` plus edit history.
