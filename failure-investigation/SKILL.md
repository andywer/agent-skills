---
name: failure-investigation
description: Investigate failed or suspect results, inefficient processes, or work that is not closing in on its goal despite successful individual steps. Use for causal diagnosis, challenging explanations, choosing repairs, and preventing recurrence, including reviews of AI-agent processes.
---

# Failure and Process Investigation

Explain why the intended outcome was not achieved, or why achieving it took unsatisfactory effort. Individual steps can succeed while the overall process makes little useful progress.

Separate what went wrong, how it happened, why recovery or containment did not suffice, and how consequences spread. Choose an intervention that improves the complete outcome, rather than treating the most visible symptom or earliest defect as the whole problem.

## When To Use

Use this skill when:

- a review, test, gate, experiment, run, or deployment failed;
- accepted work is later found suspect;
- artifacts contradict each other;
- a result depends on evidence that may not support it;
- a regression has unclear origin;
- a process consumes excessive resources, repeats work, or makes little progress toward its goal;
- the user asks to investigate, trace to root, challenge hypotheses, or prevent recurrence.

Do not use it for ordinary code review, generic debugging with an obvious fix, or broad project summaries. Use a lighter direct workflow when the failure is local and the cause is already clear.

## Workflow

Use these questions where they could change the diagnosis or intervention. They are not sequential gates or mandatory report sections. Start with the whole outcome and investigate particular steps when the evidence warrants it.

1. **Establish the intended outcome**
   - Recover the governing goal from the user's mandate. Distinguish the desired outcome from documents, completed steps or other intermediate outputs. If the goal is missing, propose a working interpretation; clarify material uncertainty rather than silently choosing a convenient objective.
   - Name the observed shortfall and what meaningful progress or success would look like, including relevant quality, pace or cost expectations. Resolving an uncertainty can be progress when it changes a consequential decision.
   - Clarify actual requirements, safety boundaries and resource limits. Separate them from preferences, assumptions and inherited procedures. Unclear constraints do not automatically call for more rules; unnecessary or conflicting rules may be part of the problem.
   - Identify the relevant evidence and its authority. Preserve the original expectation, but be willing to question whether it was reasonable or whether the evaluation judged the outcome correctly.

2. **Trace the necessary work and the actual process**
   - From the goal and constraints, reason about what work is needed before accepting the existing steps. Could a step be omitted or replaced by something simpler without losing required behavior?
   - For each consequential stage, identify the needed inputs, expected useful output and how subsequent work uses it. Compare these expectations with observations; include handoffs, waiting, repeated work and feedback loops. Expectations are hypotheses, not proof of a process defect.
   - Identify the initiating condition or artifact and the local mechanism that turned it into the observed failure.
   - Identify each containment, recovery, acceptance, propagation, and detection step that mattered.
   - Separate initiation, mechanism, failed containment or recovery, amplification, escape, and detection when those distinctions explain the outcome. Do not manufacture a layer that the evidence or a simple local failure does not require.

3. **Classify causes**
   - Initiating causes: conditions or defects that started this instance.
   - Local mechanism: how the initiating condition produced the immediate failure.
   - Containment or recovery causes: why an expected, normal disturbance became harmful or remained harmful.
   - Consequence-driving or systemic causes: conditions that most strongly determine harm or recurrence at the abstraction layer relevant to the user's objective.
   - Contributing causes: conditions that amplified the failure or made it easier or harder to detect.
   - Non-causes: plausible explanations ruled out by evidence.
   - Use only categories supported by evidence; one cause may occupy several roles. The earliest fixable event is not automatically the most consequential cause or the best intervention point.

4. **Challenge the current hypothesis**
   - Check a credible competing explanation when it could change the diagnosis. Use an assumption inversion or counterexample when it adds distinct information. Do not manufacture one of each to complete a ritual.
   - Hold the initiating condition constant and ask what the system should still handle when that condition is normal ambiguity, noise, human error, malformed input, dependency failure, or another expected disturbance.
   - Conversely, ask whether removing the initiating condition prevents the failure class or only this instance.
   - Revise the diagnosis if the challenge survives.

5. **Design the repair**
   - Choose the smallest repair or combination of repairs that materially improves the complete outcome or reduces the relevant harm or recurrence. This may mean removing work, changing task selection or stopping an unproductive approach. If causes remain uncertain, choose the next observation that could distinguish them instead of prescribing a speculative repair.
   - Repair avoidable initiating defects and/or missing containment or recovery according to evidence, consequence, recurrence, control, and repair risk; do not give chronological priority by default.
   - Then repair contaminated downstream artifacts.
   - Choose a proportionate observation or check that could show whether the repair worked; reuse an existing check when adequate. For a system or method, test the governing outcome and any claimed quality or cost advantage, not only the local error.
   - State what remains unknown after repair.

