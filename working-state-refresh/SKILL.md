---
name: working-state-refresh
description: Use when the user requests a current-state handoff or when no canonical current-state source can cheaply and safely support the next decision. Default to an inline, transient delta; create or update a durable state artifact only when an ownership or context-loss boundary makes persistence necessary.
---

# Working State Refresh

Use this skill when the current thread cannot safely recover the latest
operational state from canonical sources within a bounded read, or when the user
explicitly requests a handoff, briefing, or current-state summary. Project
complexity or a fresh agent alone is not a trigger.

## Stance

A working-state refresh is not a rewrite and not a defense of prior conclusions. Its job is to surface the latest usable state, name what changed, and make stale assumptions easy to spot.

Treat current docs and recent findings as working state, not ground truth. The job is to reconstruct what the project currently believes, where that belief came from, and what is still in motion.

Keep the refresh readable for the next agent. If the state cannot be understood quickly, the refresh has not done its job.

Identify the canonical current-state source first. If it is usable, do not
reconstruct or mirror it: report only material deltas, conflicts, or stale
claims and point back to the canonical source.

## When To Use

Use this skill when:

- the user asks for a handoff, briefing, or current-state summary;
- no canonical source answers the next decision without reconciling several
  current artifacts;
- recent corrections materially conflict with the recorded current frame; or
- state must cross an ownership or context-loss boundary.

Do not use this skill for a generic summary, merely because a project has many
moving parts, or when a usable canonical source already answers the next
decision. The refresh should be selective, current, and decision-relevant.

## Core Workflow

1. Name the scope of the refresh.
2. Identify the canonical current-state source and the shortest evidence path
   needed to test its freshness.
3. Reconstruct only the unresolved surface and material deltas in plain language.
4. Separate observed facts, working hypotheses, open tensions, and stale assumptions.
5. Identify what changed most recently and why it matters.
6. Name the highest-leverage unresolved questions.
7. Point to the next move that would most improve the working state.

## What To Preserve

A good refresh usually preserves:

- the current objective;
- the latest believed frame;
- key hypotheses and confidence shifts;
- open tensions and disagreements;
- important constraints and boundaries;
- source references to the evidence that supports the refresh;
- the next decision-changing move or largest safe, interpretable step.

## Output Shape

Return the refresh inline and transient by default. Do not create or update a
durable state or handoff artifact unless the user requests it or an ownership
or context-loss boundary makes persistence necessary. A durable refresh must
identify its canonical source, freshness boundary, and non-authoritative role
so it cannot become a competing state surface.

When useful, choose only the sections needed from:

- `Purpose`
- `Latest Working State`
- `What Changed`
- `Key Hypotheses`
- `Open Tensions`
- `Next Move`
- `Source Notes`

Omit empty sections. A durable refresh should let a future agent continue
without reconstructing the whole trail.

## Quality Bar

- The refresh should make the current state easier to navigate than the raw pile of artifacts.
- It should call out uncertainty instead of laundering it into confidence.
- It should not freeze recent opinions into permanent truth.
- It should preserve enough provenance that the next agent can audit the frame if needed.
- It should make the next move obvious without overcommitting to a single branch.
- It should not duplicate a usable canonical state or create a competing authority.
