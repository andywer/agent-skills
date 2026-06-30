---
name: working-state-refresh
description: Use when a project, subject, or workstream needs its latest working state reconstructed from current docs, logs, and artifacts so another agent can continue without carrying stale assumptions.
---

# Working State Refresh

Use this skill when the current thread has drifted away from the latest operational state, when a project has many moving parts, or when a fresh agent needs a compact but honest handoff before continuing.

## Stance

A working-state refresh is not a rewrite and not a defense of prior conclusions. Its job is to surface the latest usable state, name what changed, and make stale assumptions easy to spot.

Treat current docs and recent findings as working state, not ground truth. The job is to reconstruct what the project currently believes, where that belief came from, and what is still in motion.

Keep the refresh readable for the next agent. If the state cannot be understood quickly, the refresh has not done its job.

## When To Use

Use this skill when:

- a project has accumulated many notes, logs, and pivots;
- the latest working state is spread across several artifacts;
- the user asks for a handoff, briefing, or current-state summary;
- recent corrections may have shifted the frame;
- a self-documenting subject needs its latest state refreshed;
- the next move depends on distinguishing current belief from old context.

Do not use this skill for a generic summary of all available material. The refresh should be selective, current, and decision-relevant.

## Core Workflow

1. Name the scope of the refresh.
2. Read the most recent source artifacts first: project docs, indexes, logs, decisions, and recent corrections.
3. Reconstruct the latest working state in plain language.
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
- the smallest useful next step.

## Output Shape

Prefer a compact handoff with sections like:

- `Purpose`
- `Latest Working State`
- `What Changed`
- `Key Hypotheses`
- `Open Tensions`
- `Next Move`
- `Source Notes`

The refresh should be self-documenting: a future agent should be able to read it and continue work without reconstructing the whole trail.

## Quality Bar

- The refresh should make the current state easier to navigate than the raw pile of artifacts.
- It should call out uncertainty instead of laundering it into confidence.
- It should not freeze recent opinions into permanent truth.
- It should preserve enough provenance that the next agent can audit the frame if needed.
- It should make the next move obvious without overcommitting to a single branch.
