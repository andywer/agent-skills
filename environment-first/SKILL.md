---
name: environment-first
description: "Use for complex or error-compounding work — deep research, multi-source analysis, refactors, audits, migrations, or tasks where hidden state, consequential risk, delegation, repeated execution, or deferred obligations can make an early mistake expensive. Start with direct work for clear, local, reversible tasks; add only the controls whose concrete triggers appear, and activate a relevant control immediately when its hazard is already known. Build reconstructible state, bounded execution, and independent verification only to the degree the work needs them."
---

# Environment-first

Build a reconstructible operating environment before complex work. The core move: **do not try to remember how to behave well — shape the environment so behaving well is structural.**

Every agent session is an environment. It has capabilities and boundaries that determine what the agent can perceive and do, and those boundaries quietly shape the outcome whether or not the agent is aware of them. Trying to hold a complex task together by remembering — "I must run the check at the end," "I mustn't forget the edge case," "I should verify this claim later" — is brittle: memory degrades, context compacts, and the reminder is exactly what gets lost. Restructuring the environment so the check happens by construction is cheap and durable.

So before doing the work, prepare the environment to do the work in. This skill is about that preparation and the light-touch maintenance that keeps it honest.

## Start with the smallest sufficient environment

If the task is clear, local, reversible, and comfortably fits one context — with no delegation or deferred checks — work directly. Do not create a game plan, checklist, or reviewer merely to demonstrate use of this skill. Perform the ordinary verification appropriate to the task.

Escalation is modular, not a mode ceremony. Add the control tied to the concrete hazard: durable state when obligations must survive context, a bounded brief when work is delegated, transactional handling for irreplaceable results, a provenance gate for evidence promotion, an execution lease for repeated metered or consequential work, and independent review for load-bearing synthesis. If a hazard is known at the start, activate that control immediately. If it is only suspected, take one cheap reversible probe. Task size or number of steps alone is not a reason to activate every control.

Controls may accumulate as the work reveals real needs. When several interact, or the work must survive compaction and dependent handoffs, use the full environment below. Starting directly is not a commitment to stay direct; entering coordinated work is not a commitment to keep every control active.

## The two environments

**Macro environment** — what you are given. The operational surfaces of the harness: the tools and MCPs available, the workspace directory and reachable filesystem, auto-loaded instructions (AGENTS.md, CLAUDE.md, system prompt, skill files), command-line tooling, permission and guardrail behavior, network access, and model/context limits. You discover this; you mostly cannot change it. But you must know it, because every limit you are unaware of becomes a silent failure later.

**Micro environment** — what you construct inside the macro one. The current model context and, crucially, the parts of it you shape deliberately: a maintained game plan, a closeout checklist, the boundaries and contracts of the subagents you dispatch, the required *shape* of results (e.g. "return a diff plus a passing-test transcript"), and the guiding instructions you hand down. This is the lever. Most of the skill is about using it well.

The governing insight about the micro environment: **the one context that must persist should be lean and reconstructible.** The top agent's job is monitoring and maintenance of current state, not primary production; the bulky work happens in subagent contexts that are thrown away. But leanness only *delays* compaction — dispatches, results, and reviews still accumulate. The actual defense is that every load-bearing fact lives in an external artifact (the game plan, verdicts on disk, evidence files), so when compaction does come, it removes nothing that cannot be rebuilt. This is the real reason to delegate and to externalize. It is not about parallelism or speed; it is about making the one context that must persist survivable.

**Compact coordination index.** For work with deferred obligations, branching, asynchronous delegation, evidence promotion, or another stated need to survive compaction, maintain a small index of acceptance-critical state: objective and acceptance criteria; current unit, status, next action, and blocker; ownership and protected-boundary state; pointers to authoritative inputs, candidate/accepted results, and verdicts; and, when relevant, the required/observed provenance class, attempt status, and mutable environment or tool-version identity. Keep detailed artifacts and source evidence on their durable surfaces. The index is a coordination aid, not hidden reasoning persistence and not a replacement for source access. It may point to reasoning or reports when those artifacts are needed, but does not require persisting private internal reasoning.

