**English** | [日本語](2026-google-alphaproof-code.ja.md)

# AlphaProof Code and machine-checked guarantees for libsignal

## Overview

- **What it is** Google DeepMind’s report on agent-assisted formal verification of libsignal.
- **What it says** Human-approved specifications, a model of AArch64 machine code and Lean proof checks connect selected guarantees to a compiled artifact.
- **Caveat** The guarantees depend on the selected binary, formal specification and trusted assumptions.

## Practical reading (six lines)

- The question is whether selected protocol properties can be established for compiled code.
- Experts review what the Lean specifications mean before agents attempt to prove them.
- A gatekeeper checks the resulting proofs with Lean against the approved statements.
- The report describes guarantees for selected properties of the PQXDH handshake and Triple Ratchet under its model.
- A proposed research-harness adaptation records the exact specification and artifact accepted by an independent verifier.
- A proof establishes the stated property under its assumptions. Specification fidelity and coverage still require review.

## Source and reading scope

Pushmeet Kohli and Swarat Chaudhuri, Google DeepMind announcement, 2026-11-10. Technical report by Swarat Chaudhuri, Andrew Ferraiuolo and colleagues. Checked 2026-11-11 JST, including the report’s abstract, verification workflow and scope.

## Method, evidence and limitations

The authors report approximately 6.5 million lines of checked Lean proof code and about 26,000 lines of trusted specifications and machine semantics. These figures describe their artifact, while general proof effort and review costs remain workload-specific. The result concerns selected properties for a particular libsignal build and execution model. The scope of those properties depends on the modeled platform and assumptions.

## Related work

- [AI discovery of formally verified quantum programs](2026-formally-verified-quantum-discovery.md)
- [Neuro-Formal Verification](2026-neuro-formal-verification.md)

## Free check and usage status

Proposed, untried. Choose a small owned deterministic program and state one invariant in a versioned specification. Record who reviewed the statement, the expected inputs, the code version and the acceptance check. Next read the report’s trusted computing base and scope sections in detail before applying the method elsewhere. Proof replay has yet to be performed for this note.

## Sources

- [DeepMind announcement](https://deepmind.google/blog/introducing-alphaproof-code/)
- [Technical report](https://google-deepmind.github.io/code-verification/)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
