---
name: instruction-editing
description: Use when editing prompts, AGENTS.md files, role instructions, shared policies, or operational agent docs. Helps revise wording by correcting the agent's mistaken mental model, preserving hard boundaries, and avoiding bureaucratic rule accretion.
---

# Instruction Editing

Use this skill when the requested change affects how agents think or behave.

## Stance

Instruction editing is language design, not rule accumulation. The wording is the mechanism: choose words for the reflex they create in the next agent, what feels natural, what feels costly, and what feels obviously out of scope.

Good instruction wording gives the agent a working image. If the sentence sounds bureaucratic, it will invite bureaucratic behavior; if it carries the right image, the checklist can stay short.

Keep edits compact while correcting the real frame. A tiny patch that leaves the wrong mental model intact is not lean; it is under-editing.

Prefer:

- sharper vocabulary over longer rule lists;
- revising the mistaken frame over adding exceptions;
- concrete behavior deltas over abstract policy ceremony;
- lightweight stance-setting language over checklists unless exact steps are truly fragile;
- hard constraints where they exist, high-leverage guidance where they help, and freedom elsewhere.

## Before Editing

Read the current instruction text and the nearest evidence: recent user feedback, relevant lessons, frontier state, run logs, commits, or reports.

Name the mistaken frame before changing text. Common frames:

- current baseline mistaken for a hard boundary;
- product-code change mistaken for approval by default;
- role-local stop mistaken for autonomous-session stop;
- local progress mistaken for verified completion;
- an external access or approval gate mistaken for more local work to grind through;
- abstract challenge language drifting away from lived product behavior;
- branch or state file treated as ceremony rather than a handoff aid.

Name the intended reflex and the nearby wrong reflex before changing text.

## How To Edit

Revise the smallest section that carries the mistaken frame. If the same idea appears in several files, align the vocabulary instead of adding a competing rule.

Before adding requirements, ask whether the instruction already has enough rules but evokes the wrong working picture. If so, rewrite the stance or central metaphor first. A good edit should make the desired behavior feel obvious before it makes noncompliance impossible.

Watch for checklist patching: adding sections, schemas, stop rules, or validation bullets while leaving the agent's default posture unchanged. Use schemas only after the motivating frame is clear, and keep them as rails for execution rather than substitutes for judgment.

Preserve hard boundaries explicitly: user control, destructive changes, source anchors, fetch-before-claim, candidate-only limits, reviewed-core authority, non-transfer, release/merge/publication, and external permissions.

When guidance risks becoming abstract, ground it with ordinary behavior categories: what the system would read, write, allow, refuse, show, validate, or hand off.

Use `LESSONS_LEARNED.md` only for durable lessons from the edit, not every wording tweak.

## Validation

After editing, read the final wording from the perspective of the agent who will consume it:

- Does it provoke the right instinct?
- Would the first read of the new wording pull a capable agent toward the intended behavior before it reaches any checklist?
- Would a capable agent reading this imagine the right kind of work before reaching the checklist?
- Does it preserve freedom for strong models?
- Does it avoid micromanaging where judgment is better?
- Does it keep the real hard boundaries visible?
- Did you check the edit against the motivating failure, a normal use case, and the opposite failure mode?
