---
name: results-and-decisions
description: Interpret implementation and experiment results, explain their significance for the user's goal, and choose evidence-informed next steps. Use for substantive result analysis, progress synthesis, retrospective diagnosis, and research or engineering decisions; simple status facts do not need the full workflow.
---

# Results and Decisions

Turn evidence into an understandable judgment and a useful next decision. An execution log, an acceptance record, an explanation, and a research conclusion serve different purposes. Do not present a shortened log as the conclusion or improve the prose while leaving the next action disconnected from the evidence.

## Scope and use

Use after meaningful implementation or experimental work, when comparing outcomes, investigating progress problems, or explaining a design the user has not seen. Apply only the relevant guidance; a small fix does not require a research report. This skill imposes no report template, mandatory experiment, review ceremony, or approval layer.

It does not authorize execution, delegation, messaging, changing limits, or restarting paused work. Separate a recommended action from one actually authorized. Existing project and user constraints remain in effect.

## Start with the user's question

Establish what the user is trying to accomplish, what this work could tell them, and what they already know. Prioritize the change in useful capability or understanding over the sequence of actions taken.

Distinguish implementation, successful operation, correctness, measured effect, and generalization. They answer different questions. Explain a limitation when it changes the current conclusion; do not mechanically append every unverified property to every paragraph.

For updates, lead with what changed since the last accepted account. Carry older facts only when needed to interpret the change. For an overview, synthesize around the main outcomes and unresolved questions rather than concatenating equally long branch reports.

## Choose detail by its effect on judgment

Give space to information that changes the assessment of value, mechanism, confidence, applicability, or next action:

- A capability a consumer can now use, and the task it enables.
- A meaningful effect, regression, unexpected result, or conflict with earlier evidence.
- A design choice or failure mechanism that explains the outcome.
- A blocker's practical consequence and the evidence needed to resolve it.

Routine version pinning, successful cleanup, and recoverable evidence usually need a short statement or a link. Hashes, file counts, log counts, process identifiers, and call ledgers belong in supporting evidence unless they explain the actual question. Do not forbid these details when they are material to scale, integrity, cost, or a failure.

Use numbers with an object, unit, baseline, and interpretation. Test counts do not describe coverage; output volume does not establish a tool's usefulness; profiling event counts do not identify a bottleneck. Retain meaningful quantitative evidence instead of replacing it with vague claims.

## Explain the design the reader needs

When the agent chose a design the user has not discussed, explain the problem, input and output, central rule or mechanism, and a small example. Describe why this choice addresses the goal and its main tradeoff. Show formulas when they clarify a decision, and explain the terms in ordinary language.

When the design was already agreed, summarize implementation fidelity and focus on outcomes, deviations, and new findings. Explain changed terminology; do not assume a source filename, CLI name, acronym, or internal status label communicates a capability.

Select detail based on the user's actual knowledge, not a universal preference for brevity. A short answer that omits the key mechanism can be as unhelpful as a long inventory.

## Interpret the evidence

Connect the observation to the explanation it supports, the alternatives it leaves open, and the consequence for the goal. Keep observed facts, inferred explanations, and proposed actions distinguishable in prose; these need not be headings.

A candidate compiling does not validate its selection strategy. An unsuccessful optimization does not establish that the whole direction lacks opportunity. A hot function's elapsed time is not automatically removable end-to-end time. Low CPU utilization can reflect dependencies, serial work, I/O, resource allocation, or measurement scope; it neither proves nor rules out a useful structural change.

When current and historical results conflict, inspect what was actually changed and measured before explaining the gap. Do not guess that experiments are equivalent, or stop at "not comparable" when a bounded comparison could explain why. Read [experiments and comparisons](references/experiments-and-comparisons.md) for performance, causal, cross-project, or metric-validity questions.

## Make the result affect the next action

Choose the next action for the uncertainty it can resolve and the decision it could change. Prefer an existing source or a small discriminating check when it can answer the question. Do not require exact causal attribution before every exploratory test; explain which uncertainty a screening test can usefully reduce.

Distinguish fresh information from repeated failure to reach the research question. A succession of preparation fixes is engineering progress, but may leave the hypothesis untouched. Reconsider the integration boundary, experiment order, or unnecessary requirements instead of automatically adding another check or repeating the same run.

Continuing, simplifying, reusing evidence, changing the hypothesis, and stopping a particular route are all valid outcomes. Do not optimize for candidate count, test count, audit layers, or positive-looking results. Avoid new experiments when current evidence is sufficient, and avoid requiring the user to inspect the repository to discover the conclusion.

## Diagnose friction proportionately

Separate physical resource exhaustion, concurrent-task contention, implementation defects, algorithmic work limits, and experimenter-imposed time, memory, or space caps. Similar exit symptoms can require different remedies.

Identify a restriction's purpose and source. Shared-resource protection, runaway prevention, and fair comparisons can justify limits; unexplained strictness or repeatedly underestimated exploration budgets do not justify themselves. Early exploration should have suitable headroom and observable progress. Preserve completed work where reuse is valid. Do not infer that all checks should disappear or shared resources should be unbounded.

Estimate cost from records: work lost, preparation repeated, waiting, and research questions never reached. Do not add overlapping task durations and call that elapsed delay. Mark unknown costs as unknown. Rank bottlenecks by consequences, not the number of failure messages. This is a diagnostic lens, not an additional gate on routine development.

## Compose the explanation

Lead with the answer or important change. Develop the supporting experiment and mechanism at the depth needed to assess it. Put traceable evidence near consequential claims, with operational detail behind links when it adds no explanatory value.

Match the organization to the question: capabilities for "what can it do", mechanism for "how was it designed", conditions for historical comparisons, and causes and costs for slow progress. Do not force identical sections or equal coverage across unrelated components. Use a table when it clarifies a real comparison, not to inventory every action.

Before sending, ask whether the reader can understand what changed, why it matters, what the evidence warrants, and what decision follows when one is requested. Remove detail that obscures those answers; add missing explanations rather than merely shortening the text. See [examples](references/examples.md) when calibrating the difference between evidence inventory and useful interpretation.
