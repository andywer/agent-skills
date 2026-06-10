---
name: paper-process-walkthrough
description: Use when walking through a research paper, technical report, algorithm, system design, workflow, incident, agent run, or other concrete process where the user needs an evidence-grounded explanation, causal trace, process simulation, critique, or next inspection plan. Especially useful when summarizing would be too shallow, when mechanisms span abstraction layers, or when claims must distinguish what the source says from what is inferred, hypothesized, unknown, or omitted.
---

# Paper Process Walkthrough

## Stance

Treat the source material as canonical and the walkthrough as a projection over it. A good walkthrough is not a prettier summary, and a good simulation is not a claim of exact replay. It is a bounded, inspectable model of what the sources support, what they imply, where the hidden work happens, and what still needs evidence.

Prefer one excellent critical path over many shallow branches. Keep missing evidence visible. Do not upgrade an inferred, estimated, or hypothesized mechanism into an observed one.

## When To Use

Use this skill for:

- paper walkthroughs, reading notes, paper clubs, or technical explainers;
- simulating how an algorithm, protocol, workflow, experiment, or system operates;
- tracing a process across abstraction layers;
- turning a paper or report into claims, mechanisms, evidence, uncertainties, and actions;
- critiquing whether a paper's evidence actually supports its claims;
- finding what to inspect, reproduce, implement, or test next.

Do not use it for a simple abstract, citation lookup, or broad literature survey unless the user asks for a mechanism-oriented walkthrough.

## Core Workflow

1. Establish the walkthrough contract.
2. Map canonical sources.
3. Build a projection of the argument or process.
4. Walk one critical path deeply.
5. Label evidence and fidelity.
6. Critique the model.
7. Propose repairs, replications, or next inspections.

Keep the workflow lightweight when the request is small. Use the full structure when the source is complex, disputed, or action-guiding.

## 1. Walkthrough Contract

Before explaining, decide what the walkthrough is for.

Capture:

- `source`: paper, report, code, transcript, logs, figures, tables, appendix, or other materials;
- `question`: what the user wants to understand or decide;
- `scope`: the process, mechanism, result, or argument being traced;
- `excluded`: layers or claims that are out of scope;
- `fidelity boundary`: what can be observed directly from sources versus inferred from domain knowledge;
- `output shape`: notes, causal trace, implementation plan, critique, replication plan, or study guide.

For vague asks like "walk me through this paper", choose a useful default: explain the paper's central mechanism, the evidence behind it, the weakest assumptions, and what to inspect next. Ask a question only when the source or desired depth is genuinely ambiguous.

## 2. Canonical Sources

The original source remains the authority. Do not let the projection replace it.

Use source anchors whenever possible:

- section, page, figure, table, equation, algorithm block, appendix, code file, log line, benchmark, or experiment;
- exact wording only when short and necessary;
- paraphrase with clear attribution for longer material.

If sources are missing, say so as part of the result. Missing source access is not a footnote; it is a limit on the model.

## 3. Projection Model

Project the source into a small graph-shaped model. Use only the pieces that help the user answer the current question.

Useful node types:

- `claim`: what the source asserts;
- `mechanism`: how the claimed process is supposed to work;
- `event`: something that happens over time;
- `state`: what changes or must be tracked;
- `operation`: work performed by an algorithm, system, person, or model;
- `resource`: time, memory, compute, data, authority, attention, money, or trust;
- `wait`: blocking, queuing, latency, synchronization, or missing precondition;
- `evidence`: source support;
- `uncertainty`: what remains unresolved;
- `tension`: conflicting claims, tradeoffs, or interpretations;
- `action`: next experiment, reproduction, implementation, read, or measurement.

Useful edge relations:

- `causes`
- `depends_on`
- `supports`
- `contradicts`
- `refines`
- `translates_to`
- `amplifies`
- `hides`
- `blocks`
- `waits_for`
- `may_contribute_to`
- `requires_evidence_from`
- `mitigates`

Every important causal edge should say what kind of relation it expresses.

## 4. Critical Path Walkthrough

Default to a short, grounded path:

```text
source claim -> hidden mechanism -> evidence -> consequence -> uncertainty -> next action
```

