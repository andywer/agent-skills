---
name: failure-investigation
description: Use when a run, review, experiment, implementation, agent workflow, or artifact has failed or produced a suspect result and the user wants root cause analysis, causal trace, hypothesis challenge, repair planning, or recurrence prevention. Especially useful for contradictory artifacts, failed final gates, regressions, bad reviews, invalid evidence, or cases where a prior acceptance may have been premature.
---

# Failure Investigation

Investigate failures by separating what broke, what initiated it, which containment or recovery failed, how consequences spread, and where a repair will reduce harm or recurrence. The goal is not to assign blame or add ceremony. The goal is to prevent false closure and produce a repair plan that targets the consequential causal chain instead of only the most visible symptom or earliest defect.

## When To Use

Use this skill when:

- a review, test, gate, experiment, run, or deployment failed;
- accepted work is later found suspect;
- artifacts contradict each other;
- a result depends on evidence that may not support it;
- a regression has unclear origin;
- the user asks to investigate, trace to root, challenge hypotheses, or prevent recurrence.

Do not use it for ordinary code review, generic debugging with an obvious fix, or broad project summaries. Use a lighter direct workflow when the failure is local and the cause is already clear.

## Core Contract

Use the following questions to guide diagnosis where they could change the conclusion or repair; they are not mandatory report sections:

1. What failed?
2. What invariant or expectation was violated?
3. For a failed system or method, how was the governing outcome supposed to be produced, and which necessary links or assumptions failed or remain untested?
4. Which conditions initiated the failure, and through what local mechanism?
5. Which expected containment, recovery, or detection capabilities failed?
6. Which causes most strongly determine harm or recurrence at the relevant layer?
7. What downstream artifacts, decisions, or claims did it contaminate?
8. What alternative explanations were checked?
9. Which intervention is best supported by expected consequence, recurrence, control, and repair risk?
10. What prevention hooks should be added, if any?

## Workflow

1. **Set the failure contract**
   - Name the observed failure.
   - Name the expected invariant, criterion, or claim that failed.
   - For a system, method, or architecture, trace the intended path from source input through the decisions to the outcome that justified it. Identify necessary quality, scale, or cost assumptions and where the observation diverged.
   - Define the evidence boundary: which logs, files, reviews, tests, traces, datasets, or source artifacts are authoritative.

2. **Map the timeline**
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
   - Choose the smallest repair or combination of repairs that materially reduces the relevant harm or recurrence.
   - Repair avoidable initiating defects and/or missing containment or recovery according to evidence, consequence, recurrence, control, and repair risk; do not give chronological priority by default.
   - Then repair contaminated downstream artifacts.
   - Choose a proportionate observation or check that could show whether the repair worked; reuse an existing check when adequate. For a system or method, test the governing outcome and any claimed quality or cost advantage, not only the local error.
   - State what remains unknown after repair.

6. **Add prevention only where it pays rent**
   - Prefer prevention hooks that catch the same failure mode early.
   - Match the verification method to the claim: use deterministic checks for mechanical properties and sourced review for meaning, causality, or judgment.
   - Do not add process that would not have caught this failure or changed the next decision.

## Evidence Discipline

Distinguish the evidence status of load-bearing claims in ordinary prose. These terms may help; they are not required fields:

- `observed`: directly present in a source artifact, log, test output, diff, review, or trace.
- `derived`: follows from observed facts and explicit rules.
- `inferred`: plausible explanation from the available evidence.
- `unknown`: not established by available evidence.
- `ruled_out`: checked and contradicted by evidence.

Do not promote an inferred cause into an observed fact. If a conclusion depends on an inference, say what evidence would confirm or falsify it.

## Communicate the diagnosis and repair

Explain the observed failure, the best-supported cause and its evidence, the repair and how to check it, and material uncertainty. Use a timeline or causal diagram only when the sequence is needed to understand the mechanism. Persist a concise note in an existing project document when later work will depend on it; do not create a new investigation package or fixed report format by default.

## Prevention

First consider removing an unnecessary component, simplifying an interface or correcting the faulty behavior. Add a rule, helper, schema field, validator or review step only if it would catch or contain the demonstrated failure and the objective cannot reasonably be protected more simply. Apply the same test to existing controls during review.

Preserve required safety and evidence boundaries. Reuse checks and native records where adequate. Broad reminders, extra review without a specific unresolved question, and validators of wording for a semantic failure do not establish prevention. A useful repair may require no new process.

## Relationship To Other Skills

- Draw on `paper-process-walkthrough` for source-grounded tracing when the causal path spans artifacts; it supplies a technique, not a second required workflow or deliverable.
- Use `exploration-map` when investigating a failure with competing plausible causes, conflicting evidence, or uncertainty that could materially change the repair or assessment of the approach. Start when that uncertainty becomes apparent. Reuse an existing decision note or map to track explanations, supporting and contradicting evidence, and the next useful check. Skip it when the cause and repair are already clear.
- Draw on `complex-work` when changing state, coordination or consequential evidence boundaries require additional operating guidance. Use an explicitly scoped multi-agent workflow only when the repair itself has become a multi-unit, acceptance-bearing program; delegation alone is not the trigger.
- Turn the repair plan into a concise handoff when another person or agent must execute it; include the scope, expected outcome, and required validator.
