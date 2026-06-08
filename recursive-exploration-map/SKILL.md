---
name: recursive-exploration-map
description: Use for open-ended product, architecture, strategy, CLI/API, workflow, or research decisions where multiple shapes are plausible and premature surface answers are risky. Especially after pushback: challenge assumptions, compare branches, derive from requirements and boundaries, and avoid polished flat lists. Skip straightforward implementation, lookup, debugging, or small decisions.
---

# Recursive Exploration Map

## Purpose

Use a recursive exploration map to turn an open-ended question into a visible search process: seed adjacent nodes, track how well each node has been explored, choose the most valuable frontier, expand it, revise the hypothesis, and switch from abstraction to evidence acquisition when the next honest step is validation, sidecar execution, or a concrete handoff artifact.

This skill produces an exploration artifact, not a final proof. Treat scores as steering labels, not evidence. Do not confuse `stop abstract exploration` with `stop working`: if a runnable sidecar, outreach pack, benchmark, pilot plan, script, or other concrete artifact can be produced now, continue the loop in execution mode.

## Conversational Shortcut

For design discussion, use a compact form when a full map document would be too heavy: root question, current best answer, branches considered, decision synthesis, and remaining unknowns.

## Core Workflow

1. State the root question exactly.
2. Write a provisional current answer if one exists; label it as provisional.
3. Seed the first adjacent nodes. Common seeds are `what options exist`, `who is affected`, `what makes an option good`, `root problems`, `capabilities`, `limits`, `candidate solutions`, and `pilot / validation paths`.
4. Create a node registry with `depth`, `breadth`, `promise`, `status`, and `next direction`.
5. After the first expansion, run a quick structural self-check: each important node should have children or a reason it is terminal, and the map should show relationships rather than a flat list.
6. Pick one frontier node per iteration using promise, actionability, uncertainty, and decision importance.
7. Choose `breadth` when alternatives may be missing. Choose `depth` when a promising node needs mechanism, evidence, risks, examples, or pilot design. Choose `sidecar` when the node's next uncertainty needs a bounded research, validation, artifact, or experiment task instead of more map expansion.
8. Before promoting a sidecar as next action, run a data access gate: identify required data, how to get it, proxy evidence if direct data is unavailable, and the blocked condition.
9. Before expanding, run a subagent suitability check when subagents are available and the user has asked for or permitted delegation.
10. Use ephemeral subagents for bounded frontier probes, sidecars, or critique passes when they can reduce uncertainty faster than local work.
11. Expand the selected node, revise the hypothesis, and update the tree, registry, and iteration log.
12. If further abstraction is lower-value than validation, switch modes instead of stopping: run the node-attached sidecar, create the outreach/data-request pack, build the benchmark/prototype/pilot plan, or mark the node blocked and switch branches.
13. If the leading branch is blocked and switch branches look materially weaker, run the Pigeonhole / Frame Escape Check before stopping.
14. Stop only when no valuable map expansion remains and no runnable sidecar, proxy check, execution artifact, branch switch, or frame-escape fork can be completed with available access and resources.

## Required Artifact Shape

Create or update one map document unless the user asks otherwise.

Recommended sections:

- `Root Question`
- `Current Best Answer`
- `Scoring`
- `Current Node Tree`
- `Node Registry`
- `Iteration Log`
- `Candidate Rankings` or `Decision Synthesis`
- `Evidence Notes`
- `Validation Sidecars`
- `Remaining Unknowns`
- `Frontier Queue`
- `Next Iteration Recommendation`

Keep the map recursive. Do not let it collapse into a flat list of questions or a prose memo with decorative hierarchy.

Valid `next direction` values include `breadth`, `depth`, `sidecar`, `proxy sidecar`, `data request`, `handoff artifact`, `blocked`, `defer`, and `terminal for now`. Use `sidecar` as a first-class frontier move, not as a global add-on.

## Loop Exit Versus Mode Switch

