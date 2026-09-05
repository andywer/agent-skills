---
name: intent-preserving-docs
description: >-
  Write or revise handovers, concepts, implementation briefs, specifications,
  READMEs, and other documentation. Clarify intent, requirements, assumptions,
  choices, and change authority without silently altering commitments.
---

# Intent-Preserving Documentation

Give the reader a working picture they can act from: what matters, why, what is true now, and what they may change. Preserve the distinctions that govern decisions, not every detail of the discussion.

**Improving a document is not permission to redesign what it describes.** Match the work to the request; a small edit should stay small.

## Understand the job

Read the current text and relevant sources. Separate the reader’s task from your editing mandate: you may be clarifying a successor’s permission to redesign without having that permission yourself.

Distinguish requirements, implemented behavior, and proposals. Newer prose does not automatically supersede an accepted decision. Keep material conflicts and uncertainty visible rather than resolving them for a cleaner narrative.

## Make commitments and freedom clear

Explain intent, commitments, implications under stated assumptions, and current realization.

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

For concepts and handovers, open with the title and a short essence: problem, intended outcome, and distinguishing idea. Walk downstream into implications and mechanisms. Begin substantial sections with their main point; keep rationale, change latitude, and checks nearby. Cross-reference shared constraints rather than forcing a strict tree.

Preserve useful existing structure. Runbooks need guards before actions; references need easy lookup. Do not impose one outline or metadata scheme everywhere.

Keep history only where it changes what the reader should do. Record consequential decisions with their reason, material alternative, and reopening condition; a separate ledger is optional. Use an acceptance scenario or tempting wrong shortcut where abstract wording leaves a dangerous ambiguity. A passing example is not proof of the whole requirement.

## For handovers

Make the next meaningful action possible. Carry forward **North Star**—destination and core constraint—and **Now**—assignment, current state, and main risk. Distinguish implemented, tested, proposed, and unfinished work. Include protected boundaries, useful artifact entry points, blockers or paused actions, and the next decision or coherent work slice.

Check that essential references are accessible to the successor. For costly or ambiguous work, use a brief receiver preflight: first action and why, what must remain intact, and what may be simplified. Do not require routine approval or a long paraphrase.

## Check the result

Can the reader choose the right next action, reject an attractive but invalid shortcut, and use the freedom granted? Check the motivating case and an ordinary unrelated edit. Remove repetition and ceremony. Flag material unresolved issues without claiming unperformed verification.