A pointer is not content. Before acting on a retrieved artifact, validate its identity, version or hash when available, unit scope, and completion state. A checksum can detect accidental drift; it cannot prove that no obligation was omitted. If the index is stale, incomplete, or unsupported by the artifacts, rehydrate from the durable surfaces or stop and report the missing state. Never let compaction hide evidence, tool permissions, mutable inputs, acceptance obligations, or protected-boundary facts. When none of these triggers applies, use the ordinary lean plan rather than manufacturing an index.

## Start coordinated work with the pre-task

If the task did not qualify for the direct path, do not dive into the objective. First set up a tiny micro environment for one question: **"How do I achieve this objective, and do I have what I need?"**

Give that question a moment of real work:

- **Survey the macro environment** enough for *this* task. What exact runtime or interface will execute the work, and is it compatible? Which input is authoritative? What can still mutate? Where will candidate and accepted results live? What permissions, promotion steps, and rollback paths apply? When a claim depends on isolation or fresh context, distinguish the working directory or sandbox from inherited configuration, global instructions, plugins, caches, credentials, and state stores; probe real initialization on a non-protected surface rather than treating `--help` as an execution test. If a valid environment or result lineage already exists, verify its identity, freshness, and scope, then inspect the delta instead of rebuilding it. Do not audit everything — probe what this task will actually touch. End with a compact preflight receipt when state must persist; a discovered limit that stays only in your head is the exact failure this skill exists to remove.
- **Decide the shape of the answer.** If the objective is clear and no control trigger is present, work directly. Use a lean objective/now/next state when coordination must persist. Build the full environment when multiple controls interact, dependent delegated waves or evidence promotion make state consequential, a wrong step would be expensive to unwind, or the work will outrun one comfortable context. More than a few units, by itself, is not enough.
- **Name what you are missing.** If a fact, access, or decision is missing, get it now — a quick research probe, a tool check, or one high-leverage question to the user ("what would make this output unusable?"). Do not convert a missing input into a hidden assumption.

The pre-task is itself an example of the discipline: rather than trusting yourself to plan well in your head, you make a small explicit space to plan in. When it resolves, tear it down and build the environment for the main work.

## Shaping the working environment

An environment that guides without distracting has a few properties. Aim for these; do not manufacture structure that no unit of work will read.

**A single source of live state: the game plan.** Keep one artifact — see `references/game-plan.md` — that holds the current concrete step, the high-level next steps, a backlog of deferred actions, a closeout checklist, the constraints the macro survey found, and the decisions later units must stay consistent with. It is not a full project plan; it is the minimum a fresh context would need to know what is happening and what happens next. Expand only the active part in detail; keep everything else as terse prose until it becomes active. This artifact is the thing the top agent maintains instead of remembering.

**Deferred actions live on the checklist, not in your head.** The moment you notice "this will need X before we're done," write X on the closeout checklist. A remembered obligation is a bug waiting to happen; a written one is inert until it is time.

**Critical checks are structural, not hoped-for.** If a check must happen after the work, make it happen by construction: require the producing step to emit the evidence (a test transcript, a diff, a schema-valid file), and make a *different* context verify that evidence. "I'll remember to double-check" is the failure mode this skill exists to remove.

**Task-local evidence promotion gate.** When provenance is a prerequisite for downstream work or dispatch, declare the provenance needed for the claim in a task-local form and check it before that dependent work begins; otherwise declare it before the load-bearing result is promoted. It may require one evidence class or a set of classes plus an explicit derivation path; the skill does not define a universal enum. Record the observed provenance and compare it with the declared requirement. A replay, summary, or derived artifact may be useful evidence, but it cannot silently satisfy a stronger live, direct, or independently attested requirement. On mismatch, absence, or ambiguity, record a fail-closed block and stop dependent work, dispatch, and promotion until the required evidence or an explicit decision changes the requirement. Use the identifiers, fields, and event names supplied by the applicable harness or project. A receipt records provenance; it never substitutes for the evidence itself.

**Treat result surfaces transactionally.** Accepted artifacts are immutable. Write a candidate to a new or versioned path, validate it, then promote it. Before any unavoidable in-place transformation of irreplaceable data, create and verify a rollback copy. A command succeeding is not evidence that its output is safe to replace the prior result.

