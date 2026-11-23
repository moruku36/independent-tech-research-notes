**English** | [日本語](2026-formally-verified-quantum-discovery.ja.md)

# AI discovery of formally verified quantum programs

## Overview

- **What it is**: A quantum-program discovery preprint.
- **What it says**: AI search is checked against formal correctness and cost specifications.
- **Caveat**: Resource-model reductions are not measured hardware speedups.

## Practical reading (six lines)

- Researchers define the problem before agent search.
- Lean checks programs and their cost proofs.
- An external checker protects the frozen specification.
- Our proposal: isolate evaluation from candidate editing.
- Share proven artifacts separately from conjectures.
- Formal validity still depends on specification fidelity.

## Bibliography and verification scope

Sergey Shirobokov, Ben Jaderberg et al. (25 authors), 2026. arXiv:2611.09822v2, revised 2026-11-09; first submitted 2026-11-06. Venue unconfirmed.

Checked 2026-11-10 JST: primary HTML §§1, selected §2 results, §3, and Appendices B–D. Partially read; proofs, implementation and experiments not independently checked or reproduced.

## Method, evidence and limits

Gemini 4 Carbon teams use a shared wiki and discussions. Independent replay checks theorem/definition identity, allowed axioms and cost. Reported 290× arcsin improvement concerns logical qubits × T gates; other tasks use different metrics. Specification loopholes still required human correction. At the first reading, Reference 44 described a planned code release.

## Follow-up on November 24, 2026 JST

DeepMind’s November 23 article links the same arXiv paper, now at v3 (revised November 16), and the public Lean 4 project. Selected v3 passages and the repository README were checked. The public project includes a core library and a separate specification and benchmark library, with dependencies pinned in the repository. The code and proofs were not built or independently checked for this follow-up.

The update confirms that the reported 290× result for fixed-point arcsin refers to the modeled spacetime cost, measured in logical qubits × T gates. The maximum 2.57× for parallel Grover search refers to expected oracle rounds for finding all marked targets under the stated conditions. Both are resource-model comparisons. The news article’s publication does not add a hardware-runtime measurement.

## Related work and interpretation

[Neuro-Formal Verification](2026-neuro-formal-verification.md) helps frame the difference between proving a statement and faithfully modeling the intended problem. [Organon](2026-organon-scientific-discovery.md) is a procedural comparison, not a matched benchmark. Do not attribute the reported gain solely to adding agents or meetings.

## Free check plan and usage status

Proposed only: take a small owned classical specification, freeze its revision, and inspect how altered definitions or unproved assumptions would be rejected. Keep valid artifacts, tentative ideas and failed approaches in separate records. This can begin as a document audit without model calls, installation or quantum hardware.

For an AI-scientist harness, propose an external acceptance receipt linking the immutable specification, candidate and evidence. This adaptation has not been tested. Before attempting reproduction, inspect the released artifacts, trusted dependencies, resource assumptions, and total discovery cost.

## Primary sources

- [Requested record](https://arxiv.org/abs/2611.09822)
- [Inspected v2](https://arxiv.org/html/2611.09822v2), especially §1.2 and Appendix B
- [Versioned bibliography](https://arxiv.org/abs/2611.09822v2)
- [DeepMind follow-up article](https://deepmind.google/blog/finding-faster-quantum-algorithms-with-agents-and-formal-verification/)
- [Selected v3 passages](https://arxiv.org/html/2611.09822v3)
- [Published Lean project and specifications](https://github.com/google-deepmind/formal-quantum-computation)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