For a paper, a good path might be:

```text
problem framing -> method idea -> algorithm step -> experimental test -> claimed result -> weakest assumption
```

For a process simulation, a good path might be:

```text
input state -> operation -> hidden work -> resource pressure -> output state -> validation hook
```

For each step, explain:

- what happens;
- why it matters;
- what supports it;
- how well supported it is;
- what would change confidence.

Avoid full expansion unless it changes the user's understanding. If the process branches, show the main branch first and name the branch points.

## 5. Fidelity Labels

Label important claims, events, and edges with one of:

| Label | Meaning |
| --- | --- |
| `observed` | Directly present in the source, code, log, trace, table, figure, measurement, or quoted material. |
| `derived` | Follows from observed facts plus explicit rules, math, or documented procedure. |
| `structural` | Part of the known architecture, protocol, model, or workflow being described. |
| `estimated` | Plausible magnitude, ranking, or effect size without exact measurement. |
| `hypothesized` | Possible explanation that needs validation. |
| `unknown` | Explicitly unresolved from available sources. |
| `omitted` | Out of scope by contract. |

Rules:

- Do not silently upgrade fidelity.
- Avoid pseudo-quantitative confidence unless calibrated evidence exists.
- Keep exactness earned: stronger claims need stronger source support.
- Treat missing evidence as a finding.

## 6. Critique Pass

After the walkthrough, audit the projection before presenting it as settled.

Look for:

- unsupported causal links;
- false precision;
- ungrounded bottleneck or performance claims;
- missing experimental details;
- missing state variables;
- omitted baselines or ablations;
- method/result mismatch;
- overbroad generalization;
- hidden assumptions;
- evidence that supports a weaker claim than the authors make;
- counterfactuals not tied to the causal path.

Phrase critique as model repair, not just cautionary prose. For example:

- downgrade a claim from `derived` to `hypothesized`;
- add a missing variable to the state model;
- add a required reproduction step;
- split one overloaded claim into observed result plus inferred mechanism;
- mark a layer or experiment as omitted.

## 7. Output Patterns

Choose the smallest useful artifact.

### Compact Walkthrough

Use for chat answers or quick reading support:

```markdown
**Walkthrough Contract**
Question:
Scope:
Fidelity boundary:

**Critical Path**
1. Step - fidelity - source/evidence - why it matters

**What The Paper Actually Shows**

**What Is Inferred**

**Missing Evidence / Weak Links**

**Next Inspection**
```

### Process Trace

Use when the user asks to simulate or debug a process:

```markdown
**Process**
Input/state:
Layers:
Resources:
Omissions:

**Trace**
| Step | Layer | Event | Relation | Fidelity | Evidence | Why it matters |

**Findings**

**Uncertainties**

**Counterfactual / Repair**
```

### Paper Critique

Use when evaluating trustworthiness:

```markdown
**Central Claim**

**Evidence Chain**

**Strongest Support**

**Weakest Link**

**Alternative Explanations**

**What Would Upgrade Confidence**
```

## Working With Crosscut Workbench

When working in a Crosscut Workbench-style repo, map this skill to the local artifacts:

- `REQUEST.md`: the walkthrough request;
- `CONTRACT.md`: scope, layers, fidelity boundaries, state/resource/evidence requirements;
- `TRACE_IR.yaml` or `PROJECTION_GRAPH.yaml`: events, claims, edges, evidence, uncertainties, and actions;
- `INSPECTOR.html` or `PROCESS_INSPECTOR.html`: rendered inspection surface;
- `WEAKNESSES.md`: critique pass;
- `REPAIR_PROPOSAL.md`: concrete model or evidence repairs.

TraceIR is useful when the process is causal and layer-oriented. A projection graph is useful when the source is exploratory, argumentative, or branch-heavy.

## Final Check

Before finishing, make sure the user can answer:

- What process, argument, or mechanism is being walked?
- Which claims came directly from the source?
- Which claims are derived, structural, estimated, or hypothesized?
- What hidden work, assumptions, or resource pressure was exposed?
- What evidence is missing?
- What would change the causal path or confidence level?