6. **Add prevention only where it pays rent**
   - Prefer prevention hooks that catch the same failure mode early.
   - Match the verification method to the claim: use deterministic checks for mechanical properties and sourced review for meaning, causality, or judgment.
   - Do not add process that would not have caught this failure or changed the next decision.

## Observe progress and effort

Start with available evidence. Distinguish useful outcomes from activity counts, and both from diagnostic signals such as retries, waiting or lost information. Add observation only where missing evidence could change the diagnosis or intervention; do not make comprehensive instrumentation a prerequisite.

For efficiency questions, account for relevant resource usage across the complete useful outcome: elapsed time, model or compute consumption, human effort, coordination, rework and maintenance. Use the precision the decision needs. Separate elapsed time from total work and avoid double-counting overlapping activity. Include the cost of the investigation itself.

A long duration alone does not establish avoidable waste, and fewer calls do not establish a better result. Compare against the required quality and a credible expectation or simpler alternative; state uncertainty when the comparison is not established.

## Inspect the working state in AI-agent processes

For AI-agent process reviews, inspect the instructions, documents and summaries the agent uses to understand its work. Make this part of the causal investigation, not a separate documentation audit.

**What did the agent actually see?**  
Check the versions it received or opened. Useful information may exist elsewhere without ever reaching the agent.

**Can it find and work with what it needs?**  
Look at how subjects are organized and connected. Notice repeated reading, duplicated accounts, buried details, or information split across so many places that the agent must reconstruct it each time. Large documents and prose are not inherently bad; judge whether their shape helps this task.

**Is the content a sound basis for action?**  
Check for missing, stale or conflicting information. Can the agent distinguish current decisions from proposals and historical conclusions? Are important uncertainties and supporting sources visible?

**How did that state affect the result?**  
Trace a consequential decision from the available information to the agent's action. Did it receive a poor account, select the wrong one, misinterpret a good one, or act incorrectly despite understanding it?

Use the findings to choose a focused repair. Do not reorganize everything without evidence that doing so would help.

## Evidence Discipline

Distinguish the evidence status of load-bearing claims in ordinary prose. These terms may help; they are not required fields:

- `observed`: directly present in a source artifact, log, test output, diff, review, or trace.
- `derived`: follows from observed facts and explicit rules.
- `inferred`: plausible explanation from the available evidence.
- `unknown`: not established by available evidence.
- `ruled_out`: checked and contradicted by evidence.

Do not promote an inferred cause into an observed fact. If a conclusion depends on an inference, say what evidence would confirm or falsify it.

## Communicate the diagnosis and repair

Explain the observed shortfall, the best-supported cause and its evidence, the chosen intervention or next discriminating observation, how to check its effect, and material uncertainty. Stop investigating when the evidence is sufficient for the next consequential decision or further investigation would not justify its cost. Use a timeline or causal diagram only when it helps explain the mechanism. Persist a concise note in an existing project document when later work will depend on it; do not create a new investigation package or fixed report format by default.

## Prevention

First consider removing an unnecessary component, simplifying an interface or correcting the faulty behavior. Add a rule, helper, schema field, validator or review step only if it would catch or contain the demonstrated failure and the objective cannot reasonably be protected more simply. Apply the same test to existing controls during review.

Preserve required safety and evidence boundaries. Reuse checks and native records where adequate. Broad reminders, extra review without a specific unresolved question, and validators of wording for a semantic failure do not establish prevention. A useful repair may require no new process.

## Relationship To Other Skills

- Draw on `paper-process-walkthrough` for source-grounded tracing when the causal path spans artifacts; it supplies a technique, not a second required workflow or deliverable.
- Use `exploration-map` when investigating a failure with competing plausible causes, conflicting evidence, or uncertainty that could materially change the repair or assessment of the approach. Start when that uncertainty becomes apparent. Reuse an existing decision note or map to track explanations, supporting and contradicting evidence, and the next useful check. Skip it when the cause and repair are already clear.
- Draw on `complex-work` when changing state, coordination or consequential evidence boundaries require additional operating guidance. Use an explicitly scoped multi-agent workflow only when the repair itself has become a multi-unit, acceptance-bearing program; delegation alone is not the trigger.
- Turn the repair plan into a concise handoff when another person or agent must execute it; include the scope, expected outcome, and required validator.