**Lease repeated or metered execution.** Treat a loop that consumes external budget, material wall time, scarce capacity, or consequential mutations as a renewable lease rather than one indivisible task. Before its first unit, name the operational proving unit, the next continuation decision, any task-local result-stop policy (or why none is valid), batch size, observable accounting source, cumulative cap, operational stop signals, and renewal owner. When later work depends on an unresolved prerequisite, order units by decision value and use a development or non-protected decision pilot when needed. At renewal inspect health, spend, and whether further units can still change the current decision; record that decision before starting the next batch. If the harness exposes relevant evidence only after the whole loop, shrink the batch or repair the harness first. Use `references/execution-leases.md` only when this trigger applies—cheap local loops and ordinary tests do not need lease machinery.

**Separate health stops from result stops.** Permission, contract, schema, provenance, integrity, and repeated identical execution failures are operational health signals; they may stop a lease without consulting protected or held-out outcomes. Result-dependent early stopping must follow the task's preregistration or decision policy. When observing a proving unit would contaminate later evaluation, use a development or non-protected surface.

**Conditional coordination receipts.** Retain the transactional protections above. If the work has asynchronous delegation, dependent waves, multi-stage promotion, protected-boundary risk, or an explicit need for comparative or joinable execution evidence, use the lightest append-only dispatch/completion and artifact-lineage receipts that make the relevant state joinable. When comparing execution conditions, instrument each compared condition. Do not call the record-and-spawn operation atomic unless the harness transactionally couples them. Otherwise use an idempotent pre-dispatch intent and reconciliation states such as `unpaired` or `unknown` for a spawn without a receipt, a receipt without a child, a crash, or an unavailable field. A retry is a new attempt with a new attempt identifier linked to the same unit; replaying the same event key is a duplicate. Accept one terminal attempt under an explicit task policy only after that attempt passes unit-identity, required-provenance, completion-evidence, boundary, and artifact-lineage checks; mark other attempts superseded or unresolved rather than treating them as duplicate units. If the harness has no event-join facility, use verified polling and artifact checks; do not infer completion from silence. Require only fields exposed and material to the claim, record unavailable fields as unavailable, and fail closed when the missing field prevents the required provenance or boundary check. For direct work without these triggers, ordinary artifact verification and review remain sufficient.

**Guiding instructions over ambient hope.** When you hand work to a subagent, give it a small system-prompt-like brief: its scope, why it matters, what "done" looks like, what is out of scope, and what evidence to return. A good brief makes the review easy and makes drift visible.

**Output contracts that force reflection.** Ask for results in a form that makes the constraints unavoidable. "Return the answer" invites hand-waving. "Return the answer, the three sources you used, and the one check that would falsify it" forces the producer to confront the constraints and gives the reviewer something to verify.

Do not over-build. Every file, checklist item, and contract you create is context someone has to read. If a unit of work would never consult it, it is decoration. The test for any structure: *would removing it make a wrong step more likely to slip through?* If not, cut it.

## Delegation

The top agent selects, monitors, and integrates; subagents produce load-bearing substantive work. Keep that line clean. The top agent may apply trivial, locally verifiable metadata or integration repairs, but it must not originate and then self-accept the claims it is supposed to challenge.

**Scaling down after full mode has begun.** Direct-path tasks never enter this section. For a small reversible unit discovered inside an existing environment, the top agent may perform the mechanical integration itself. Record the downgrade in the game plan, keep the plan current, and leave the full environment's independent final gate intact. Producing a small integration is negotiable; self-accepting load-bearing substance is not.

**Immutable defect-delta handoff.** When a reviewer identifies a repairable defect, create a new immutable handoff containing the same unit and objective, the exact defect delta, the prior verdict pointer when one exists, a verified index of inputs/results to inspect, current provenance status, owned and prohibited paths, acceptance checks, and attempt state. The repair produces a new attempt and may cite but may not edit the prior verdict or silently broaden the unit. This reusable pattern reduces repeated setup; it does not remove source evidence, boundary checks, or the fresh independent review.

**What to delegate.** Anything bulky, self-contained, and verifiable: a research question with a known answer shape, an edit confined to one area, an analysis of one source, a reconciliation of one conflict, a verification pass. If a unit needs a paragraph of setup and produces a paragraph of result, it is a good delegation. If it needs your whole conversation to make sense, the unit is wrong — fix its brief, not the subagent.

