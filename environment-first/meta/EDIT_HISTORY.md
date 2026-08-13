# META FILE — NOT TASK INSTRUCTIONS

This file is a high-level maintenance history for the `environment-first` skill. It is not operative guidance and must not be loaded as a task instruction source. Entries summarize implemented changes and their rationale; they are not diffs.

## 2026-08-09 — Put a smoke test before the consequential live run

Added a compact working image under claim validation: before consuming a
protected, held-out, scarce, or acceptance-bearing live run, send a harmless
specimen through the same path that makes the claim true. A surrogate proves
only what it exercises, and approval stops at the claim the evidence supports.

Why: a structurally accepted inference harness used its consequential proving
unit as the first live exercise of the model-facing path. The failure was not a
reviewer claiming general runtime readiness; the structural verdict authorized
spending the real unit before a cheap live canary had crossed the missing
boundary. The new wording corrects that picture without adding verdict classes,
receipt schemas, or universal reviewer fields.

## 2026-08-09 — Align discovery metadata with the result-path-first frame

Updated the YAML `description` used for skill discovery and routing. Preserved
the existing task-family triggers—research, analysis, refactors, audits,
migrations, hidden state, consequential risk, delegation, repeated execution,
and deferred obligations—and retained the lean-executive and conditional-control
language. Added the operative sequence directly to that first impression: reach
the natural result or evidence path through the smallest safe reversible slice,
and do not complete an environment first.

Why: the skill body and lease reference had been corrected after a zero-evidence
orchestration failure, but the discovery description still foregrounded
complexity and a catalogue of controls without stating the corrected working
picture. Because routing metadata is read before the body and acts as a compact
behavioral prompt, leaving it unchanged could continue to prime
environment-completion behavior. A proposed wholesale replacement was rejected
because it would have weakened useful routing specificity; the applied hybrid
changes the behavioral cue without narrowing the skill to experiments or
weakening safety, protected-data, irreversible-evidence, permission, or
promotion boundaries.

## 2026-08-08 — Re-center the skill on the natural result path

Reframed `environment-first` so its first working image is early, safe contact
with the natural result or evidence path rather than completion of an
environment before attempting the objective. Added a harm-and-recoverability
distinction: user control, people, secrets, permissions, protected or
irreplaceable data, irreversible external state, and irrecoverable evidence
contamination can justify pre-slice controls; reversible confidence limitations
normally narrow the claim, become invalidation conditions, or motivate one
cheap canary. Controls needed only for future scale, polish, or reproducibility
wait, while acceptance-critical reproducibility and pre-outcome protections
remain intact.

Made objective output, decision-changing evidence, or a defensible blocker the
progress surface. Before another repair or review cycle with no objective
evidence, the top agent must choose whether to run the smallest safe slice,
switch to a proven mechanism, narrow the claim, return the blocker, or repair a
defect that prevents or invalidates even that slice. Calibrated reviewers to
the claim and consequence currently in scope; their findings require an
explicit top-agent disposition and do not acquire blocker status merely from
review. Explicit approval, independent-review, and protected-promotion gates
remain authoritative.

Clarified execution leases so a first safe proving unit normally uses an inline
cap, stop condition, and terminal receipt rather than a durable reservation or
renewal subsystem. Durable machinery still precedes repetition, fan-out,
material scarce spend, non-retryable execution, or consequential partial state.

Why: in a bounded agent-memory concept experiment, the orchestration spent
roughly an hour producing and repeatedly reviewing fixture, freeze, ledger,
evaluator, and containment machinery while making zero authenticated subject
calls and producing zero experimental observations. A genuine contamination
risk was silently promoted into a security-grade gate, reviewer findings became
de facto vetoes over a disposable directional pilot, and an explicit warning
against bureaucracy narrowed the planned scope without changing the next
action. Session reconstruction confirmed that local setup checks and three
freeze revisions displaced the first end-to-end observation.

The change targets the originating mental model rather than adding a fixed
timebox or experiment-specific checklist. Independent challenge first rejected
an earlier draft for leaning too far toward premature execution, then accepted
the revised wording against irreversible migrations, security work with
secrets, ordinary bounded implementation, open-ended research, metered batches,
and the motivating experiment. Rejected nearby overcorrections: universal
canaries, fixed repair counts, weakened safety or approval boundaries, treating
all validity defects as recoverable, deferring acceptance-critical
reproducibility, and forbidding durable controls before every first invocation.

## 2026-08-08 — Validate claims and calibrate review to decision authority

Clarified that validation tests the claim a result must support rather than its implementation shape, with structural checks only where safety or acceptance depends on them. Calibrated review to current authority: disposable prototypes need an interpretable directional signal; unresolved judgment that would authorize consequential follow-on work, or protected promotion, warrants independent review while preserving producer/reviewer separation.

## 2026-08-06 — Detect semantic direction drift before plausible endpoints compound

