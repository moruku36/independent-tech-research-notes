**English** | [日本語](2026-agentcap-runtime-authorization.ja.md)

# AgentCap: runtime authorization at the tool boundary

## Overview

- **What it is** Research on authorizing each model-proposed tool call outside the model.
- **What it says** An MCP wrapper checks policy and validates short-lived, budget-bounded capabilities.
- **Caveat** Reported zero attack success applies to specific evaluations; utility and policy coverage remain constraints.

## Practical reading (six lines)

- Policies check intent, prerequisites, incompatible authority and argument provenance.
- Delegation preserves action/resource and can only reduce lifetime and budget.
- GPT-5.4 reaches zero ASR on both evaluated benchmarks.
- GPT-4o retains residual attacks and some benign utility is lost.
- Each model–benchmark condition is one run, without variance estimates.
- Proposed application: validate scope, provenance and delegation in a deterministic mock tool gateway.

## Source and reading scope

Aravinda Kashyap Kabbinamakki Suresh and Peng Gao, AgentCap: Capability-Based Runtime Authorization for Secure LLM Agent Execution. arXiv:2611.00729v1, 2026-10-31. Checked 2026-11-15 JST, selected §§3–4 and 6. arXiv reports non-archival workshop acceptance; venue independently unverified.

## Evidence and limitations

AgentDojo has 97 benign tasks and 949 attacked instances; InjecAgent has 1,054 attacked instances plus constructed clean cases. Policies are application specifications. Unbound arguments, unlabeled provenance and textual effects leave gaps. Persistent-memory/cross-context provenance and independent administrative domains remain future work.

## Related notes

- [Human approval boundaries](2026-inalienable-human-approval.md)
- [Cairn misuse investigation](../security-governance/2026-cairn-autonomous-intrusion-report.md)

## Free check and usage status

Proposed, untried. Use free synthetic requests and a mock local tool, testing expiry, budget reuse, cross-session replay, unsupported recipients and attenuated delegation while retaining valid calls. Record denials and legitimate task completion separately. Next inspect trusted-field definitions, policy coverage and audit integrity before implementation. No real credentials or external actions are needed.

## Sources

- [Submitted source](https://arxiv.org/abs/2611.00729v1)
- [Inspected text](https://arxiv.org/html/2611.00729v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
