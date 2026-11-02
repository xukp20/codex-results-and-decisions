# Examples of Useful Interpretation

These are illustrative rewrites, not fixed templates or claims about a particular project. Use only conclusions supported by the actual evidence.

## Profiling capability

**Inventory:** "We validated hundreds of spans and thousands of JSON pointers."

**Useful account:** "The tool can now take a slow declaration and show whether its recorded work includes instance search. We checked this on two real declarations and the optimizer used the output to select a candidate. It still does not tell us whether that work delays the whole build, so the candidate needs a normal-build comparison."

The validation details remain accessible. The main text explains the new task the tool enables and the decision it cannot yet settle.

## Shared dependencies

**Inventory:** "We copied and hashed several gigabytes and tens of thousands of files."

**Useful account:** "Experiments can now reuse one prepared read-only dependency set and create only their own outputs. This removes repeated dependency preparation from each branch. We have not measured the aggregate time saved."

Size matters if explaining disk capacity; it is not automatically the result the user needs.

## Algorithm chosen by the agent

**Inventory:** "Assignment, construction, maps, and tests passed."

**Useful account:** "The algorithm groups declarations using their dependency edges, then selects a partition using an estimated compilation cost. It produced a buildable split on the real project. The split shortened elapsed build time but used more CPU, which suggests the current cost estimate does not fully capture the tradeoff. These measurements do not yet identify the cause."

Describe the actual selection rule, not this illustrative one if the implementation differs. If the user already agreed the rule, spend more space on the observed deviation than repeating the design.

## A score changes after whitespace is added

**Inventory:** "Padding raised the score by 3%. We stopped ranking."

**Useful account:** "The score rewards similarity in file size, measured in physical lines. Adding blank lines to the smallest file made the sizes look more balanced although the code structure did not change. Counting nonblank lines would remove this particular defect. We still need to decide whether size balance predicts the readability we care about; fixing the input measure alone would not validate that claim."

This explanation is appropriate only if the formula actually has that mechanism. Investigate the affected term instead of guessing from the symptom.

## Work cap versus machine capacity

**Inventory:** "Five comparisons exceeded the budget. More resources are needed."

**Useful account:** "The checker stopped after its own node-visit counter reached the limit; the run did not exhaust machine memory. Four cases repeatedly parsed the same field, while the fifth did not. Reusing parsed fields can address the first mechanism, but it is not an explanation for all five."

Next choices depend on the observed mechanism, not on the word "budget" in an error message.

## Conflicting historical performance

**Inventory:** "The old version was 20% faster; the new version is 5% faster."

**Useful account:** "The older candidate changed module structure and dependency imports together; the new candidate changes structure only. That is one documented difference, not yet proof of where the extra gain came from. Compare the fixed variants and their build conditions before attributing the gap to a worse partitioning algorithm."

If the combined changes have not been verified, describe them as a hypothesis to check, not an established explanation.

## A simple implementation update

**Overgrown account:** A full method, risk, evidence, and future-work report for a display-label fix.

**Useful account:** "Updated the label and checked both empty and populated views. The layout still fits at the smallest supported width."

Proportionate explanation is part of the skill. More detail is not inherently more rigorous.

## A concrete blocker deserves detail

**Too vague:** "Integration remains blocked by environment issues."

**Useful account:** "The loader resolved a directory symlink, but our checker compared its physical path to the original alias string and rejected the same package. Compilation itself was not the failure. The proposed fix binds both representations to the same expected object while preserving the identity check; it has not yet been exercised in a real project run."

Explain the consequence and the unresolved part. Routine path hashes can remain in the linked report.
