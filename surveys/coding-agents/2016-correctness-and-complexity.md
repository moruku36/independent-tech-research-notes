**English** | [日本語](2016-correctness-and-complexity.ja.md)

# Why Writing Correct Software Is Hard

## Overview

- **What it is** A 2016 press ron essay on program correctness and verification complexity.
- **What it says** It discusses model checking, deductive proof and abstraction as ways of handling verification costs.
- **Caveat** This is an expository argument. Its worst-case results need their stated assumptions and do not measure a particular tool.

## Practical reading (six lines)

- The essay asks why correct software remains difficult to produce.
- State-space growth limits general model-checking procedures.
- Deductive methods can use problem structure and carefully designed programs.
- Abstraction reduces the state space while limiting the properties established.
- A proposed agent workflow states the property and accepted uncertainty before choosing a verifier.
- Faster proof construction still requires checking that the specification captures the intended behavior.

## Source and reading scope

press ron, Why Writing Correct Software Is Hard, 2016-07-23. Checked 2026-11-13 JST, selected sections on model checking, proofs, abstraction and types. Proofs and cited results were not independently rederived.

## Content, evidence and limitations

The discussion links verification difficulty to the problem class and representation. Its general complexity arguments require care when applied to restricted programs or specific properties. Modern AI-assisted verification offers a related workflow question, with no performance comparison here.

## Related notes

- [AlphaProof Code](2026-google-alphaproof-code.md)

## Free check and usage status

Proposed, untried. Select a small owned program and one invariant. Compare a concrete model with an abstraction, recording which conclusions each supports. Next inspect the assumptions behind any theorem used to justify the design.

## Sources

- [Submitted essay](https://pron.github.io/posts/correctness-and-complexity)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
