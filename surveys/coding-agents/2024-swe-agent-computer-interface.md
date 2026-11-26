**English** | [日本語](2024-swe-agent-computer-interface.ja.md)

# SWE-agent: interfaces designed for software engineering agents

## Overview

- A NeurIPS paper on agent-computer interfaces for repository maintenance tasks.
- SWE-agent uses purpose-built commands and feedback to help an LM inspect files, edit code and test patches. Its GPT-4 Turbo configuration resolved more SWE-bench Lite tasks than the same model with shell-only access.
- The comparison reflects the tested interface, models and benchmark splits. Table values make the comparison conditions explicit.

## Six practical takeaways

- SWE-agent gives the model structured search, windowed files and edit feedback, with concise observations after actions.
- With GPT-4 Turbo, it solved 286 of 2,294 full SWE-bench instances (12.47%) and 54 of 300 Lite instances (18.00%).
- In the same-model Lite comparison in Table 1, the shell-only agent reached 11.00%. SWE-agent's 18.00% is seven percentage points higher.
- Table 3 reports 18.0% for summarized search, 12.0% for iterative search and 15.7% when the dedicated search interface is removed.
- The editor, file viewer and history also affected scores. Passing the benchmark tests measures one attempt against the benchmark criteria.
- Proposed use. Keep the model, tasks and budget fixed when comparing tool interfaces, then review extra calls, errors and patch quality.

## Publication and review scope

John Yang, Carlos E. Jimenez, Alexander Wettig, Kilian Lieret, Shunyu Yao, Karthik Narasimhan and Ofir Press. NeurIPS 2024, arXiv:2405.15793v3 (November 11, 2024). Reviewed sections 3–5 and Tables 1 and 3 on November 27, 2026 JST. No reproduction.

## Evidence and limitations

- Table 1 records 18.00% versus 11.00% on Lite for GPT-4 Turbo. The introduction instead gives a 10.7-point improvement over a shell baseline. This note uses the explicitly paired table rows for the same-model comparison.
- Table 3 reports 18.0% for the default 100-line view and 12.7% for showing the full file. With syntax linting, the edit variant reaches 18.0%, compared with 15.0% for the edit action alone. These ablations apply to the configurations the authors tested.
- The per-instance API budget was $4. The average cost metric only covers resolved instances. Benchmark success tests the resulting patch against the task's tests. Review for integration and maintainability remains a separate activity.

## Application and low-cost check

Proposed and untried. Use a small set of ordinary bug fixes in a local test repository. Keep time and model settings fixed and vary only the search or viewing interface. Compare resolved tasks, calls, failed edits and review findings.

## Related notes

- [ReAct and tool-grounded prompting](2023-react-reasoning-and-acting.md)
- [FrontierHarness evaluation](2026-frontierharness-eval-v1-1.md)

## Sources

- [arXiv v3 record](https://arxiv.org/abs/2405.15793v3)
- [Full v3 text reviewed](https://arxiv.org/html/2405.15793v3)
- [NeurIPS 2024](https://proceedings.neurips.cc/paper_files/paper/2024/hash/5a7c947568c1b1328ccc5230172e1e7c-Abstract-Conference.html)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
