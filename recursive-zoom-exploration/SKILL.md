---

name: recursive-zoom-exploration
description: Use for open-ended design, strategy, architecture, research, planning, or problem-solving tasks where premature linearization would hide important structure. Start from the whole shape, zoom into concrete details, zoom out when resistance appears, revise the frame, and zoom back in.
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Recursive Zoom Exploration

Use this skill when the user wants exploratory thinking that is concrete but not reduced to a linear checklist.

The goal is to understand and shape the problem by moving deliberately between levels:

```text
whole picture
-> concrete detail
-> resistance / tension
-> wider frame
-> revised detail
```

Do not default to sequential steps. First show the whole operating shape. Then zoom into the parts where detail changes the understanding. When you hit friction, zoom out to analyze the tension. If needed, zoom out beyond the immediate object into the surrounding system, incentives, assumptions, or meta-process. Then zoom back in with a revised proposal.

## Core stance

Think in recursive zooms, not in flat outlines.

A good answer should feel like this:

1. The user sees the whole shape early.
2. The important parts become concrete.
3. Tensions are not hidden; they trigger zoom-outs.
4. Wider frames change the proposal.
5. The answer returns to concrete implications.
6. The final direction is clearer, not merely broader.

Use a live priority queue of questions only as a steering mechanism. The queue decides where to zoom next. It should not become decorative headings.

## When to use

Use this skill for:

* complex design or strategy questions;
* architecture and system-shape exploration;
* research direction and validation design;
* product or workflow exploration;
* ambiguous planning where the right frame is uncertain;
* critique of prior reasoning;
* turning a mission into an actionable but non-linear direction.

Do not use the full visible procedure for straightforward implementation, lookup, debugging, editing, or small decisions.

## Main operation

### 1. Start with the whole shape

Begin by describing the full object at a high level.

Depending on the task, the object may be:

* a system;
* a plan;
* a research path;
* a product direction;
* an architecture;
* a validation effort;
* a workflow;
* an argument;
* a decision frame.

State:

* what it is trying to achieve;
* what pressure it applies;
* what success would look like;
* what failure would look like;
* what decision it should unlock.

Do this before decomposing into parts.

### 2. Identify the current zoom target

Choose the part where more detail would most change the understanding.

Ask:

* Which part is most load-bearing?
* Which assumption is most fragile?
* Which abstraction is hiding complexity?
* Which alternative could overturn the direction?
* Which concrete example would expose failure?

Zoom into that part.

### 3. Zoom in concretely

When zoomed in, avoid generic prose.

Use:

* concrete examples;
* pressure cases;
* artifacts;
* actors or workers;
* inputs and outputs;
* failure paths;
* scoring signals;
* trade-offs;
* small testable slices.

The point of detail is not completeness. The point is to reveal whether the high-level shape survives contact with concrete behavior.

### 4. Treat resistance as a zoom trigger

When a detail creates friction, do not smooth it over.

Resistance includes:

* contradiction;
* excessive complexity;
* weak evidence;
* overfitting;
* implementation gravity;
* unclear ownership;
* artifact proliferation;
* hidden cost;
* mismatch between artifact quality and behavioral improvement;
* a strong alternative explanation;
* a part that still fails even if the current proposal works.

When resistance appears, zoom out.

### 5. Zoom out to analyze the tension

At the wider level, ask:

* Is this the real bottleneck or only the visible subproblem?
* Did the current frame exclude a better alternative?
* Are we solving a symptom?
* Are we treating a tool, repo, benchmark, artifact, or prior conversation as the center because it is concrete?
* If this proposal worked perfectly, what hard problem would remain?
* Does the tension suggest a different center of gravity?

Let the answer change the direction.

### 6. Zoom out beyond the object when needed

Sometimes the right frame is outside the object.

Zoom out to meta-levels such as:

* reasoning process;
* evaluation method;
* incentives;
* user-visible value;
* maintenance economics;
* evidence quality;
* organizational adoption;
* failure diagnosis;
* product framing;
* abstraction boundaries.

Use meta-levels only when they change the concrete proposal. Do not stay meta for its own sake.

### 7. Zoom back in

After a zoom-out changes the frame, return to concrete implications.

Show how the revised frame changes:

* the object shape;
* the important details;
* the next test;
* what to defer;
* what to kill;
* what to preserve;
* what to measure.

A zoom-out that never returns to detail is incomplete.

## Priority queue of questions

Maintain a live queue of decision-relevant questions.

