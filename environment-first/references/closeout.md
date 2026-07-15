# Closeout

This closeout contract applies to work that entered the full environment. Direct-path work uses ordinary verification proportional to its scope and risk; it does not require a game plan or fresh-context final gate merely to demonstrate process.

The full environment you built includes its own exit. Closeout is not a formality tacked on at the end — it is the payoff of having shaped the environment instead of trusting memory. If you kept a real game plan and a real checklist, closeout is mostly reading them back. If you didn't, closeout is where that catches up with you.

There are three parts, in order: walk the checklist, rebuild state from artifacts, run the fresh-context final gate.

## 1. Walk the closeout checklist

Go through every item on the game plan's closeout checklist. Each one is now in exactly one state:

- **Done** — with a pointer to the real artifact that shows it (a file, a passing check, a committed change). "I did that" without a pointer is not done.
- **Dropped** — with a one-line reason. Deciding not to do something is fine; forgetting you meant to is not.
- **Carried forward** — explicitly handed to the user or a follow-up, named as such in the final response.

Nothing that was ever "to remember" should still be only remembered. If an item can't be resolved into one of these three states, the task isn't ready to close.

## 2. Rebuild state from artifacts

Reconstruct what actually happened from the durable record alone — result surface, review verdicts on disk, produced files and evidence — **without** using your running memory or the maintained game plan as input. Then compare against the plan: a unit the plan says was dispatched with nothing on disk to show for it is exactly the kind of divergence this step exists to expose. Confirm:

- every acceptance criterion from the objective is **met, blocked, or consciously deferred**, each with evidence that points at something real;
- the reviews that were supposed to happen actually left verdicts on disk, outside the plan;
- what you think the answer is matches what the artifacts support.

Any gap between your recollection and the record is a finding. Fix it — or, if it can't be fixed, name it in the final response — before declaring done. A clean rebuild is also what lets someone (including a future you on a cold context) trust the result without re-running the work.

When the task declared provenance for a load-bearing claim, confirm that the observed evidence and any derivation support that declaration. Where conditional instrumentation was enabled, reconcile attempts, completion records, artifact identities, boundary checks, and unavailable/unpaired states. A replay must not be accepted as direct or live evidence merely because a receipt exists. If the join is incomplete, use the verified fallback or leave the unit blocked; do not infer completion. This validates evidence and state, not resource savings.

## 3. The fresh-context final gate

This is the one check you do not skip.

Per-step reviews caught errors where they happened, but each saw only its own unit. The final gate is a *fresh empty-context reviewer* that sees the assembled whole and asks the question none of the per-step reviews could: **is this fit for the objective?**

Give it: the objective and its acceptance criteria, the result surface, the rebuilt state summary, and the load-bearing evidence. Do **not** give it a desired outcome. Its job is not "was the procedure followed" but "does this actually answer the objective, with evidence that holds up and uncertainties honestly named." If compression or synthesis produces an exact user-facing answer that changes a causal claim, evidence label, numerical denominator, experimental contrast, or material uncertainty, include that exact answer in this gate; validate each changed dimension against the artifacts, and revise/re-review it if it is unsupported, materially inaccurate, or overstates the artifacts. If the final presentation does not change a load-bearing claim, the existing proportionate final gate is sufficient; do not create a second ceremony.

For a load-bearing empirical result, arithmetic reproduction is necessary but
not sufficient. Challenge whether the instrument could discriminate the claim:
check relevant ceiling or floor saturation, selective missingness, proxy or
self-reported metering, and one plausible setup explanation. This is
conditional on empirical evidence driving the decision; do not add statistical
ceremony to ordinary code or document review. A surprising or all-equal result
is not automatically invalid, but its interpretation must survive this check.

- If it returns **accept**, the task is genuinely done.
- If it returns **fix**, dispatch substantive fixes to a worker with a proper brief. The top agent may apply a trivial mechanical or metadata repair, noting it, but must not self-accept it. **Re-run the gate** on the fixed whole, not on an assurance that the issue was fixed.

If you had to run the gate in your own context because no fresh subagent was available, say so plainly in the final response — a self-run gate is a weaker check, and the reader deserves to know which one they got.

If resource use is reported, separate runtime counters and elapsed/session telemetry from provider billing and from unique-token or novel-reasoning waste. State unknowns and denominators explicitly. A lower counter is not an acceptance criterion when evidence validity, boundary safety, reasoning completeness, or reviewer independence is worse.

## Why the gate is non-negotiable

A task that ends on its own author's say-so has not been tested; it has been asserted. The entire skill is about replacing "I'll remember to verify" with structure that verifies. The final gate is that principle applied to the finish line. Skipping it undoes the discipline at the exact moment it matters most.
