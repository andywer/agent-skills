---
name: paper-process-walkthrough
description: Use for source-grounded explanations of papers, algorithms, systems or concrete processes, including mechanism walkthroughs, causal traces, simulations and critiques. Skip simple summaries and broad literature surveys.
---

# Paper Process Walkthrough

Explain how a source's argument or process works through a grounded path that answers the user's question. Keep separate what the source records or asserts, what its evidence supports, what the explanation infers and what remains unknown. Sources establish what was claimed or recorded; they do not make every claim true. A simulation is a bounded explanatory model, not a claim of exact replay.

## Choose a useful path

Establish the question, relevant sources, scope and desired depth from the request. For “walk me through this paper,” a useful default is the central mechanism, its supporting evidence, the weakest assumptions and what to inspect next. Ask only when a missing source or ambiguity would materially change the explanation. A formal contract is unnecessary unless the task requires one.

Anchor consequential statements to sections, pages, figures, equations, code, log spans or measurements. Inspect the surrounding material needed to resolve a claim; derived summaries can guide navigation but do not replace primary evidence. State material access gaps and their effect on the explanation.

Walk a concrete input, event or argument through the important transitions. Explain what happens, why, what state or assumptions it depends on, and what evidence supports the transition. Show resource pressure, waits or hidden work where they change the mechanism or conclusion. Follow one useful path deeply before expanding branches; expand only where the user's understanding or decision needs it.

A short algorithm example might trace an input through the operation to its output. A paper critique might connect the framing, method, experiment and claimed result. Use prose, a trace table or a diagram according to what makes the relationships clearest. Graphs, node types, fidelity labels and templates are optional; read [forms.md](references/forms.md) only when one of those forms helps inspection or the requested artifact requires it.

## Keep evidence and inference distinct

A recorded assertion is evidence that the assertion was made. Code describes an implemented mechanism; a measurement supports the conditions actually exercised. Neither alone establishes every claimed behavior, performance advantage or causal explanation.

Explain load-bearing derivations and assumptions. Mark estimates, hypotheses, unknowns and deliberate omissions in ordinary language. Do not silently strengthen a claim, invent exact magnitudes or supply an unobserved mechanism as fact. Identify the next discriminating observation when uncertainty could change the conclusion.

For example, a log showing an agent reported a successful deployment establishes the report. Proof of the external change requires evidence from the affected system. A hypothetical input trace can explain an algorithm without establishing that the implementation executed it correctly.

## Critique within the requested scope

Check consequential links for unsupported causality, false precision, missing baselines, method/result mismatch and conclusions broader than the evidence. Challenge the framing when a concrete case exposes a material tension; avoid expanding into an unrelated research survey.

Distinguish an open implementation choice from a defect, an unsupported claim from a disproved one, and an excluded layer from a missing requirement. Repair only an in-scope gap that breaks the path, at the relevant abstraction layer. A valid critique may require no architectural change.

When the explanation overstates the evidence, change the account: separate observation from inferred mechanism, expose the missing assumption or narrow the claim. Propose a repair, replication or further inspection only where it serves the request or resolves consequential uncertainty.

## Return the explanation the user needs

The reader should be able to follow the mechanism, locate its support, distinguish inference from recorded evidence and see the material unknowns. Use the smallest useful presentation; the task need not produce separate contract, graph, critique and repair artifacts.

For a Crosscut Workbench project, read [crosscut.md](references/crosscut.md) when mapping the explanation to its local artifacts. Honor an explicit artifact contract; those filenames are not defaults for other work.