A question is decision-relevant if answering it would change what to design, test, reject, defer, preserve, or inspect next.

Use the queue to choose zoom targets.

Queue states:

* **Current zoom target**: the question being explored now.
* **Promoted**: became more important because it exposes a stronger bottleneck, tension, or alternative.
* **Deferred**: matters, but does not block the current direction.
* **Retired**: answered well enough or replaced by a sharper question.
* **Reframed**: was asked at the wrong abstraction level.
* **Accepted premise**: established enough locally that it should not be re-proven unless the task is to audit it or new evidence conflicts with it.

Do not show every queue update. Show only changes that alter the exploration.

## Validated premises

If the user marks something as already validated, treat it as a local accepted premise.

Do not re-litigate it unless:

* the user asks for an audit;
* new evidence conflicts with it;
* the current conclusion critically depends on its scope;
* the premise was validated only for a narrower context than the current use.

Move the uncertainty frontier forward.

## Challenge passes

Run challenge passes after provisional conclusions.

Ask:

* What assumption did this answer rely on?
* What is the strongest alternative?
* What would make this fail in a concrete case?
* Are we overfitting to this example?
* Are we overfitting to the current tool, repo, benchmark, artifact, or discussion?
* Are we mistaking implementation maturity for conceptual centrality?
* Are we mistaking proof convenience for importance?
* Are we mistaking artifact quality for behavioral improvement?
* Are we making the answer actionable by making it too narrow?
* Are we keeping it open by making it too vague?

A challenge pass should either change the direction or explain why the current direction survives.

## Incrementality without sequentialization

Do not turn the answer into a step-by-step procedure unless the user asks for steps.

Use maturity bands instead.

A maturity band describes a stronger version of the same effort, with more pressure or realism.

Examples:

* smallest useful slice;
* added contradiction;
* added edge case;
* added independent worker or reviewer;
* added objective scoring;
* added baseline comparison;
* added real-world data;
* added feedback/write-back loop;
* added operational constraints.

For each maturity band, say:

* what pressure it adds;
* what behavior it tests;
* what decision it unlocks;
* what would cause stop, pivot, or escalation.

Maturity bands are escalation levels, not an implementation checklist.

## Output shape

Use this shape when useful. Do not force every heading if a lighter answer is clearer.

```text
Whole shape:
  Describe the full object before decomposing it.

Current zoom target:
  Name the question or part where detail matters most.

Zoom in:
  Explore the target concretely with examples, artifacts, behaviors, or failure paths.

Resistance:
  Name the friction, contradiction, uncertainty, or alternative that appears.

Zoom out:
  Analyze the tension at a wider frame.

Queue update:
  Say what was promoted, deferred, retired, reframed, or accepted.

Zoom back in:
  Show how the wider insight changes the concrete proposal.

Maturity bands:
  Show how the effort can grow incrementally without becoming a linear step list.

Current best direction:
  State the recommendation.

Live alternatives:
  Name plausible alternatives still worth tracking.

Falsifiers:
  State what would weaken or overturn the recommendation.

Smallest decision-grade slice:
  Name the smallest concrete test, artifact, or action that would produce useful information.
```

## Common failure modes

Avoid:

* producing a sequential checklist when the user asked for whole-shape exploration;
* staying high-level and never zooming into concrete mechanics;
* zooming into details before showing the whole;
* finding tension but not zooming out;
* zooming out but never returning to concrete implications;
* using a priority queue as decorative P0/P1 headings;
* keeping all alternatives alive without ranking them;
* re-proving accepted premises;
* letting the most concrete artifact define the architecture;
* treating artifact elegance as evidence of behavioral improvement;
* treating “not sequential” as “not incremental”;
* adding meta-levels that do not change the object-level proposal.

## Final check

Before finalizing, ask:

1. Did I show the whole shape early?
2. Did I zoom into at least one load-bearing detail?
3. Did any resistance trigger a real zoom-out?
4. Did the zoom-out change the proposal or confirm it under challenge?
5. Did I zoom back in after the wider analysis?
6. Did I preserve accepted premises?
7. Did I avoid a rigid step list?
8. Did I still provide an incremental path through maturity bands?
9. Did I end with a concrete smallest decision-grade slice?

A good result should leave the user with:

* a clear whole picture;
* concrete detail where it matters;
* exposed tensions;
* a better frame;
* live alternatives;
* falsifiers;
* and a concrete next slice without reducing the exploration to a linear checklist.
