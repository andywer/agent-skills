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

Produce an investigation that answers:

1. What failed?
2. What invariant or expectation was violated?
3. Which conditions initiated the failure, and through what local mechanism?
4. Which expected containment, recovery, or detection capabilities failed?
5. Which causes most strongly determine harm or recurrence at the relevant layer?
6. What downstream artifacts, decisions, or claims did it contaminate?
7. What alternative explanations were checked?
8. Which intervention is best supported by expected consequence, recurrence, control, and repair risk?
9. What prevention hooks should be added, if any?

## Workflow

1. **Set the failure contract**
   - Name the observed failure.
   - Name the expected invariant, criterion, or claim that failed.
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
   - Steelman at least one alternative explanation.
   - Invert one load-bearing assumption.
   - Look for one counterexample that would change the conclusion.
   - Hold the initiating condition constant and ask what the system should still handle when that condition is normal ambiguity, noise, human error, malformed input, dependency failure, or another expected disturbance.
   - Conversely, ask whether removing the initiating condition prevents the failure class or only this instance.
   - Revise the diagnosis if the challenge survives.

5. **Design the repair**
   - Choose the smallest repair or combination of repairs that materially reduces the relevant harm or recurrence.
   - Repair avoidable initiating defects and/or missing containment or recovery according to evidence, consequence, recurrence, control, and repair risk; do not give chronological priority by default.
   - Then repair contaminated downstream artifacts.
   - Define the validator or review that must pass before the repair is accepted.
   - State what remains unknown after repair.

6. **Add prevention only where it pays rent**
   - Prefer prevention hooks that catch the same failure mode early.
   - Match the verification method to the claim: use deterministic checks for mechanical properties and sourced review for meaning, causality, or judgment.
   - Do not add process that would not have caught this failure or changed the next decision.

## Evidence Discipline

Use fidelity labels for load-bearing claims:

- `observed`: directly present in a source artifact, log, test output, diff, review, or trace.
- `derived`: follows from observed facts and explicit rules.
- `inferred`: plausible explanation from the available evidence.
- `unknown`: not established by available evidence.
- `ruled_out`: checked and contradicted by evidence.

Do not promote an inferred cause into an observed fact. If a conclusion depends on an inference, say what evidence would confirm or falsify it.

## Output Shape

Use this shape for durable investigations; compress it for small failures.

```markdown
# Failure Investigation

## Failure Contract
- Observed failure:
- Expected invariant:
- Scope:
- Evidence boundary:

## Current Diagnosis
One paragraph with confidence level and what would change it.

## Timeline / Causal Trace
| Step | Event | Role | Fidelity | Evidence | Effect |
| --- | --- | --- | --- | --- | --- |

## Causes by Layer
- Initiating condition or defect:
- Local mechanism:
- Failed containment or recovery:
- Consequence-driving or systemic cause:
- Contributing causes:
- Non-causes ruled out:

## Challenge Pass
- Alternative explanation tested:
- Assumption inverted:
- Counterexample search:
- Diagnosis revision:

## Contamination / Blast Radius
- Affected artifacts or decisions:
- Unaffected artifacts or decisions:
- Stale claims to retract or mark superseded:

## Repair Plan
1. Chosen intervention and priority rationale:
2. Downstream repair:
3. Required validator or review:
4. Stop condition:

## Prevention Hooks
- Deterministic checks:
- Judgmental review checks:
- Process or contract changes:
- Hooks rejected as not worth it:

## Residual Risk
- Unknowns:
- Reopen trigger:
```

## Prevention Guidance

A prevention hook should be specific enough that a future agent can apply it without reconstructing the whole incident.

Good hooks:

- schema or contract fields that make missing evidence visible;
- validators for file existence, parseability, count parity, references, freshness, or reproducibility;
- review rubric items tied to the failed invariant;
- required source anchors for claims that drive decisions;
- final-gate checks for downstream artifacts that consume an earlier result.

Weak hooks:

- broad reminders to be careful;
- extra review with no changed review question;
- validators that only check wording style when the failure was semantic;
- process steps whose pass/fail result would not change acceptance.

## Relationship To Other Skills

- Use `paper-process-walkthrough` when the failure is mainly a process trace across source artifacts.
- Use `exploration-map` when several competing root-cause branches remain live after the first pass.
- Use `environment-first` to keep consequential investigations on the smallest real evidence path. Use an explicitly scoped multi-agent workflow only when the repair itself has become a multi-unit, acceptance-bearing program; delegation alone is not the trigger.
- Turn the repair plan into a concise handoff when another person or agent must execute it; include the scope, expected outcome, and required validator.
