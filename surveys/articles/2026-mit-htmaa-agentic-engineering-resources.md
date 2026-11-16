**English** | [日本語](2026-mit-htmaa-agentic-engineering-resources.ja.md)

# MIT HTMAA 2026: fabrication resources and agentic engineering

## Overview

- **What it is**: A fabrication course collection, not one research paper.
- **What it says**: Its selected agent lecture links engineering tools, feedback and independent verification.
- **Caveat**: The slides synthesize research and teaching demos; the whole curriculum was not audited.

## Practical reading (6 lines)

- The question is how agents can use CAD, simulation and other engineering tools.
- The lecture compares code, structured/MCP calls and GUI interfaces.
- It emphasizes executable checks and separating proposal from evaluation.
- Proposed use: specify units, constraints and failure cases before generating an artifact.
- Parallelize independent evaluations only after measuring coordination and solver costs.
- The gear demo uses zero LLM tokens; it is not an AI-agent performance experiment.

## Source and reading scope

MIT Center for Bits and Atoms, *How To Make (almost) Anything*, MAS.863/4.140/6.9020, 2026 course site. Selected lecture: Ric Fulop, *Agentic Engineering*, October 1 recitation (cover also says September 2026).

Checked November 17, 2026: schedule, AI recitation index and Ric's slides; tool-interface and scripted-demo slides also visually checked. Sayam's slides partially inspected. Eitan's slides, other lectures and code not fully reviewed.

- [Submitted source](https://pub.cba.mit.edu/863.26/site/)
- [AI recitation](https://pub.cba.mit.edu/863.26/site/recitations/AI/index.html)
- [Ric's slides](https://pub.cba.mit.edu/863.26/site/recitations/AI/Ric.pdf)

## Method, evidence and limitations

Ric's pp.10, 30–33 distinguish tool access, simulation parallelism, verification and fabrication sign-off. The schedule covers design through integration; November 18 and later sessions were still scheduled as of this reading.

## Related reading and comparison

[Agent-scaling research](../llm-infrastructure/2025-scaling-agent-systems.md) is one cited empirical source; do not count its numbers again as an independent MIT experiment. Compare the teaching checks with [WorkflowArena](../llm-infrastructure/2026-workflowarena-executable-orchestration.md)'s integrated acceptance.

## Free-to-run check and usage status

Proposed, free and unrun: define a simple parametric shape with dimensional invariants; check a deliberately invalid and a valid artifact with an independent script. Record generation and verification separately. This is a schema/checker exercise, not a manufacturing safety certification or a reproduction of the solver demo.

Usage status: proposed / untrialed / not adopted. No reproduction of the reported results is claimed.

## Unconfirmed points and next checks

Next: review the specific assignment, tool licenses, verifier and referenced original papers before reproducing. No machine commands or workshop equipment were operated.

[Category index](README.md) | [Reading list](../../docs/reading-list.md)
