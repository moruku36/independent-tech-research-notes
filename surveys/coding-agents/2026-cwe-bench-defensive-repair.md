**English** | [日本語](2026-cwe-bench-defensive-repair.ja.md)

# CWE-bench and evaluation of defensive repository repair

## Overview

- **What it is** Benchmark preprint about repository-level defensive auditing and repair.
- **What it says** It tests whether a patch satisfies security checks and preserves expected functionality. The highest reported configuration reaches 67.1% pass@1 and 79.2% pass@4.
- **Caveat** The results depend on the task mix, verifier coverage and model–harness combination.

## Practical reading (six lines)

- Agents receive the repository and threat model. The authors withhold the weakness type, location and number of affected sites.
- The evaluation covers 250 tasks, including 100 public and 150 held-out tasks, across 185 CWE types and eight languages.
- An automated verifier checks the security requirement and functional regressions together.
- Pass@1 averages per-task attempt success. Pass@4 counts tasks with any passing attempt out of four.
- For an owned-code review harness, a proposed check records security invariants, functional tests and retry costs separately.
- Table 3 reports model–harness configurations. It leaves the contribution of each component unresolved.

## Bibliography and reading scope

Gonzalo Gonzalez-Pumariega, Ajay Jagannath, Adit Jain, Guram Gogia, Soumyadeep Bakshi and Nazneen Rajani. arXiv:2610.17020v2, revised 2026-11-07, first submitted 2026-10-12. Partially read on 2026-11-11 JST, covering §§3–5 and Table 3.

## Method, evidence and limitations

Eleven configurations are compared. The top overall configuration in Table 3 is Claude Opus 5.5 with Claude Code. Retry gains and API cost differ even for configurations with similar single-attempt results. The authors describe automated and human review of verifiers. Any reported pass is scoped to the benchmark’s tested requirements and functionality. Pass@4 also assumes a way to recognize a passing patch under the benchmark verifier.

## Related work

AlphaProof Code uses machine-checked proofs for specified properties. CWE-bench measures whether patches meet executable benchmark checks. Each relies on the quality and scope of its acceptance criteria.

- [AlphaProof Code](2026-google-alphaproof-code.md)
- [Three pillars of agent oversight](../security-governance/2026-three-pillar-agent-oversight.md)

## Free check and usage status

Proposed, untried. Draft a test matrix for an owned, synthetic module using an access-policy invariant and expected behavior for authorized operations. Compare a single attempt with a fixed retry budget using the same acceptance checks. Record accepted patches, regressions and per-attempt cost. Next check verifier coverage and portability to the intended codebase. No benchmark runs were performed.

## Primary sources

- [arXiv record](https://arxiv.org/abs/2610.17020v2)
- [HTML full text](https://arxiv.org/html/2610.17020v2)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
