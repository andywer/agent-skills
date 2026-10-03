# Bound consequential execution

Use this reference when external spending, scarce capacity, unsafe retries or consequential partial state could change how work should run. Repeated calls do not by themselves require a lease protocol, custom receipt, ledger or repeated approval.

## Start with ordinary bounds

Use an enforceable attempt, time, cost or mutation limit and relevant operational stop conditions. Prefer limits and counters already provided by the tool or a simple loop. Keep authorization for the actual sources, destination and actions separate from internal resource accounting; do not invent permission renewals inside an already authorized scope.

Choose a coherent batch that answers the user's question. Use a small proving call when the interface is unproven and failure could spoil the run; reuse adequate existing evidence rather than requiring a fresh canary each time. A mechanical success does not establish semantic quality or scale behavior.

Count failed attempts when they consume resources. Preserve actual inputs, outputs and error evidence needed to interpret the result. Distinguish completed, failed and unattempted work when it matters. Unknown usage remains unknown; do not substitute model-authored estimates for runtime counters or manufacture missing results.

## Add renewal only when it changes continuation

A renewal check is useful when intermediate operational evidence can determine whether another batch is safe or worthwhile, or when concurrent workers could exceed a shared cap. Check the relevant health signal and remaining budget before continuing. Use existing task state or native counters; add a durable reservation or join record only when the coordination cannot reasonably work without it.

Do not build a renewal service or per-unit receipt format for a bounded sequential experiment. For a consequential atomic operation, establish the cap, permissions and available abort or rollback path beforehand; do not pretend it supports intermediate decisions.

## Keep stopping honest

Choose operational stop conditions before running. An isolated error need not stop an experiment intended to measure failures. Repeated errors, loss of permission or threatened data integrity may require a stop depending on the task.

For acceptance-bearing experiments, decide any result-dependent stopping rule before observing outcomes; otherwise it can bias the conclusion. Do not peek at held-out results to decide whether to continue unless the design permits it. Use development data for diagnosis when necessary.

After a stop, preserve what happened and report incomplete work. Do not silently retry, overwrite failed observations or treat an empty response as a successful result. Remove extra execution machinery when its concrete need ends.