This skill is open-ended but not infinite. The common transition is:

`conceptual exploration -> sidecar / artifact / validation work -> map update -> next frontier decision`.

When the map says `the next honest step is empirical`, that usually means `stop adding abstractions and do the empirical-enabling work`, not `return a final answer`.

Before ending a turn, ask:

- Is there a selected frontier with `sidecar`, `proxy sidecar`, `data request`, or `handoff artifact` as the next direction?
- Can I run that sidecar now, or create the concrete artifact needed to run it later?
- If direct fieldwork is required and cannot be performed here, can I still create the outreach list, interview guide, data request, benchmark rubric, script, prototype, or tracking sheet?
- If the leading node is blocked, is there a more actionable switch branch whose sidecar can be run now?

Only stop after answering these. A valid stop state must name why all remaining moves require unavailable external access, user approval, real-world contact, paid tools, or a later pilot. Otherwise, continue with the next runnable frontier move.

## Anti-Flatness Rules

A well-written skill should usually prevent flat maps, but open-ended work can drift into brainstorming. Catch that early.

After the first expansion, verify:

- Important nodes have child nodes or an explicit `terminal for now` reason.
- The tree shows relationships, not only categories.
- The node registry records each important node's `status` and `next direction`.
- The iteration log names one selected node and one expansion direction.

If the artifact fails this check, repair structure before adding more content. Do not continue iterating on a flat map.

## Scoring Guidance

Use simple ordinal scores, but make them relative to adjacent nodes. Scores are not absolute truth; they answer questions like `relative to sibling nodes, which frontier is deeper, broader, or more promising right now?`

Pair each important score with a one-line rationale. Prefer `4: stronger than sibling nodes because response-time proof is clearer` over a bare `4`.

Depth:

- `0`: named only
- `1`: rough definition
- `2`: drivers and caveats listed
- `3`: mechanism, evidence, risks, and examples explored
- `4`: compared against alternatives and translated into action or test design
- `5`: tested with real data, users, customers, or execution results

Breadth:

- `0`: no alternatives listed
- `1`: one or two obvious adjacent alternatives
- `2`: several adjacent alternatives
- `3`: major categories covered
- `4`: categories plus edge cases and counterexamples covered
- `5`: broad scan validated externally or empirically

Promise:

- `1`: interesting but probably low-value
- `2`: useful but narrow
- `3`: plausible candidate
- `4`: strong candidate
- `5`: likely core direction or first-priority test

Actionability:

- `1`: no realistic data, access, or execution path right now
- `2`: possible only with difficult external access
- `3`: can run proxy research or light outreach
- `4`: can run a decision-changing sidecar with available resources
- `5`: can execute a pilot, experiment, or data-backed decision immediately

Guardrails:

- Do not assign `Depth 5` or `Breadth 5` from desk reasoning alone.
- Do not compare scores across unrelated branches as if they were precise measurements.
- Add an explicit `evidence level` when a high promise score is not yet validated.
- Track `actionability` separately from `promise`; a high-promise node can be blocked.
- For decision-relevant nodes, include `what would change this score?`

## Optional Node Metadata

Use more metadata only when it helps decide the next frontier. Do not overload every early node. Add richer metadata when a node becomes decision-relevant, high-promise, or disputed.

Useful fields:

- `relative score`: numeric score plus one-line reason against adjacent nodes
- `evidence level`: `none`, `reasoned`, `source-backed`, `field data`, or `validated`
- `actionability`: relative score plus reason, based on currently available data/access/resources
- `data access`: `direct available`, `direct obtainable`, `proxy only`, `blocked`, or `not needed`
- `validation sidecar`: research task, experiment, interview, prototype, or data request that would test the node
- `validation cost`: rough cost class such as `tiny`, `small`, `medium`, `large`, or a concrete estimate when known
- `validation target`: what the sidecar tests, such as `desirability`, `feasibility`, `viability`, or `evidence quality`
- `kill criterion`: what result would make us stop pursuing the node

