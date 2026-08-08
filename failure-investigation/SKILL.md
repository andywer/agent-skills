---
name: failure-investigation
description: Use when a run, review, experiment, implementation, agent workflow, or artifact has failed or produced a suspect result and the user wants root cause analysis, causal trace, hypothesis challenge, repair planning, or recurrence prevention. Especially useful for contradictory artifacts, failed final gates, regressions, bad reviews, invalid evidence, or cases where a prior acceptance may have been premature.
---

# Failure Investigation

Investigate failures by separating what broke, why it broke, how it escaped, and how to repair it. The goal is not to assign blame or add ceremony. The goal is to prevent false closure and produce a repair plan that targets the root cause instead of the most visible symptom.

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
3. Where did the defect originate?
4. How did it escape detection?
5. What downstream artifacts, decisions, or claims did it contaminate?
6. What alternative explanations were checked?
7. What repair addresses the root cause?
8. What prevention hooks should be added, if any?

## Workflow

1. **Set the failure contract**
   - Name the observed failure.
   - Name the expected invariant, criterion, or claim that failed.
   - Define the evidence boundary: which logs, files, reviews, tests, traces, datasets, or source artifacts are authoritative.

2. **Map the timeline**
   - Identify the originating action or artifact.
   - Identify each acceptance or propagation step.
   - Separate origin, escape, amplification, and detection.

3. **Classify causes**
   - Root cause: the earliest fixable reason the failure became possible.
   - Contributing causes: conditions that made it easier or harder to detect.
   - Non-causes: plausible explanations ruled out by evidence.

4. **Challenge the current hypothesis**
   - Steelman at least one alternative explanation.
   - Invert one load-bearing assumption.
   - Look for one counterexample that would change the conclusion.
   - Revise the diagnosis if the challenge survives.

5. **Design the repair**
   - Repair the root cause first.
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

## Root Cause
- Root cause:
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
1. Root repair:
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
- Delegate repair or verification only when independent work or review would materially improve confidence; otherwise investigate and validate directly.
- Turn the repair plan into a concise handoff when another person or agent must execute it; include the scope, expected outcome, and required validator.
