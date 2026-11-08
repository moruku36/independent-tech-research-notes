**English** | [日本語](2026-security-skills-kernel-skill-sif.ja.md)

# How Effectively Do Security Skills Guide Coding Agents in Vulnerability Detection in Linux Kernel?

- This preprint evaluates public security skills on known Linux-kernel vulnerabilities.
- It compares 37 skills, four models, and 100 cases over 14,800 runs, then studies failure-driven SKILL-SIF revisions.
- Target files are supplied; results do not directly measure whole-repository auditing or false-positive rates.

## Practical interpretation (7 lines)

- Examine evidence acquisition and verification rather than assuming a supplied skill ensures accuracy.
- Score function, responsible statement, and vulnerability class separately.
- Consider preserving unresolved questions and explicit candidate-rejection conditions.
- Check whether final reports retain supporting locations and evidence.
- Evaluate revised procedures on cases excluded from refinement.
- Report absolute performance, regressions, and verification cost alongside multipliers.
- No kernel audit, skill execution, reproduction, or weight update was performed here.

## Metadata and scope

- Authors: Haoran Xue, Nikta Akbarpour, Gias Uddin, Song Wang.
- arXiv:2610.25705v1, October 19, 2026. Venue/peer-review acceptance unconfirmed.
- Checked November 9, 2026 JST. Abstract and main HTML methods/results/refinement/validity sections partially read; code unverified.

## Method and reported findings

Agents inspect pre-fix source with target paths supplied and no internet/Git history. Fully correct means jointly matching CWE, function, and statement: 11.1% overall.

Five high-performing skills are revised using failure analysis and tested on 100 separate cases. Aggregate full correctness rises from 6.05% to 11.20%; the maximum eightfold result is one combination's 2% to 16%, not an overall multiplier. This comparison and the original 14,800 runs have different populations. Procedures, not model weights, are updated.

## Limitations and interpretation

Known vulnerable cases with file hints cannot establish false-positive rates on ordinary code or zero-day discovery. Language, classes, models, selection, and annotations constrain transfer. These aggregates alone do not establish an advantage over no skills.

Our proposed harness should preserve revision diffs, failures, and regressions and separate missing guidance from poor execution. Generalization needs independent tasks.

## Related notes

- [OpenAI kernel investigation pipeline](../security-governance/2026-openai-linux-kernel-vulnerability-pipeline.md).
- [OpenClaw Dreaming](../llm-infrastructure/2026-openclaw-dreaming-memory-consolidation.md): external memory differs from procedure revision.

## Low-cost proposal — not performed

Use small known-bug and healthy examples. Manually score evidence, location, and rejection reasons. Separate refinement/evaluation cases; hold model and budget constant. Record false positives and total cost, rather than trusting self-grading with supplied answers.

- Use: proposed only; no implementation/reproduction.
- Open checks: artifacts, runtime budgets, no-skill controls, healthy cases, and transfer.

## Primary sources

- [arXiv v1](https://arxiv.org/abs/2610.25705v1)
- [HTML](https://arxiv.org/html/2610.25705v1)
