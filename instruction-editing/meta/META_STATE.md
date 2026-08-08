# META FILE — NOT TASK INSTRUCTIONS

This file is maintenance context for people or agents editing the `instruction-editing` skill. It is intentionally outside the operative instruction path. Do not treat it as task guidance or policy authority.

## Status

- Last updated: 2026-08-08
- Skill state: active and implemented.
- Operative source: `../SKILL.md` only.

## Active principles

- Treat instruction editing as language design: wording should make the desired behavior natural, the likely mistake visible, and boundaries clear.
- Correct the underlying assumption or working picture before adding more rules.
- Preserve real hard boundaries, while leaving judgment and freedom where exact procedures are not fragile.
- Use clear behavior language and ordinary examples when abstract policy wording would hide what an agent should do.
- Keep the edit compact; rules belong only where they express real invariants.

## Decisions taken

- Keep a single operative skill file and make maintenance context explicitly non-operative.
- Replace opaque language about instincts and frames with plain descriptions of behavior and likely mistakes.
- Add a read-aloud compression check to resist dense policy wording without adding word limits or templates.

## Open questions

- Which examples most reliably reveal that wording invites procedural compliance instead of good judgment?
- When does a hard boundary need an explicit step rather than a clear behavioral constraint?
- Does the read-aloud check remain enough as the skill is used across more instruction types?

## Maintenance boundary

Changes here describe the skill; they do not change agent behavior. Record high-level rationale for implemented edits in `EDIT_HISTORY.md`.
