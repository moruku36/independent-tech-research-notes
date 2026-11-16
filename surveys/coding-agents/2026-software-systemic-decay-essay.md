**English** | [日本語](2026-software-systemic-decay-essay.ja.md)

# Software systemic decay: an argument about coherence and control

## Overview

- **What it is**: An opinion on software complexity, dependencies and AI-assisted development.
- **What it says**: The author argues that locally plausible changes can erode whole-system coherence.
- **Caveat**: Selected incidents and personal observations do not establish an industry-wide causal trend.

## Practical reading (6 lines)

- The question is who understands and controls an increasingly complex system.
- The essay links outsourcing of detail, dependency chains and AI-generated changes.
- Its core concern is loss of coherent intent, rather than only bad individual code.
- Proposed use: assign ownership of invariants and document why a change is needed.
- Review cross-component contracts and integration tests alongside local tests.
- Treat incident attribution and claims of widespread deskilling as unverified hypotheses here.

## Source and reading scope

Jimmy Breck-McKye, *Software is breaking down at a systemic level*, November 15, 2026. Practitioner opinion essay.

Primary article read in full in the rendered page on November 17, 2026. Linked incident accounts and quoted essays not independently audited.

- [Submitted source](https://www.breck-mckye.com/blog/2026/11/software-is-breaking-down-at-a-systemic-level/)


## Method, evidence and limitations

The piece uses outage and supply-chain examples to motivate “decoherence” and organizational cognition. It supplies no representative sample, counterfactual comparison or measurement separating AI from other changes.

## Related reading and comparison

[WorkflowArena](../llm-infrastructure/2026-workflowarena-executable-orchestration.md) offers a separate way to check integrated outcomes. The [MIT teaching note](../articles/2026-mit-htmaa-agentic-engineering-resources.md) offers verifier design ideas. Neither validates this essay's macro-level diagnosis.

## Free-to-run check and usage status

Proposed, free and unrun: inspect a small past change for duplicated concepts, inconsistent schemas and missing owners. Use one known integration failure and one correct change to check the review template. Record concrete contradictions rather than attributing every defect to AI. This audits a local process, not the essay's societal claim.

Usage status: proposed / untrialed / not adopted. No reproduction of the reported results is claimed.

## Unconfirmed points and next checks

Next: verify each incident against its primary report before reusing causal claims. A longitudinal comparison would be needed to measure whether coherence worsens with AI adoption.

[Category index](README.md) | [Reading list](../../docs/reading-list.md)
