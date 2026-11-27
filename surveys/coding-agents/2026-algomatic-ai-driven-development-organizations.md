**English** | [日本語](2026-algomatic-ai-driven-development-organizations.ja.md)

# Algomatic’s prototype-led AI development and supervised automation

## Overview

- Yusuke Shibuya’s Architecture Conference 2026 talk on how Algomatic redesigned development around coding agents.
- It introduces shared prototypes, a workflow with explicit controls, and a feedback loop based on human interventions.
- The slides present one organization’s practices and measurement definitions. They provide no controlled estimate of lead-time or quality gains.

## Six practical takeaways

- Making code faster can shift delays to requirements, review, and testing. The talk frames these as development-wide bottlenecks.
- Product, design, engineering, and QA discuss a working prototype to spot disagreements before production implementation.
- The harness defines sequencing, permissions, retries, and stop conditions. Agents implement changes and perform checks in that workflow.
- During execution, people can see progress and take over. They choose the direction and make the final acceptance decision.
- The talk proposes measuring the share of runs that submit PRs without intervention, the share of PRs merged without human rework or follow-up requests, and the cost per submitted PR.
- A team could trial one low-risk change type and log where human intervention was needed, alongside rework and review time.

## Source and verification scope

- Primary source checked on 2026-11-28 using the public slide transcript. Slides 12–27, 32–35, and 41–57 support the points below.
- Yusuke Shibuya (Algomatic). *組織で結果を出すAI駆動開発 全開発工程を自動化するアーキテクチャ設計の実践知*. Architecture Conference 2026, 2026-11-27.
- [Speaker Deck slides](https://speakerdeck.com/sergicalsix/ai-driven-development-in-organizations/)

## Prototype and workflow

The team uses a working prototype to draw feedback from all roles early. It iterates on the prototype and the code with production reuse in mind. The talk illustrates a progression through four versions of the harness and describes consolidating steps after making rules explicit.

## Measurement boundary

Creation rate uses runs as the denominator. Merge rate uses PRs and tracks whether humans had to revise them or ask for more work. The cost includes AI usage and human time. A merge that needed no rework can still involve a human acceptance decision.

## Evidence and related work

The deck includes an illustrative lead-time example, an Issue and PR example, and a chart of core harness code size. It does not quantify the before-and-after change in team lead time or defect rates. [Platform engineering for AI agents and accountable teams](2026-jacopen-platform-engineering-agent-era.md) covers the shared controls that can support workflows like this one.

## Proposed small trial

For a low-risk change type, record time to acceptance, human review time, follow-up requests, and the verification evidence attached to each PR. Review frequent causes of intervention before changing workflow rules. Status is proposed. Effects outside the reported organization remain unverified.