**Empty context by default.** Dispatch workers and reviewers from empty context, working only from their brief and the files it names. If they cannot succeed from that, the brief is incomplete — repair the brief rather than leaking your conversation into theirs. The point of a fresh context is that it has not anchored on your conclusion; that is what makes its review worth anything.

**A reviewer is not the worker.** Have a *different* empty-context agent check a result before you accept it. Give the reviewer the brief, the produced artifact, and the current result surface — never the worker's rationale or a desired verdict as ambient truth. If those claims need checking, pass them as explicitly labeled artifacts. And be honest about what independence buys: a fresh context removes anchoring on the worker's conclusion, not the blind spots two instances of the same model share — so prefer machine-checked evidence (a passing run, a diff, a validation) over evidence a reviewer merely read. A verdict that lives only in chat is not a verdict; put it on disk, outside the game plan, so closeout can rebuild state from verdicts without leaning on the plan.

Reviewer verdicts are reviewer-owned and append-only. A repair worker may cite a verdict and produce superseding work, but must never edit the prior verdict. The reviewer writes the next verdict after inspecting the repair.

**Monitoring subagents.** You cannot watch a subagent think; you can only shape what it must return and check what it did. So monitor structurally: give every dispatch a worker-visible **budget** in units it can count — files touched, attempts, tool calls, sources read — and a **return contract**. The top agent may additionally enforce externally observed elapsed-time or token ceilings; record the accounting basis and do not pretend the worker can see them. Record the dispatch in the game plan the moment you send it (an abandoned unit must stay visible), and when the result lands, judge it against the brief — accept, send back with specific feedback, or block it after repeated failure and move on. A unit that has failed three times is a signal the unit is wrong, not that the worker is bad; re-scope it.

**Account when resources can change the next decision.** Track resource use when the user asks for accounting, when work is externally metered or materially long-running, when efficiency is an objective, or when continuation depends on spend or elapsed time. Start with the proving unit and keep a lightweight run ledger of observable facts: start/end time, completed units, failures and retries, configured lease, approval waits, and runtime-reported usage or cost. A budget without a stop or renewal rule is reporting, not control. Do not enforce a lease with worker-authored estimates when harness counters exist, and do not invent token or monetary estimates the environment cannot measure. At closeout, report observed usage, unknown fields, and lease compliance. The ledger is evidence, not an acceptance gate unless the task makes it one.

When accounting is requested, label runtime-reported input/output/reasoning counters, elapsed time, session count, and cache-counter fields as operational observations. Keep them distinct from provider billing, price, cache-pricing semantics, and unique-token or novel-reasoning waste. Give every percentage its denominator; identify unavailable fields; and call counterfactual savings unmeasured unless a controlled comparison establishes them. Lower counters do not compensate for weaker evidence validity, reasoning completeness, boundary safety, or reviewer independence.

**Bounded workers — no unilateral self-promotion.** A worker that senses it cannot finish within its budget does **not** silently spawn its own sub-workers and become an orchestrator. That way lies an unbounded tree where every level re-derives context and reliability quietly erodes. Instead, the worker returns a **partial result plus a decomposition proposal**: what it completed, what remains, and how it would split the rest. The top agent — which holds the map — decides whether to split, re-scope, or escalate.