Added a compact delegation reflex for cases where materially different
interpretations or methods can produce similarly plausible finished-looking
results: obtain one cheapest useful early signal that the work still serves its
intended use, then leave routine work autonomous. Briefs now preserve intended
use and ask workers to surface only material changes in interpretation, method,
workaround, or verification that could make a result unusable. The signal is
explicitly distinct from liveness and from task-native evidence of external
effects.

Made `agent-introspect` a Codex-only optional optimization for sparse
session-referenced reflection: `whoami` identifies the invoking parent for
self-reflection, while delegated-worker direction inspection requires an exact
worker reference passed or captured by the harness, or lineage/session
discovery from the exact parent identity. Never infer a child from cwd,
workspace, or recency; if its exact reference is unavailable, use another cheap
directional signal. Begin with metadata or a span and expand only as needed.
This is not a portable requirement, a reason to read full traces routinely, or
evidence that an external effect occurred.

Why: delegated results were superficially plausible yet missed the original
intended use, and a result-only review could reproduce the packet's literal but
wrong frame. Rejected the nearby overcorrections: continuous monitoring,
mandatory checkpoints, exhaustive decision logs, fixed status cadence, a new
persistent role, or a required coordination artifact.

## 2026-08-06 — Correct the passive-only liveness interpretation

Clarified that routine work remains autonomous and does not need heartbeats,
scheduled polling, or status chatter, while passive observation, a lightweight
status request, a follow-up or turn transition, interruption, and cancellation
are distinct operations. When silence is decision-relevant because of a real
anomaly, missed task-relative window, absent expected evidence, changed
decision, or accumulating risk, the orchestrator may make the cheapest
reliable one-off probe whose information value exceeds its disruption. Kept
interruption for explicit cancellation and task-native evidence as proof of
consequential external effects.

Narrowed the terminal `AWAITING_ORCHESTRATOR` fallback to its portable purpose:
a child that needs a material upstream decision without a known suitable live
return channel. A missing bidirectional child-decision channel does not make a
parent-to-child liveness probe useless. In the Codex defaults, a status message
is preferred when available; a follow-up can be a proportionate one-off probe
only when its turn semantics are safe and no cheaper reliable mechanism fits.

Why: after the coordination revision, a strong orchestrator interpreted the
wording as requiring terminal partial returns and passive waiting whenever its
child tools lacked the documented bidirectional mailbox. That categorical
reflex was induced by the instruction wording. It is evidence about how the
guidance was interpreted, not proof of a runtime defect. The correction
preserves capable task-relative judgment without fixed time thresholds, probe
schemas, or new ceremony.

## 2026-08-06 — Make delegated decisions portable and use Codex live coordination

Replaced the terminal-only delegated-decision frame with a portable baseline:
routine work stays quiet, nonblocking facts, milestones, and replies do not
create approval gates, material decision requests stop at a safe boundary, and
observation is separate from cancellation. Retained terminal partial-return and
deliberate resume as the safe fallback when the known live capability set is
absent or delay is long. Added Codex-specific defaults for noninterrupting
messages and passive waiting or lifecycle observation, while reserving
interruption for explicit cancellation. Consequential external effects now
require task-native evidence, not agent prose.

Why: the changed launch-nonexecution investigation at
`/Users/andy/tmp/subagent-issues/2026-08-06-launch-nonexecution-root-cause.md`
documented silent nonexecution and a delayed terminal handoff that could leave
child progress or execution unproven to the parent. Separately, inspection of
the frozen Codex collaboration tool contract established noninterrupting
messaging and passive waiting, and that interruption is an explicit
state-changing cancellation. This supersedes the terminal-only mental model
without adding mandatory heartbeats, schedules, acknowledgements, or universal
status reporting.

## 2026-08-05 — Add exception-driven worker checkpoints

Added an `AWAITING_ORCHESTRATOR` return for material tension between a bounded
brief and observed operational reality. The parent holds the unit, answers or
revises the brief, and resumes the same worker and context when the unit remains
materially unchanged. Routine status, optional refinements, and questions the
brief already answers remain outside the checkpoint path.

Why: a delegated implementation encountered a real mismatch between literal
scope and the mission, but completed through a unilateral assumption because
its only modeled outcomes were completion or terminal blockage. The repair
creates one cheap coordination point while preserving management by exception,
warm same-unit continuation, and fresh independent review.

## 2026-07-18 — Make the top agent lean and move coordination to exceptions

Replaced the top-agent-as-monitor frame with a lean executive role centered on
intent, next-action choice, acceptance, and closure. Replaced the mandatory game
plan with a minimal `Done / Still missing / Blocked or deferred / Next`
orientation, made direct object-level work normal, made worker freshness and
durable briefs selective, bounded independent review by consequence, and made
closeout proportional to integration risk rather than entry into a full mode.

Moved transactional, provenance, and asynchronous-join detail into a
conditionally loaded reference. Added sparse Codex trace-referenced operations
reflection at high-leverage decision boundaries, passing the session log by
path rather than copying trace content into the parent context. Updated model
routing to use task fit and dated capability evidence rather than role prestige.

