# Example: a short decision map

The following evidence is illustrative, not a real migration recommendation. This is one possible shape, not a required template.

**Question:** Should we extract the order service this quarter, with the current team and no customer downtime?

**Current answer:** Diagnose the write path before choosing migration. The observed slowdown does not yet identify the component causing it.

- **Extract writes:** Might isolate the slow path, but only if service coupling causes the delay. The illustrative APM report says "write latency doubled"; that observation supports investigating writes, not the proposed cause.
  - **Is coupling responsible?** Compare time spent waiting across service boundaries with time inside database queries in the slow traces. Boundary waits would support extraction; slow queries would strengthen the in-place option below. This missing causal link determines whether the proposed architecture addresses the observed failure.
- **Optimize in place:** Avoids migration work if database queries dominate. The proposed 30% improvement is a staff estimate; test the actual bottleneck before using it to rank options.
- **Full migration:** Adds scope without an established benefit beyond fixing writes. Defer unless evidence shows the read path also requires separation.

**Unresolved evidence:** Customer reports show no latency change while the internal APM report shows a slowdown. Determine whether they cover the same requests and period. Team availability may have changed after the reorganization; verify it before committing work.

**Next:** Inspect representative slow write traces and compare their request coverage with the customer reports. That can distinguish migration from an in-place repair more usefully than scoring additional architectures.
