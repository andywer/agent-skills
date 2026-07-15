# Execution leases

Use this reference only when repeated execution consumes external budget,
material wall time, scarce capacity, or consequential mutations, or when
partial health evidence could change whether more units should run. Do not use
it for cheap local loops, ordinary tests, or genuinely atomic operations whose
partial state cannot inform continuation.

## The working picture

A repeated operation is not one authorization to finish the list. It is a
renewable lease: prove the interface and residue on the smallest useful unit,
then inspect health, spend, and whether another batch can still change the
current decision. Put the lease around the scarce operation itself, even when
a cheap subagent or script launches it.

## Lease contract

Before the first unit, record only what will affect continuation:

- **Operational proving unit** — the smallest execution that exercises real
  initialization, output shape, permissions, boundaries, and accounting. It
  proves mechanics, not usefulness. When later work depends on an empirical
  prerequisite, separately name the smallest development or non-protected
  **decision pilot** that can redirect the work; the two units may coincide.
- **Continuation question** — the unresolved decision that justifies another
  batch and the evidence available at renewal. If partial results may settle
  it, record the task-local result-stop policy before outcomes, or state why no
  result-dependent stop is valid.
- **Batch order and size** — execute prerequisites before dependent work and
  choose how many units may start before health and decision sufficiency are
  checked again. Begin with one when the interface is unproven or the next unit
  can settle the continuation question; enlarge only when overshoot is safe.
- **Accounting source** — harness or service counters, elapsed time, completed
  unit count, mutations, or another observable basis. Keep worker estimates
  separate and never use them to enforce a lease when authoritative counters
  exist.
- **Cumulative cap** — the task-local ceiling on the material resource. Do not
  invent a monetary or token cap when it is unavailable; use an observable
  proxy such as sessions, batches, or elapsed time and label it honestly.
- **Operational stop signals** — permission failure, contract/schema mismatch,
  provenance or integrity failure, repeated identical errors, timeout rate, or
  another health condition known before execution. Do not silently turn an
  outcome into a health signal.
- **Renewal owner** — usually the top agent; a worker may renew only when its
  brief explicitly grants that authority and the accounting surface is visible
  to it.

## Make continuation observable

Persist unit- or batch-level terminal evidence before renewal when that
evidence could change continuation. Record completed, failed, and abandoned or
unstarted work distinctly when those states matter to the objective. Before
the next batch, record whether health passes, spend remains justified, the
continuation question is still unresolved, and the lease is renewed or stopped.
If a tool returns only one aggregate result at the end, use a smaller
invocation, add an incremental wrapper, or accept the operation as atomic and
bound it globally.

Do not confuse watching progress with renewal. File counts, process liveness,
and elapsed time say that work is happening; they do not show that the produced
residue satisfies its contract or that more work has information value.
Validate the named health signals and continuation evidence before renewing.

## Stop without corrupting meaning

Operational health stops may fire without reading protected or held-out
outcomes. Result-dependent stopping must be preregistered or explicitly
authorized because it can bias interpretation. A canary proves mechanics; it
does not prove scale behavior or semantic efficacy, so authorize only the next
decision-relevant unit after the canary. When observing outcomes would
contaminate later evaluation, use a separate development surface or record why
the full operation is indivisible.

Do not mandate stop-on-first-error. Some sweeps intentionally measure a failure
distribution, and some operations tolerate isolated failures. Name the failure
class or threshold that changes continuation. On a global stop, preserve the
evidence already produced and state what was not attempted; do not synthesize
missing results.

## Lightweight accounting

At each renewal, update: units attempted/completed/failed, elapsed time,
runtime-reported counters, cap consumed, cap remaining when knowable,
operational health, continuation-question status, and the renewal decision.
Treat cache counters, billing, unique work, and worker-authored estimates as
different quantities. A ledger that cannot change the next decision is
optional reporting, not lease control.

Parallelism is a later optimization, not a substitute for proving the unit.
After health is established, choose sequential or bounded parallel batches
according to reproducibility, rate limits, shared-state risk, and information
value.
