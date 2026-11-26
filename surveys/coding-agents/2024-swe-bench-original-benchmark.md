**English** | [日本語](2024-swe-bench-original-benchmark.ja.md)

# SWE-bench: evaluating patches against real GitHub issues

## Overview

- The original SWE-bench paper on evaluating repository-level Python issue fixes using real issue and pull request pairs.
- It scores generated patches by checking that issue-specific tests pass and tests that passed on the base revision still pass.
- The benchmark is selected for executable test evidence, covers 12 Python repositories, and measures behavior checked by those tests.

## Six practical takeaways

- The full benchmark contains 2,294 tasks from 12 Python repositories. The method uses GitHub issues and linked merged PRs with test edits.
- Candidate tasks require at least one test that fails before the reference fix and passes after it.
- A generated patch resolves a task when all designated FAIL_TO_PASS and PASS_TO_PASS tests pass. Missing required tests count as failures.
- For BM25 retrieval in v3 Table 5, Claude 3 Opus reached 3.79% and GPT-4 Turbo 1.31% on the full set. These are original paper baselines.
- The oracle retrieval condition supplies files touched by the reference patch. The difference from BM25 helps explain why file selection matters.
- Proposed use. Pin the dataset split and revision, log patch application and both test groups, and review the patch separately.

## Publication and review scope

Carlos E. Jimenez, John Yang, Alexander Wettig, Shunyu Yao, Kexin Pei, Ofir Press and Karthik Narasimhan. ICLR 2024, arXiv:2310.06770v3 (November 11, 2024). Reviewed sections 2, 4, 5 and 7, Table 5 and Appendix A.4 on November 27, 2026 JST. No benchmark rerun.

## Evidence and limitations

- The pipeline filters PRs for a linked issue and test changes, runs reference tests on the original and fixed code, and excludes cases with unusable environments or without a demonstrated fail-to-pass test. This favors changes with executable test evidence.
- In v3 Table 5, Claude 3 Opus reached 3.79% resolved and 46.56% applied on the full set. GPT-4 Turbo reached 1.31% resolved and 26.90% applied. Applying cleanly and satisfying all required tests are separate outcomes. The results paragraph discusses Claude 2 at 1.96%, which is also reported under a particular context length in Table 2. The model comparison here uses the rows explicitly labeled in Table 5.
- The BM25 baseline retrieves relevant code files from the issue text and produces a patch. Oracle retrieval supplies the pre-fix contents of the files changed by the reference PR, so it assumes file-localization information unavailable for new issues. Full, Lite and Verified results require their corresponding split and evaluation setup.

## Application and low-cost check

Proposed and untried. Pick a routine local bug fix with a known base revision. Add a test that reproduces the problem and preserve an existing passing test. Apply a small candidate patch and record patch application, both test results and review observations on maintainability.

## Related notes

- [SWE-agent’s agent-computer interface](2024-swe-agent-computer-interface.md)
- [ReAct and tool-grounded prompting](2023-react-reasoning-and-acting.md)

## Sources

- [arXiv v3 record](https://arxiv.org/abs/2310.06770v3)
- [Full v3 text reviewed](https://arxiv.org/html/2310.06770v3)
- [SWE-bench project and leaderboard](https://www.swebench.com/)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