Example node metadata:

```markdown
| Node | Relative Scores | Evidence | Data Access | Current Uncertainty | Next Direction | Sidecar | Cost | Kill Criterion |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| N6.1 | Promise 4: best among siblings because proof is faster; Actionability 2: needs buyer data we do not have | reasoned + source-backed | direct obtainable or blocked | Is the pain real enough? | data request | Interview 5 buyers and request sample call logs | small | Fewer than 2/5 report real missed-lead pain |
```

## Validation Sidecars

Use validation sidecars to keep the map connected to reality. A sidecar is a bounded task attached to a specific node because that node's next uncertainty is better reduced by research, validation, an artifact, or an experiment than by more conceptual breadth/depth expansion.

Treat `sidecar` as one possible node direction:

```markdown
| Node | Current Uncertainty | Next Direction | Sidecar | Cost | Trigger |
| --- | --- | --- | --- | --- | --- |
| N6.1 | Is the pain real enough? | sidecar | Interview 5 buyers and request sample logs | small | Run before further depth |
```

When logging an iteration, `Direction` may be `sidecar`:

```markdown
Selected node: `N6.1`
Direction: `sidecar`
Reason: Further depth would be speculative; the uncertainty is empirical.
Sidecar: `Buyer discovery and sample-log request`
Expected output: evidence summary, score changes, go/kill recommendation.
```

Sidecar types:

- `orientation`: source-gathering, competitor scan, market shape, target filters, benchmark search
- `proxy evidence`: substitutes for unavailable direct data, such as reviews, forums, social posts, complaint portals, job ads, vendor benchmarks, studies, or public datasets
- `data request`: ask for logs, exports, analytics, customer records, or operational samples
- `interview`: customer, buyer, operator, expert, or stakeholder discovery
- `experiment`: landing page, outreach test, fake-door test, prototype trial, process dry run
- `artifact test`: build a small pilot plan, script, workflow, or mock deliverable

Do not call a sidecar `validation` unless it can change confidence using decision-relevant evidence. An orientation sidecar can sharpen the node, but it does not validate pain, demand, willingness to pay, or operational feasibility by itself.

Before promoting a sidecar to the next action, run the data access gate:

```markdown
| Node | Required Data | Direct Access Path | Proxy Evidence Path | Blocked If | Next Move |
| --- | --- | --- | --- | --- | --- |
| N6.1 | call logs and missed-lead outcomes | operator outreach | reviews, social posts, complaint portals, studies | no outreach and no credible proxy | proxy sidecar or switch branch |
```

Add sidecars only when useful:

- Early exploration: usually skip cost metadata unless a sidecar is obvious.
- Promising node: add one small sidecar and rough cost class.
- Top candidate: add validation target, cost, evidence threshold, and kill criterion.
- If direct data is required but not currently obtainable, mark the node `blocked pending data access`, run a proxy sidecar, or switch to the next candidate branch.

Cost classes:

- `tiny`: minutes, no external access, desk check
- `small`: hours, light browsing, small subagent task, or a few outreach messages
- `medium`: days, interviews, prototype, data request, or paid tool use
- `large`: multi-week pilot, customer integration, fieldwork, or material spend

When a node's biggest uncertainty is empirical, set that node's `next direction` to `sidecar` only if the sidecar can produce decision-changing evidence with available resources. Otherwise set it to `proxy sidecar`, `data request`, or `blocked`.

## Frontier State Gate

Every decision-relevant frontier should end in exactly one of these states:

- `validated enough to pilot`: evidence supports a pilot or concrete execution step
- `needs proxy evidence`: direct data is unavailable but credible substitutes can be gathered now
- `blocked pending access`: direct data is required and neither access nor credible proxy evidence is available
- `defer / switch branch`: another node is more actionable or has a better evidence path
- `handoff artifact ready`: the next real-world move cannot be executed here, but the artifact required to execute it has been produced

