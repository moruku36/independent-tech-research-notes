**English** | [日本語](2026-microsoft-ai-ignite-mai-models.ja.md)

# Microsoft AI at Ignite 2026: model benchmarks, pricing, and access

## Overview

- **What it is**: Microsoft AI’s Ignite 2026 announcement for its MAI model family, model routing, and licensed deployment.
- **What it says**: Microsoft reports competitive scores and lower costs for selected tasks. The companion announcements document pricing assumptions and different access stages.
- **Caveat**: Coding cost ratios use promotional MAI prices. Benchmark results, preview terms, and customer case studies each have a limited scope.

## Practical reading (six lines)

- The announcement addresses the cost of running specialized models for frequent enterprise tasks.
- Microsoft reports that MAI Code 2 reaches 98% of GPT-6.1 Sol’s benchmark performance at 40% of its cost across four coding benchmarks.
- The coding evaluation uses maximum reasoning and a 50%-discounted MAI price. Three of the four benchmarks use the GitHub Copilot CLI with subagents disabled.
- Image 2.7 was announced in public preview, while Realtime 1 has separate charges for speech and reasoning and entered limited-access Foundry preview.
- Microsoft-Decision-1.1 was announced as generally available for decisions such as model routing. Licensed Weights was marked as forthcoming through Frontier Company engagements for deployment in a customer’s Azure environment.
- Proposed application: measure cost per accepted change on representative tasks and record prices, retries, review time, and access conditions.

## Source and reading scope

Microsoft AI, November 17, 2026. The launch article and selected passages in the companion sources below were checked on November 21, 2026 JST. Availability and prices refer to the announcements. Benchmarks, customer examples, and deployment behavior remain independently unverified.

## Evidence and limitations

| Area | What Microsoft reports at launch | Conditions that affect interpretation |
| --- | --- | --- |
| MAI Code 2 and Code 2 Flash | Code 2 reached 98% of GPT-6.1 Sol’s score at 40% of its cost and 96% of Claude Opus 5.5’s score at 5% of its cost across four benchmarks. Flash showed comparable scores to GPT-6 Luna and Claude Haiku 5.5 at 65% and 20% of their respective costs across three benchmarks. | Ratios are relative to each comparator. Microsoft cites maximum reasoning and a 50% promotional MAI price. DeepSWE 1.1, TerminalBench 2.1, and SWE-Atlas ran on Microsoft’s MSBench using the GitHub Copilot CLI with subagents disabled. Code 2 adds Artificial Analysis FrontierCode v1.1. Both models were announced in GitHub Copilot, with a limited-access Foundry preview for Flash. |
| MAI Image 2.7 and Flash | Microsoft cites first place for Image 2.7 on the Artificial Analysis image-editing leaderboard and published approximate Foundry costs of USD 35 and USD 10 per 1,000 images, respectively. | Both were announced in public preview. The cited ranking covers editing, and the cost depends on the image request. |
| MAI Realtime 1 and Dragon Copilot Transcribe | Realtime 1 starts at USD 0.01 per audio minute. Dragon Copilot Transcribe uses MAI Transcribe 2, with Microsoft reporting fewer multilingual transcription errors. | The Realtime footnote bills reasoning separately at USD 1 per million input tokens and USD 5 per million output tokens. The transcription comparison is a vendor-reported workflow result. |
| Microsoft-Decision-1.1 and MAI Licensed Weights | The routing and classification model reached GA in Foundry and was offered through OpenRouter and Vercel. Licensed Weights describes customer-controlled deployment, access, and adaptation in Azure. | Routing results depend on the task and deferral policy. The licensing article says availability is forthcoming through Frontier Company engagements. The scope of individual license terms was outside this reading. |
| MAI Cyber 2 Flash and Maia 200 | The launch discusses a model for defensive security teams and reports that the Maia 200 accelerator is running Microsoft models in production. | Security benchmark results cover the evaluated configuration. Accelerator efficiency is reported in tokens per watt, a separate measure from the cost of completing a task. |

The cost ratios summarize the selected benchmark suites. A repository’s acceptance rate, retries, and human review time can change the effective cost per accepted change. The announcement gives distinct signals for benchmark performance, usage, and release stage.

## Application and free check

Proposed. Create a small set of synthetic or public coding tasks with fixed tests and review criteria. Prepare a local worksheet that calculates cost per accepted change from success, retries, inference prices, and review time. Use hypothetical costs to compare promotional and regular-rate scenarios before scheduling a product trial.

## Related notes

- [Microsoft’s Ignite keynote on the enterprise AI stack](2026-microsoft-ignite-frontier-ecosystem.md)
- [Azure’s Ignite announcement on deployment and operations](2026-azure-ignite-platform-announcements.md)

## Sources

- [Microsoft AI launch overview](https://microsoft.ai/news/microsoft-ignite-2026/)
- [Code 2 and Flash evaluation notes](https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/)
- [Image 2.7 release and preview](https://microsoft.ai/news/introducing-mai-image-2-7/)
- [Realtime 1 billing details](https://microsoft.ai/news/introducing-mai-realtime-1/)
- [Decision 1.1 availability and evaluation](https://commandline.microsoft.com/microsoft-decision-model-ga/)
- [Licensed Weights announcement](https://microsoft.ai/news/introducing-mai-licensed-weights/)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
