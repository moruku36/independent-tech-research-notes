**English** | [日本語](2026-lean4agent-workflow-trajectory-verification.ja.md)

# Lean4Agent: formal checks for agent workflows and execution traces

## Overview

- A paper on using Lean 4 to model agent workflows and inspect their execution traces.
- FormalAgentLib checks structure, specified semantics, and observed executions. LeanEvolve uses diagnostics to revise the workflow.
- Static checks prove properties of the formalized workflow under explicit assumptions. Runtime assessments can rely on external validators or an LLM judge.

## Six practical takeaways

- Layer 1 checks the workflow graph, types and data flow. Layer 2 checks preconditions and postconditions under stated assumptions about each LLM step.
- Layer 3 checks observed traces. It can use Lean, external validators, or an LLM judge for predicates expressed only in natural language.
- In a five-model comparison, workflows passing Layer 2 averaged 58.27% versus 43.47% on the 50-task SWE-bench Verified hard subset.
- On 100 ELAIP-Bench questions, the pass/fail comparison averaged 36.60% versus 27.53%. These are comparisons between groups of generated workflows.
- In the separate SWE refinement experiment, full LeanEvolve raised the reported average from 56.93% to 64.40%, a gain of 7.47 percentage points.
- Proposed use. Review whether the formal predicates capture the intended requirement, then independently check the critical claims against a trace.

## Publication and review scope

Ruida Wang, Jerry Huang, Pengcheng Wang, Xuanqing Liu, Luyang Kong and Tong Zhang. arXiv:2606.06523v3, revised October 20, 2026. The arXiv record identifies it as accepted at NeurIPS 2026. Reviewed the PDF and HTML on November 27, 2026 JST, including sections 2–3, Tables 1–3 and Appendix F. No independent reproduction.

## Evidence and limitations

- Layer 2 assumes an LLM step can satisfy its declared postconditions when its preconditions hold. A pass therefore concerns the predicates and assumptions expressed in the workflow model. The paper uses LLM-generated predicate annotations, so specification errors remain possible.
- For the Layer 2 comparison, the reported pass-minus-fail differences are 14.80 percentage points on SWE-bench Verified (95% CI 10.00–19.60) and 9.07 on ELAIP-Bench (5.66–13.07). Verification status is grouped after workflow generation, so these differences describe association in the tested setting.
- The full SWE LeanEvolve condition incorporates formal-guided refinement and an optional LLM-only refinement stage with feedback from the environment. The 7.47-point gain belongs to that configuration and benchmark subset.

## Application and low-cost check

Proposed and untried. Use a small synthetic workflow with a checkable precondition, such as a required document arriving before it is summarized. Specify it, review whether the predicate captures the intended behavior, and inspect a passing and failing trace using an independently produced record.

## Related notes

- [Original SWE-bench paper](2024-swe-bench-original-benchmark.md)
- [ProofPatch and Lean statement review](2026-proofpatch-lean-statement-review.md)

## Sources

- [arXiv v3 record](https://arxiv.org/abs/2606.06523v3)
- [Reviewed v3 PDF](https://arxiv.org/pdf/2606.06523v3)
- [v3 HTML text](https://arxiv.org/html/2606.06523v3)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
