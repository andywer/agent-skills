---
name: instruction-editing
description: Use when editing prompts, AGENTS.md files, role instructions, shared policies, operational principles, or other agent guidance. Revise the wording so it matches the document's job, enables the intended decisions, corrects mistaken working models, and preserves hard boundaries without procedural overfit.
---

# Instruction Editing

Use this skill when the requested change affects how agents think or behave.

## Stance

Instruction editing is behavioral design through language. Match the wording to the document's job and useful level of prescription: principles direct judgment, procedures stabilize fragile sequences, and requirements state real invariants. Do not turn workflow guidance into slogans merely to make it shorter, or principles into recipes merely to make them testable.

The wording is the mechanism. Choose words that make the desired behavior natural, the likely mistake easy to notice, and the boundaries obvious. A working picture is useful only when the consuming agent can act from it: the text should guide the next choice while leaving freedom over mechanics that do not carry the outcome.

Keep edits compact while correcting the underlying assumption or working picture. A tiny patch that leaves the wrong mental model intact is not lean; more rules are not necessarily more actionable.

Prefer:

- a concrete working picture that transfers beyond the motivating case, rather than denser vocabulary or longer rule lists;
- revising the mistaken frame over adding exceptions;
- guidance that changes choices over abstract policy ceremony or agreeable prose;
- enough workflow to direct action, without prescribing incidental mechanics;
- hard constraints where they exist, guidance where judgment matters, and freedom elsewhere.

## Before Editing

Read the current instruction text and the nearest evidence: recent user feedback, relevant lessons, frontier state, run logs, commits, or reports.

Identify the document's function, the decisions it must enable, the freedom it should preserve, and the mistaken frame that produces the current behavior. Do not infer these from the title alone. Common mistaken frames:

- current baseline mistaken for a hard boundary;
- product-code change mistaken for approval by default;
- one worker stopping mistaken for the whole session being finished;
- local progress mistaken for verified completion;
- an external access or approval gate mistaken for more local work to grind through;
- a principles file mistaken for either an algorithmic recipe or a collection of slogans;
- branch or state file treated as ceremony rather than a handoff aid.

## How To Edit

Revise the smallest section that carries the mistaken frame. If the same idea appears in several files, align the vocabulary instead of adding a competing rule.

Make the document actionable at its intended level. Communicate direction, decision criteria, and meaningful boundaries; prescribe mechanics only where their consistency protects the result.

Before adding requirements, ask whether the instruction already has enough rules but evokes the wrong working picture. If so, rewrite the stance or central metaphor first. A good edit should make the desired behavior clear before it relies on strict rules to prevent mistakes.

Watch both failure modes. Checklist patching adds machinery while leaving the default posture unchanged. Aphorism collapse removes so much workflow that an agent can agree with the wording but cannot use it to act. Use schemas only when exact structure is load-bearing, and memorable language in service of action rather than as a substitute for it.

Preserve hard boundaries explicitly: user control, destructive changes, source anchors, fetch-before-claim, candidate-only limits, reviewed-core authority, non-transfer, release/merge/publication, and external permissions.

When guidance risks becoming abstract, make the decision visible through a concrete, ordinary contrast or example. Generalize the relationship it exposes, not the motivating case's nouns: the example should illuminate the guidance, not become its hidden scope. Use exact wording when the document's role makes it load-bearing, as with a hard boundary, interface contract, or fragile procedure.

## Validation

Read the final wording from the perspective of the agent who will consume it:

- Can the agent use it to choose or change course, or does it merely sound sensible?
- Does its prescription match the document's job without becoming a recipe or a slogan?
- Is the desired behavior easy to picture and the common mistake easy to recognize?
- Read it aloud. If it sounds like a policy memo or a case-specific postmortem, recast it as the concrete relationship the reader should notice without losing a load-bearing workflow or boundary.
- Does it preserve freedom for strong models while keeping real hard boundaries visible?
- Did you test it against the motivating failure, an unrelated ordinary case, and the opposite failure mode or document role?
