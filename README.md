<h1 align="center">Results and Decisions for Codex</h1>

<p align="center"><strong>Explain what changed, why it matters, and what the evidence should change next.</strong></p>

<p align="center"><a href="README.zh-CN.md">中文</a> · <a href="skills/results-and-decisions/SKILL.md">Skill reference</a> · <a href="LICENSE">MIT License</a></p>

`results-and-decisions` helps agents interpret engineering and research outcomes before choosing another action or reporting progress. It favors meaningful capabilities, mechanisms, and effects over execution inventories. It adapts the explanation to what the user already knows rather than imposing a reporting template.

## What it changes

- Explain the task a new tool enables, not the volume of its output.
- Connect experimental results to the hypothesis and the user's objective.
- Explain an agent-chosen algorithm before reporting opaque scores.
- Investigate conflicting historical results instead of guessing why they differ.
- Distinguish resource exhaustion, work caps, implementation defects, and avoidable process friction.
- Let negative and unexpected results change the next action.
- Turn conflicting results into discriminating experiments without confusing accounting with causation.
- Keep planning assumptions, resource estimates, and routine verification from becoming invented gates.

The skill does not add tests, approval gates, mandatory reports, or a scheduler. It does not authorize execution or resume paused work. Operational evidence stays available; the explanation concentrates on what changes a decision.

## Install

From a local checkout:

```bash
git clone https://github.com/xukp20/codex-results-and-decisions.git
cd codex-results-and-decisions
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
results_skill_target="${CODEX_HOME:-$HOME/.codex}/skills/results-and-decisions"
if [ -e "$results_skill_target" ] || [ -L "$results_skill_target" ]; then
  echo "Destination exists; inspect it before changing the installation."
else
  ln -s "$PWD/skills/results-and-decisions" "$results_skill_target"
fi
```

The link follows this checkout. Reload Codex if skill discovery has not refreshed. Installation does not change global instructions, other skills, agent profiles, or permissions. Normal automatic discovery is enabled; explicit invocation works too.

## Use

```text
Use $results-and-decisions to explain these experiments. Compare the actual
variants, assess the proposed mechanism, and identify what the results change.
Do not start new experiments.
```

```text
Use $results-and-decisions after this implementation. Explain the design choices
I have not seen, what the checks establish, and the important remaining gap.
```

## Structure

- [SKILL.md](skills/results-and-decisions/SKILL.md): shared analysis and communication guidance.
- [Experiments and comparisons](skills/results-and-decisions/references/experiments-and-comparisons.md): use when interpreting experiments, costs, metrics, and historical or cross-project evidence.
- [Examples](skills/results-and-decisions/references/examples.md): illustrative rewrites that explain significance without inventing conclusions.

## Validation

Run the validator bundled with Codex's `skill-creator`:

```bash
python /path/to/skill-creator/scripts/quick_validate.py skills/results-and-decisions
```

Syntax checks do not establish behavioral quality. Exercise the skill on realistic result-analysis requests, checking whether it explains the mechanism, respects evidence limits, adapts to the reader, and avoids unnecessary new work.