Why: the prior skill assigned monitoring, state maintenance, repeated review,
and closeout machinery to the top agent. In a live run those responsibilities
became the work, authoritative state drifted, and human steering supplied the
missing reflection. A later mitigation exercise repeated the same failure by
formalizing recovery state before establishing that the schema was needed. The
revision corrects that working picture while preserving the hard safety,
provenance, transactional, and independent-review boundaries for tasks whose
concrete hazards require them.

## 2026-07-14 — Make escalation progressive and lease renewal decision-aware

Reframed entry into the skill around the smallest sufficient environment and
concrete hazard triggers rather than task size or a binary mode choice. Added a
known-hazard fast path, reuse-before-rebuild guidance, and conditional
decision-frontier fields only for dependent work or execution leases. Extended
leases to distinguish operational canaries from decision pilots and to renew
against health, spend, and whether further work can still change the current
decision.

Why: a live calibration used full provenance, review, budget, and lease
machinery but still prepared downstream conditions before testing the
load-bearing prerequisite and renewed batches on operational health alone. A
universal new mode or fixed budget would add ceremony without supplying the
missing decision. The change preserves direct work for small and large-routine
tasks while fast-pathing immediately to the relevant controls when protected,
metered, irreversible, delegated, or context-survival hazards are already
visible.

## 2026-07-13 — Add renewable execution leases and empirical discrimination checks

Added a conditional renewable-lease model for repeated, externally metered,
materially long-running, scarce-capacity, or consequential execution. Added
real-initialization and inherited-context checks when isolation matters,
unit/batch-level health evidence, operational-versus-result stop semantics,
harness-counter accounting, and a conditional empirical instrument challenge
at closeout. Updated the game-plan, subagent brief, Codex defaults, and
maintenance state, with detailed lease guidance in a new reference.

Why: a live campaign treated a 64-unit model loop as one indivisible task,
continued after repeated permission and output-contract failures, enforced
model-authored rather than runtime usage fields, and accepted a numerically
correct but ceiling-saturated contrast too strongly. The changes generalize the
repair to other metered loops, migrations, API batches, deployments, and long
test matrices while explicitly exempting cheap local loops, ordinary tests,
atomic operations, universal stop-on-first-error rules, and fixed task-agnostic
budgets.

## 2026-07-13 — Narrow the receipt trigger after conservative review

Changed the conditional receipt trigger from any explicit audit/efficiency objective to an actual need for comparative or joinable execution evidence. Condition comparisons now instrument each compared condition without presuming that every audit has a baseline and treatment.

Why: a second-pass static review found that the word “audit” could activate attempt and receipt machinery for a bounded read-only audit with no asynchronous work or execution comparison. The narrower wording preserves the intended observability while protecting the direct path from unnecessary ceremony.

## 2026-07-13 — Add conditional context and provenance controls

Added a conditional compact coordination index, task-local evidence promotion gate, coordination receipts with explicit retry/unpaired semantics, immutable defect-delta handoffs, and precise runtime-accounting caveats. Added a conditional execution rule for wave joins and polling fallback, plus claim-changing exact-answer checks in closeout.

Why: a campaign audit found large parent-side input accounting during waits, late reconciliation of dispatch state, a replay-only path continuing after a live-evidence prerequisite failed, repeated repair setup, and stronger causal language introduced during final answer compression. The controls were generalized and made conditional so the skill's direct path and lean-plan posture remain intact.

## 2026-07-13 — Constrain warm continuation

Defined warm continuation as an optional, harness-supported experiment for the same repair unit only, with unchanged objective, provenance, inputs, artifacts, model/runtime/tool state, mutable environment, ownership, and acceptance contract. Preserved fresh independent review and prohibited reviewer or promotion reuse.

Why: the audit observed fresh child contexts but no completed-context resume call. The potential efficiency benefit was therefore unvalidated and the safety risk—stale state, anchoring, and lineage confusion—was higher than the evidence justified for a default.

## 2026-07-13 — Keep campaign machinery out of the general contract

Generalized provenance classes, receipt fields, and event semantics instead of embedding campaign-specific enums, event names, or factorial test designs. Made receipts, joins, frontier fields, and instrumented repair return contracts conditional on actual risk or an explicit audit/efficiency objective.

Why: independent review found that a literal implementation of the initial draft would add unnecessary bureaucracy to ordinary full-mode work and overfit one campaign's harness.

## 2026-07-13 — Preserve transactional and review boundaries

Retained immutable accepted artifacts, versioned candidates, validate-before-promote behavior, rollback copies, fresh reviewers, protected boundaries, and full authorized source access while adding observability around them. Exact final-answer checks remain within the existing closeout gate and apply only when synthesis changes load-bearing claims.

Why: review identified that receipts must not replace result-surface safety, and that the final compressed answer itself can introduce unsupported claims even after upstream reports pass review.
