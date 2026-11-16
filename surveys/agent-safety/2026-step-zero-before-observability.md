**English** | [日本語](2026-step-zero-before-observability.ja.md)

# Step Zero: safety before an agent can inspect an input

## Overview

- **What it is**: A preprint on harm during an agent's first processing of opaque inputs.
- **What it says**: Produced-byte gates address effects that occur before model-side inspection.
- **Caveat**: Protection covers routed calls; bypasses and cumulative budgets remain deployment issues.

## Practical reading (7 lines)

- The question is whether acquiring information already changes the environment unsafely.
- Seven harnesses and six models process crafted inputs and matched benign twins.
- 32/42 pairs exceed the archive budget; 26/42 do so before member content reaches the model.
- Proposed use: put bounded observation and staging before committing imported artifacts.
- Treat a safe tool's availability separately from enforcement across all processing routes.
- Proposed measurement: count rejected writes, peak output and legitimate task completion separately.
- This testbed does not establish the safety or vulnerability of the user's current setup.

## Bibliography and reading scope

Tian Qin, Yuhang Jiang, Junzhe Chen, Lit Sin Tan, Lijie Wen. *Step-Zero Attack: Agent Safety Before Observability*. arXiv:2611.01953v1, 2026-11-01.

Checked 2026-11-17 JST. Primary HTML §§III–VII and IX checked, including Tables II–IV and the aligned-carrier bypass. Partial reading / not reproduced. Code release is promised upon acceptance; availability was not independently verified.

- [arXiv record and version history](https://arxiv.org/abs/2611.01953v1)
- [Inspected full text](https://arxiv.org/html/2611.01953v1)
- [DOI](https://doi.org/10.48550/arXiv.2611.01953)

## Method, evidence and limitations

The hidden 4 MiB threshold measures availability, not a recommended production limit. SZSP counts output before staged commit. An aligned-carrier live run still breaches in 1/28 cases through an absolute-path bypass; the enforced network write contract is future work. Per-call bounds do not bound cumulative output. Few fixtures and a shared API gateway limit generalization (§IX).

## Comparison with related notes

[AgentCap](2026-agentcap-runtime-authorization.md) checks authorization at the tool boundary. My reading: authorized processing also needs bounded side effects; permission and resource accounting answer different questions.

## Free-to-run check and usage status

Proposed, free and unrun: use a tiny offline mock importer that emits ordinary bounded byte chunks, with an immutable test budget. Check below/exactly/above-budget output, two consecutive calls, rejection without final-file changes, and a deliberately unregistered mock route. No malicious archive is needed. Next inspect tool routing and cumulative accounting before considering any deployment. No extractor, payload, model run or environment audit was performed.

Usage status: proposed / untrialed / not adopted.

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