If the leading node is high-promise but low-actionability, do not keep refining it. Mark the blockage and pick the best available next move: data acquisition, proxy evidence, or another candidate branch.

## Pigeonhole / Frame Escape Check

Use this when the search may have compressed itself into a too-narrow frame.

Trigger this check when all are true:

- The leading branch is `blocked pending access`, `handoff artifact ready`, or otherwise waiting on unavailable real-world feedback.
- Available switch branches look materially less promising, less trusted, or merely more desk-actionable.
- Recent iterations mostly refine the same abstraction, customer type, service family, or validation pattern.

Also consider it when the current answer depends heavily on a broad abstraction such as `coordination recovery`, `AI ops`, `platform`, `marketplace`, or `automation`.

Run one recursive challenge round over major parent nodes, usually:

- `what makes this high leverage?`
- `who can we serve?`
- `what services can we provide?`
- `what root problems are we targeting?`
- `what are our capabilities and limits?`
- `what validation or access paths exist?`

For each major node, ask:

- Did this framing exclude promising alternatives?
- Did we optimize for the wrong criterion, such as elegance, agent-fit, public observability, or repeatability?
- Did we mistake researchability for actionability or actionability for market value?
- Did we overfit to the first concrete case, geography, customer type, or data source?
- What alternative child branch appears if this node is reframed?

Fork only branches that are both meaningfully different and plausibly better on at least one named criterion such as access, proof speed, trust path, willingness to pay, repeatability, or risk.

Guardrails:

- Run only one frame-escape round unless it produces a new branch that beats the current frontier on a named criterion.
- Do not reopen every old branch. Challenge major parent nodes, then fork selectively.
- Do not let this become infinite brainstorming. If no new branch beats the current frontier or improves the evidence path, return to validation/contact or stop with the blockage recorded.
- Log the check as an iteration with `Direction: frame escape` and record which parent nodes were challenged, which forks were created, and why most alternatives were rejected.

## Ephemeral Subagent Use

Subagents are especially useful for recursive exploration because frontier work is naturally branch-shaped. Use them deliberately, not ceremonially.

At each frontier or sidecar decision, ask:

- Is there a bounded branch, sidecar, or critique that can run independently?
- Would an independent pass reduce uncertainty, broaden the map, or catch overfitting?
- Can the assignment fit in a concise prompt with a clear output shape?
- Is the result useful even if it disagrees with the current hypothesis?

Prefer ephemeral subagents for:

- `breadth probes`: missing branches, adjacent markets, edge cases, counterexamples
- `depth probes`: mechanism, risks, evidence, pilot design, failure modes for one node
- `validation sidecars`: public research, artifact tests, competitor scans, validation-plan drafts
- `critique passes`: unsupported claims, fake precision, repetition, premature convergence

Do not spawn subagents for:

- tiny edits or formatting cleanup
- tasks whose answer blocks the immediate next local step
- duplicate probes on the same branch
- broad brainstorming without a required output shape

If subagents are not available or not permitted, record the same task as a sidecar or frontier item instead of implying it was completed.

## Subagent Pattern

Use subagents to widen or deepen the frontier, not to generate unfocused brainstorms.

Good subagent assignments:

- `Deep-probe node X. Return mechanism, evidence, risks, pilot design, failure modes, and whether it beats the current best candidate.`
- `Act as the counterexample/breadth agent. Find missing branches and explain why each might beat or fail against the current wedge.`
- `Critique the current map. Identify unsupported claims, fake precision, repetitions, and what would change the conclusion.`

Main-agent responsibilities:

- Give each subagent a bounded branch and required output shape.
- Avoid duplicate branch assignments.
- Continue non-overlapping local work while subagents run.
- Synthesize once in the main artifact; do not paste subagent outputs wholesale.
- Close subagents when finished.

## Evidence Hygiene

Separate three claim types:

