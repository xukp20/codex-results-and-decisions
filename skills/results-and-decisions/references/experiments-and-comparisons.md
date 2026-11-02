# Experiments and Comparisons

Use the parts that answer the current question. These are reasoning aids, not additional experiments every task must run.

## Connect a modification to real work

Explain what operation is expensive, how that was observed, and what the proposed change can alter. A profile may justify a candidate without proving its eventual benefit. State that distinction rather than either demanding a complete profiler first or choosing a change without a reason.

For a screening experiment, ask whether a promising candidate has a meaningful effect under ordinary execution. For a mechanism experiment, change a factor that distinguishes competing explanations. For an adoption decision, include the relevant correctness, compatibility, cost, and repeatability evidence. Do not present one experiment as answering all three questions.

When a negative screen occurs, distinguish an ineffective modification, a wrong target, the wrong measured workload, noise, and failed execution. A successful negative result can stop an unpromising route. It cannot by itself refute other methods or opportunities in the project.

## Explain what was compared

Describe the actual intervention and baseline, the representative task being measured, and material controls. Usually a few sentences suffice; exact commands remain in the evidence.

For historical differences, identify changes in source, transformation scope, toolchain, machine allocation, build mode, caching, and measurement boundary only where they could explain the discrepancy. Separate a historic claim, a reproduced observation, and a causal explanation. If the old variant mixed structural, dependency, and proof changes, attribute the result to that combined variant until evidence separates the contributions.

Do not silently turn one sample into a stable estimate, divide unrelated medians to invent a missing direct comparison, or treat a small-sample variance estimate as precise. Keep unfavorable samples and acknowledge material uncertainty without burying the result under routine protocol details.

## Use the right cost measure

Target completion time, total attributed CPU, peak memory, throughput, and the cost of generating or checking the candidate answer different questions. Explain a tradeoff when it matters to the user. Do not retrospectively replace a failed primary objective with a favorable secondary metric.

Nested profiler durations may overlap. Parallel tasks can consume substantial CPU without extending completion time, while a shorter serial task can determine the finish. Do not sum nested durations as exclusive cost or subtract a hot interval as guaranteed savings.

CPU utilization needs a time interval, denominator, and scope: allocated CPUs versus machine CPUs; one process versus descendants; active compilation versus preparation. Underutilization suggests questions about the dependency graph, serial execution, I/O, or task scheduling. It does not identify the cause without further evidence. A short targeted timeline or counterfactual may be more useful than an elaborate permanent profiling system.

Distinguish a program's work counter from physical resources. Exceeding a node-visit cap need not mean the machine ran out of memory. Count repeated visits and unique structure when relevant, then consider algorithmic waste, a better-supported capacity choice, or a limitation in the accepted scope. Do not assume every cap should be increased or every cap should remain unchanged.

A simple accounting model can expose a useful hypothesis. With consistent process coverage and time boundaries, average CPU occupancy is `CPU time / wall time`, and utilization divides that by allocated CPUs. Thus `wall = CPU work / (allocated CPUs × utilization)`. This describes whether measured work or occupancy changed; it does not causally assign the change to a particular optimization. Cross-run differences, ratios of separately aggregated medians, nested elapsed profiles, and incomplete child accounting can invalidate a precise decomposition. Report the supported direction rather than an invented percentage of causal responsibility.

A dependency graph and observed task durations can suggest a long chain. They do not alone establish a scheduling lower bound: task durations can change with contention, internal parallelism, caching, and the transformation itself. Use the chain to choose a test or a useful measurement, not to declare that optimization space is exhausted.

## Describe a tool by the decision it supports

Explain the consumer's question, what the tool can now answer, and how an actual task checked that answer. Examples include identifying which declaration contains instance-search work, comparing normal build times, or locating a dependency introduced by a transformation.

Separate producer capability, integration with the consumer, and actual use. A profiler existing in the SDK does not mean the optimization algorithm consumes its output. A detailed trace does not automatically identify a root critical path or an actionable source edit.

State a missing capability as a missing decision input, not a vague lack of "full observability". Distinguish capability already implemented, data actually collected, and analysis delivered to its consumer. A tool may be sufficient for the next question without providing a complete cost partition; report overlapping categories or unmeasured work honestly rather than fabricating a pie chart. Recommend the smallest useful addition, and identify what existing official tools or captured data already provide before proposing new instrumentation.

## Judge metrics and generalization

Explain a metric's central formula or rule, its intended meaning, and a concrete example. If an irrelevant input change improves the score, identify the affected term and distinguish an input-representation bug from a deeper validity problem. Removing whitespace may fix one sensitivity without establishing readability, performance, or usefulness as an optimization objective.

Compare plausible alternative designs when the choice was not agreed with the user. Do not declare an entire metric useless from one repairable defect, or tune it after seeing candidates until the preferred one wins.

For multiple projects, report whether the same implementation and selection rule worked, where it required changes, and which cases influenced development. File-level summaries, successful builds, mathematical checks, and measured optimization are distinct outcomes. A multi-module project is not multiple independent project validations; a newly exposed development case is not a blind holdout.

Compare the algorithm's actual intervention space with successful manual examples. Ask which operations it can express, which candidates it proposes, what rejects them, and what objective selects among survivors. A missing operation, an overrestrictive policy, a weak cost proxy, and a truncated search need different remedies. More samples of the same narrow transformation do not establish that a broader method fails. Treat manual examples as sources of general mechanisms, not project-specific answers to hard-code.

## Analyze experimental overhead

Identify the failed stage and the work it prevented. A small import error before execution, a long run invalidated by a late checker, and a capacity guard in the mathematical algorithm have different costs.

Separate necessary semantic checks, experiment-validity controls, environmental protections, and administrative conventions. For a questionable gate, explain the failure it prevents and whether a narrower check, warning, or later validation would serve the present development stage. Do not weaken a required invariant to make a result pass, but do not let an invented acceptance rule silently redefine the user's goal.

Measure avoidable repetition where records permit it. Distinguish the research result from preparatory success. After enough information accumulates, choose an architectural simplification or a decisive experiment rather than continuing a cycle of tiny diagnoses with no effect on the main decision.

When repeated failures occur before the operation of interest, reconsider whether the execution wrapper is necessary for the question. Prefer a working ordinary path over another layer of acceptance machinery when it can safely answer the question. Validate a genuinely uncertain interface with a small representative execution when useful; do not insist that every integration defect should have been predictable from a toy input.

Reusable stages depend on relevant inputs and behavior, not ceremony or a new attempt label. Keep the outputs of successful unaffected stages, and rerun what the fix changes. A source alias, environment variable, runner change, or instrumentation change can sometimes affect behavior, so determine relevance rather than declaring all such changes either harmless or invalidating. Never overwrite an old failed observation to make it appear successful.
