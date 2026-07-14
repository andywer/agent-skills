# Worked example

This compact `MAP.md` shows the required shape after four iterations.

## Root question

> "Should we migrate the order service off the monolith this quarter?" (verbatim)

Constraints: current team only; no customer-facing downtime. As-of: 2026-07-02.

## Current Best Answer

Conditional and blocked below the decision threshold: extract the order-write path only (N2.1) if C1 resolves in favor of the write-path latency premise and G1 has fresh independent L2+ capacity evidence showing at least 60% availability; otherwise defer reads and extraction (confidence: med for the provisional ranking; not decision-ready).

Would change if: C1 resolves against the write-path latency claim, or fresh independent L2+ capacity evidence resolves G1 below 60% availability; either result fails the decision gate.

## Tree

- [N1] Full migration this quarter (P:2 A:1 | archived)
  rationale: P2 versus N2 because it has the same upside with more surface; A1 versus N2 because it is blocked on more capacity and coordination
  risk: downside=high, reversible=no, deadline=2026-09-30
  terminal reason: archived because N2 captures the useful latency path with less surface.
- [N2] Partial extraction (P:4 A:4 | expanded)
  rationale: P4 versus N1 because it captures the motivating latency win with less surface; A4 versus N1 because the partial seam is assessable now despite the G1 capacity gap
  risk: downside=med, reversible=yes, deadline=2026-09-30
  - [N2.1] Write path only (P:4 A:2 | blocked)
    rationale: P4 because it captures the motivating latency win, versus N2.2; A2 versus N2.2 because capacity evidence must be obtained and independently cross-verified rather than taken from material in hand
    risk: downside=med, reversible=yes, deadline=none
    blocked condition: C1 remains unresolved or G1 lacks fresh independent L2+ capacity evidence; decision-ready only when C1 favors the write-path latency premise and G1 shows at least 60% availability.
  - [N2.2] Read path only (P:2 A:4 | frontier)
    rationale: P2 versus N2.1 because reads are not the bottleneck per E2; A4 versus N2.1 because read-path evidence can be checked without migration work
    risk: downside=low, reversible=yes, deadline=none
- [N3] Optimize in place (P:3 A:5 | frontier)
  rationale: P3 versus N2 because it is cheaper but may cap the improvement per E4; A5 versus N2 because in-place changes can start without migration access
  risk: downside=low, reversible=yes, deadline=none
  next move: sidecar — re-derive the L0 E4 optimization ceiling from raw performance data before ranking N3 against N2.
  stop abstract expansion: further abstraction is lower-value than this verification sidecar.
- [N4] Is the monolith the actual bottleneck? (P:3 A:3 | frontier)
  rationale: P3 versus N2 because diagnosing the bottleneck could overturn the preferred extraction path; A3 versus N3 because reconciling E3 needs customer evidence while N3's in-place check can use internal data
  risk: downside=high, reversible=yes, deadline=none; missing this diagnostic could select the wrong bottleneck

## Evidence register

- [E2] "p95 order-write latency doubled in 6 months" (fact, L2, source: APM dashboard + incident reports, as-of: 2026-06-20, half-life: quarters, supports: N2.1)
- [E3] "customer-reported latency stayed flat" (fact, L1, source: customer support reports, as-of: 2026-06-20, half-life: quarters, supports: N4)
- [E4] "in-place optimization caps at about 30% improvement" (hypothesis, L0, source: staff estimate, as-of: 2026-06-20, half-life: weeks, supports: N3)
- [E5] "team has 2 free engineers this quarter" (fact, L1, source: resourcing sheet, as-of: 2026-06-01, half-life: weeks, **STALE** — re-verify)

## Contradiction ledger

- [C1] E2 (latency doubled) versus E3 (customer-reported latency flat) — OPEN
  note: possibly an internal-only path; resolution would confirm or kill N2.1's premise

## Gaps

- [G1] Actual team availability after the June reorganization; fresh independent L2+ evidence is required before selecting N2.1
- [G2] Cost of the dual-write period; accepted as small pending E2's magnitude

## Iteration log

- i1: decomposed the root into N1–N3; CBA=N2 tentative
- i2: expanded N2 into N2.1/N2.2; E2 upgraded L1→L2; CBA=N2.1 provisionally
- i3: frame escape added N4 and opened C1; CBA remained N2.1 provisionally with the decision gate open
- i4: E5 flagged stale and G1 opened; CBA became conditional and blocked pending favorable C1 resolution plus fresh independent L2+ G1 evidence, confidence med for ranking only

## Appendix: archived branches

- N1: archived after full migration was less actionable than N2.

### Conflicting artifacts

When inputs conflict, register each load-bearing figure as L1 with its as-of date and half-life, then open a contradiction immediately. Check revisions, source independence, and source primacy. A resolved conflict can upgrade the surviving claim to L3. Do not let stale positioning, price, or sentiment data be the sole support for a conclusion.
