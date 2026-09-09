# META FILE — NOT TASK INSTRUCTIONS

This file is maintenance context for people or agents editing the `instruction-editing` skill. It is intentionally outside the operative instruction path. Do not treat it as task guidance or policy authority.

## Status

- Last updated: 2026-09-09
- Skill state: active and implemented.
- Operative source: `../SKILL.md` only.

## Active principles

- Treat instruction editing as behavioral design through language.
- Match prescription to the document's job and judge concision on the complete result, not the size of the diff.
- Diagnose the instructions' contribution before changing them: repair mistaken framing when supported, clarify another defect, or leave guidance unchanged when evidence does not justify an edit.
- Keep guidance actionable at its intended level: principles direct judgment, procedures stabilize fragile sequences, and requirements state invariants.
- Preserve real hard boundaries while leaving judgment and freedom where mechanics are not load-bearing.
- Resist both checklist patching and aphorism collapse.

## Decisions taken

- Keep a single operative skill file and make maintenance context explicitly non-operative.
- Replace opaque language about instincts and frames with plain descriptions of behavior and likely mistakes.
- Retain the read-aloud compression check, but make clear that compression must not remove the workflow or boundary that makes guidance actionable.
- Treat genre and intended decisions as evidence to discover from the document's use, not as a mandatory template inferred from its title.
- Do not invent a behavioral diagnosis for routine maintenance or assume every reported failure warrants an instruction change. No change is a decision about the evidence for editing, not proof that the instructions are adequate.
- Consolidate overlapping guidance before adding more. This revision uses one transferable contrast instead of incident catalogs; that is not a ban on examples that expose a missed decision or boundary.
- Keep ordinary validation mental and proportional; use behavioral testing when it could change acceptance of a consequential revision.

## Evidence and open tensions

[PR #5](https://github.com/andywer/agent-skills/pull/5) reduces the operative skill from
846 to 357 whitespace-delimited words, including front matter. Initial text review of
[the 350-word revision](https://github.com/andywer/agent-skills/blob/b59abddf7b57c004292f92d21b43a372d8de8bbd/instruction-editing/SKILL.md)
against the recorded August/September failure modes found no concrete lost
requirement. Neither that review nor the reported mental walkthroughs establish
that shorter instructions improve reliability; no model-backed comparison was run.

- Does removing the catalogs weaken recognition of framing errors, procedural compliance, actionless slogans, or evidence boundaries? Retain examples for their discriminating value, not their count.
- When does a hard boundary need an explicit step rather than a clear behavioral constraint?

## Maintenance boundary

Changes here describe the skill; they do not change agent behavior. Record high-level rationale for implemented edits in `EDIT_HISTORY.md`.
