# Optional walkthrough forms

Use these forms only when they clarify relationships or support a requested artifact. They are examples, not required sections, fields or stages. Ordinary prose can preserve the same distinctions.

## Graphs

A small graph can help when branching or dependencies would be hard to follow linearly. Useful nodes include claims, mechanisms, events, states, operations, resources, waits, evidence, uncertainty and next actions. Name an edge's relationship clearly: causes, depends on, supports, contradicts, blocks, refines or may contribute to.

Distinguish established causality from a proposed relationship. A graph-shaped presentation does not strengthen its evidence. Avoid nodes or relations that add no explanatory value.

## Evidence labels

Labels may help a dense trace or an artifact whose contract specifies them. Use only the distinctions the reader needs:

| Label | Meaning |
| --- | --- |
| `observed` | Directly recorded or measured. A source's claim can be observed as a claim without its content being established. |
| `derived` | Follows from stated evidence and explicit rules, math or procedure. |
| `structural` | Describes documented architecture or a specified model; execution may remain unverified. |
| `estimated` | Approximate magnitude or ranking without exact measurement. |
| `hypothesized` | Possible explanation needing validation. |
| `unknown` | Not established by available evidence. |
| `omitted` | Deliberately outside the explanation's scope. |

Labels do not substitute for source anchors, reasoning or material uncertainty. Keep observations, derivations and explanatory assumptions distinguishable without implying calibrated confidence.

## Compact presentations

For a mechanism explanation, a short sequence can connect the source claim, mechanism, supporting evidence, consequence and uncertainty. For a simulation, trace input state, operation, hidden work and output state; state where the example departs from observed execution.

A trace table might use:

| Step | State or operation | Source support | Inference or uncertainty | Consequence |
| --- | --- | --- | --- | --- |

For a critique, organize around the central claim, strongest support, consequential weak link, credible alternative and observation that would distinguish them. Omit any element that adds no useful distinction.