- `Observed fact`: directly supported by source, log, data, or artifact.
- `Inference`: reasoned from observed facts but not directly proven.
- `Hypothesis`: plausible but untested; requires validation.

For top conclusions, include:

- why we believe it
- what evidence supports it
- what would change our mind
- what the next validation step is

If the user asks for grounded evaluation, read the relevant session logs, artifacts, and source files before judging the process.

For top-ranked nodes, include a compact claim table:

```markdown
| Claim | Type | Support | Confidence | What Would Change It |
| --- | --- | --- | --- | --- |
| This is the best first wedge | hypothesis | stronger relative proof path than sibling nodes | medium | failed buyer interviews or no measurable leakage |
```

## Stop Conditions

First decide whether you are stopping the whole loop or only stopping abstract map expansion.

Stop abstract map expansion when one or more is true:

- New branches mostly reduce to existing nodes.
- New candidates fail at least two core tests such as low value, weak repeatability, weak proof, high access burden, high compliance risk, or low willingness to pay.
- The ranking is stable across a counterexample pass.
- The remaining uncertainty is empirical: customer access, field data, pricing, implementation effort, or real-world adoption.
- The leading node is blocked pending data access and no credible proxy sidecar is available.
- The next useful artifact is a pilot plan, experiment, outreach list, prototype, or validation script.

Then continue in execution mode if any runnable next move remains:

- Run a node-attached orientation, proxy, benchmark, critique, or artifact sidecar.
- Create the outreach list, interview script, data-request pack, benchmark rubric, prototype, validation plan, or tracking artifact.
- Switch to the best branch whose evidence path can be advanced now.

Stop the whole loop only when:

- Further abstraction is lower-value than validation, and the validation-enabling artifact already exists or has just been created.
- The next needed action requires external access, real-world contact, user approval, paid tools, or data not available in the current environment.
- The leading node and switch branches are blocked or deferred, with the blocked condition explicitly recorded.
- If leading and switch branches are blocked but switch branches look materially weaker, a Pigeonhole / Frame Escape Check has already been run or explicitly judged unnecessary.

Do not keep iterating merely because unexpanded nodes remain. But also do not stop merely because the map says `validation is next`; produce or run the validation-enabling sidecar/artifact first when feasible.

## Common Failure Modes

- Flat list: the artifact lists questions but does not recurse into child nodes.
- Fake precision: scores appear objective but are not tied to evidence.
- Premature synthesis: the map converges before a counterexample or breadth pass.
- Infinite exploration: the map keeps expanding after the next step should be validation.
- Premature stop: the map identifies a needed sidecar, data request, or handoff artifact, but the agent ends before producing it or explaining why it cannot be produced now.
- Pigeonhole lock-in: the map keeps choosing among branches created by one narrow frame after the leading branch is blocked and alternatives look weak.
- Repetition bloat: conclusions are restated in every section instead of maintained once.
- Overbroad abstraction: a new category explains everything and therefore predicts too little.

## Final Cleanup Pass

Before delivering or saving the map, run a cleanup pass:

- Keep one canonical `Current Best Answer`.
- Keep one canonical `Candidate Rankings` or synthesis section.
- Remove repeated explanations from iteration logs; keep only deltas.
- Check that high scores have relative rationales and evidence levels.
- Check that promise and actionability are not conflated.
- Check that top candidates have node-attached sidecars or explicit reasons no sidecar is needed.
- Check that next sidecars pass the data access gate or are marked `proxy sidecar`, `data request`, or `blocked`.
- Check that `stop abstract exploration` is not being used as an excuse to skip runnable sidecars or concrete handoff artifacts.
- Check whether a Pigeonhole / Frame Escape Check is required before stopping on blocked branches with weak alternatives.
- Check that the stop condition says whether the loop truly stops or switches to validation/artifact mode.
- Check that the next action is concrete.

For additional mitigation patterns, read [mitigations.md](references/mitigations.md) when revising or evaluating a map.