The ban is on *unilateral* promotion, not on depth itself. When a unit is legitimately wide — sweep fifty sources, check every module — running every piece from the top would bloat exactly the context this discipline keeps lean. For those units the brief may explicitly grant one level of fan-out: "map over these N items with sub-workers; return only the reduction plus per-item evidence pointers." Recursion by contract, not by drift. (If a task is so large that even the top agent's plan will not fit, split the *objective* into sequential phases and run this discipline per phase, rather than growing the tree downward.)

**Escalate the boundary before the model.** When a unit flounders, in order: (1) fix its brief — is it missing intent, acceptance, or a verification rule? (2) get the missing fact — dispatch a narrow research probe. (3) narrow the unit — split just the active part. (4) only then reach for a stronger model, and only for genuine judgment or high-stakes reasoning. Reaching for a bigger model to paper over a vague brief just produces a more confident wrong answer.

## Execution and maintenance

The loop is small: **pick the next step, dispatch it, check the result, update the game plan, repeat** — until the closeout checklist is empty and the final check passes.

Maintaining the game plan is the top agent's actual job, so do it at the natural moments: when a step completes, when a deferred action appears, when the plan turns out to be wrong. When the work reveals that the objective or its acceptance criteria were mis-stated, **stop and revise the plan explicitly** — do not let the real goal drift silently while you keep executing the stated one.

Keep the plan a projection of reality, not a wish. Periodically, and always before closing out, reconstruct the current state from the durable artifacts (the result surface, produced files and evidence, review verdicts on disk) *without* leaning on your memory or the plan itself, then compare against the plan. A divergence is itself a finding — including a unit the plan says was dispatched with nothing on disk to show for it.

Watch for the environment going stale: if the result surface keeps changing but the game plan stops updating, stop dispatching and reconcile the plan with the artifacts before continuing. If steps keep spanning multiple concerns, or the reviewer keeps catching the same class of error, the decomposition is wrong; re-shape it rather than powering through.

Record completion and provenance changes as explicit events when conditional coordination instrumentation is enabled, not as inferred status prose. A parent may wait for a wave-level terminal join and then retrieve the changed artifacts; repeated status polling is a fallback for incomplete or timed-out joins, not the normal source of truth. Update the compact index at natural state changes rather than on every status tick. Keep the full event history on disk so a fresh context can reconstruct the run without replaying the entire parent conversation.

## Closeout for full-mode work

The full environment you built includes its own exit. Direct-path work uses ordinary task-proportionate verification and does not require these orchestration gates. Before declaring full-mode work done:

- **Walk the closeout checklist.** Every deferred action is done, dropped with a reason, or explicitly carried forward. Nothing that was "to remember" is still only remembered.
- **Rebuild state from artifacts** and confirm every acceptance criterion is met, blocked, or consciously deferred — each with evidence that points at something real, not at your recollection.
- **Run one final check in a fresh context.** A last empty-context reviewer verifies the *whole* is fit for the objective — not "did I follow the steps" but "does this actually answer the objective, with evidence that holds and uncertainties named." This gate is the one check you do not skip; per-step reviews caught local errors, but only the final gate sees the assembled result. If it returns fixes, dispatch them and re-run it.

See `references/closeout.md` for the checklist contract.


## The hard "don't"s

- **Don't rely on memory for anything that must happen later.** Put it on the checklist or make it structural. This is the whole skill.
- **Don't let the top agent originate and self-accept load-bearing work.** Trivial mechanical integration is allowed; substantive production and its acceptance must remain separate.
- **Don't dispatch vague intent.** A unit without scope, a "done" condition, and a return contract is not ready to send.
- **Don't let the reviewer be the worker.** Fresh context, no inherited rationale, no desired verdict.
- **Don't let workers edit reviewer verdicts.** Repairs supersede work products; reviewers issue new verdicts.
- **Don't let a worker promote itself.** Fan-out happens only when the brief grants it; otherwise the worker returns a partial and a proposal, and the top agent decides.
- **Don't build structure nothing will read.** If removing an artifact wouldn't make a wrong step more likely, it's decoration.
- **Don't declare full-mode work done without the fresh-context final check.** Direct-path work remains subject to ordinary verification proportional to its risk.

## Reference files

- `references/game-plan.md` — the game-plan artifact: shape, the closeout checklist, when to update, the rebuild rule.
- `references/subagent-brief.md` — the dispatch contract for workers and reviewers, empty-context rules, budgets, and bounded-partial returns.
- `references/execution-leases.md` — read before repeated, metered, materially long-running, or consequential batch execution.
- `references/closeout.md` — the closeout checklist and the fresh-context final gate.

## Harness-specific defaults

When a matching file exists under `harness-defaults/`, read it before dispatching subagents and carry its applicable defaults into their briefs. These files provide operational defaults for that harness/model pairing; they do not replace the core boundaries in this skill. If no matching file exists, use the harness's ordinary defaults.

- `harness-defaults/codex-gpt-5.6.md` — default subagent models, reasoning levels, and specialist-consultation guidance for Codex with GPT-5.6.

Read the relevant reference before the part you're about to do.
