---
name: intent-preserving-docs
description: >-
  Write or revise handovers, concepts, implementation briefs, specifications,
  and READMEs when intent, commitments, assumptions, or change authority need
  clarification. Preserve meaning while making the reader's next decisions
  actionable. Not for formatting-only edits, agent instruction design, or
  reconstructing current working state from multiple or conflicting sources.
---

# Intent-Preserving Documentation

Give the reader a working picture they can act from: what matters, why, what is true now, and what they may change. Preserve the distinctions that govern decisions, not every detail of the discussion.

**Improving a document is not permission to redesign what it describes.** Match the work to the request; a small edit should stay small.

## Understand the job

Read the current text and relevant sources. Separate the reader’s task from your editing mandate: you may be clarifying a successor’s permission to redesign without having that permission yourself.

Use this skill for the meaning and decision guidance in the document. Format-specific skills handle artifact mechanics; `instruction-editing` handles agent behavior; `working-state-refresh` handles reconciling current state across sources. Combine them only when the task needs both jobs.

Distinguish governing instructions and decisions from observations, proposals, and historical summaries. Supersession depends on authority and scope: an explicit user revision can replace an earlier decision; a newer summary cannot do so merely by being newer. Preserve material conflicts or unknowns that the available authority and evidence do not resolve.

## Make commitments and freedom clear

Where the distinction affects action, make clear:

- **Why it exists:** explicit requirement, inferred consequence, deliberate scope narrowing, or selected mechanism.
- **What may change:** protected for this assignment, replaceable within boundaries, or reconsidered when a stated condition changes.
- **What supports it:** instruction, observation, bounded test, or hypothesis.

A contingent choice can still be binding. Exact interfaces or architectural shapes may be protected, especially when testing a particular design. Missing rationale is not permission to remove a commitment.

For example: “Single-worker operation is fixed v1 scope; do not add concurrency. JSONL is replaceable if restart recovery and inspection remain intact.” This guides simplification better than “keep it simple.” Establish these distinctions from sources; do not invent them.

## Simplify at the right level

For editorial work, preserve conditions, exceptions, relationships, and source links. Do not turn “may” into “must,” a proposal into a decision, or “deferred” into “rejected.”

When authorized to simplify the concept, challenge the overall arrangement before defending its parts. Try removing, merging, postponing, or replacing major sources of complexity. Ask what required behavior, binding commitment, or demonstrated benefit a simpler alternative would lose.

Prefer lower total implementation, operating, verification, and maintenance burden—not merely fewer components. Do not manufacture necessity from a plausible connection to a goal: “A requires property B; C is our current way to provide B” leaves room for alternatives. State the least-complex option justified so far, not that no simpler solution exists.

## Organize for the reader

For a new concept or handover, or an authorized substantial restructuring, a short statement of the problem, intended outcome, and distinguishing idea can orient the reader before implications and mechanisms. Use equivalent content and labels that fit the document. Keep rationale, change latitude, and checks near the claims they qualify; cross-reference shared constraints where helpful.

Preserve useful existing structure and the scope of a small edit. Runbooks need guards before actions; references need easy lookup. The reader's task determines the organization, not a fixed opening, outline, or metadata scheme.

Bring history into the active narrative where it changes what the reader should do. Preserve consequential decisions and their known rationale, material alternatives, and reopening conditions without inventing missing ones. Use an acceptance scenario or tempting wrong shortcut where abstract wording leaves a consequential ambiguity. A passing example is not proof of the whole requirement.

## For handovers

Make the next meaningful action possible. Carry forward the destination and core constraint alongside the current assignment, state, and main risk; these are content needs, not required headings. Distinguish implemented, tested, proposed, and unfinished work. Include protected boundaries, useful artifact entry points, blockers or paused actions, and the next decision or coherent work slice where they matter to continuation.

Check essential references within available access and state any access limits. For costly or ambiguous work, read the handover as the successor: can you identify the first action and why, what must remain intact, and what may be simplified? Repair gaps from available sources. This is an editorial readiness check, not a required exchange with the receiver or an approval gate.

## Check the result

Read the revision against the requested task and its sources: can the reader choose the next action, avoid a plausible invalid shortcut, and use the freedom actually granted? Check for changed commitments, lost conditions, or unsupported certainty. For a small edit, keep this review local to the change; do not create unrelated edits, test artifacts, or receiver interactions just to validate the prose. Remove repetition and flag material unresolved issues without claiming unperformed verification.
