---
name: instruction-editing
description: Use when editing prompts, AGENTS.md files, role instructions, shared policies, or operational agent docs. Helps revise wording by correcting the agent's mistaken mental model, preserving hard boundaries, and avoiding piling up unnecessary bureaucratic rules.
---

# Instruction Editing

Use this skill when the requested change affects how agents think or behave.

## Stance

Instruction editing is language design, not rule accumulation. The wording is the mechanism: choose words that make the desired behavior feel natural, the likely mistake easy to notice, and the boundaries obvious.

Good instruction wording gives the agent a working image. If the sentence sounds bureaucratic, it will invite bureaucratic behavior; if it carries the right image, the checklist can stay short.

Keep edits compact while correcting the underlying assumption or working picture. A tiny patch that leaves the wrong mental model intact is not lean; it is under-editing.

Prefer:

- sharper vocabulary over longer rule lists;
- revising the mistaken frame over adding exceptions;
- clear changes in behavior over abstract policy ceremony;
- a short description of how the agent should approach the work over checklists unless exact steps are truly fragile;
- hard constraints where they exist, high-leverage guidance where they help, and freedom elsewhere.

## Before Editing

Read the current instruction text and the nearest evidence: recent user feedback, relevant lessons, frontier state, run logs, commits, or reports.

Name the mistaken frame before changing text. Common frames:

- current baseline mistaken for a hard boundary;
- product-code change mistaken for approval by default;
- one worker stopping mistaken for the whole session being finished;
- local progress mistaken for verified completion;
- an external access or approval gate mistaken for more local work to grind through;
- abstract wording that no longer matches what users actually experience;
- branch or state file treated as ceremony rather than a handoff aid.

State the behavior the instruction should encourage and the likely mistake it should prevent.

## How To Edit

Revise the smallest section that carries the mistaken frame. If the same idea appears in several files, align the vocabulary instead of adding a competing rule.

Before adding requirements, ask whether the instruction already has enough rules but evokes the wrong working picture. If so, rewrite the stance or central metaphor first. A good edit should make the desired behavior clear before it relies on strict rules to prevent mistakes.

Watch for checklist patching: adding sections, schemas, stop rules, or validation bullets while leaving the agent's default posture unchanged. Use schemas only after the motivating frame is clear, and keep them as rails for execution rather than substitutes for judgment.

Preserve hard boundaries explicitly: user control, destructive changes, source anchors, fetch-before-claim, candidate-only limits, reviewed-core authority, non-transfer, release/merge/publication, and external permissions.

When guidance risks becoming abstract, ground it with ordinary behavior categories: what the system would read, write, allow, refuse, show, validate, or hand off.

## Validation

After editing, read the final wording from the perspective of the agent who will consume it:

- After one read, is the desired behavior easy to picture and the common mistake easy to recognize?
- Read it aloud. If it sounds like a policy memo or tries to preserve every concern as a clause, compress it. Keep rules only for real invariants.
- Does it preserve freedom for strong models?
- Does it avoid micromanaging where judgment is better?
- Does it keep the real hard boundaries visible?
- Did you check the edit against the motivating failure, a normal use case, and the opposite failure mode?
