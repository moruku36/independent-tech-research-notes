# Connection Escrow: Holding AI-Agent Pod Egress in the Kernel Until an Isolated Verifier Rules

[日本語](2026-connection-escrow.ja.md) | [Theme index](README.md)

- **Source:** [arXiv:2610.26501v1](https://arxiv.org/html/2610.26501v1), independent preprint, 19 October 2026.
- **Author:** Ashok Subbabhatta Gopalakrishna.
- **Scope:** Main text and implementation/evaluation sections reviewed; code and experiments not independently reproduced.

## Summary
Connection Escrow is a prototype that holds outbound IPv4 TCP connections at a cgroup boundary while an isolated verifier decides whether to release them. A signed single-use verdict is bound to the socket and destination, and a timeout fails closed.

## Method and findings
The paper reports 36 adversarial checks and a single-node Kubernetes experiment involving 600 connections from six pods. A separate sequential microbenchmark of 200 connections reports a 4.29 ms median hold time and 6.82 ms p95 with native eBPF. This measures the evaluated hold, not an unconditional network latency guarantee.

## Practical interpretation
When designing an agent sandbox, consider a controlled egress boundary, explicit destination policy, timeouts and audit trails. Prototype separately in the actual kernel and workload, and address DNS and other protocols through additional controls.

## Limits
IPv6 is not implemented. UDP is pinned to configured DNS resolvers rather than held for verification; DNS lookups can reach authoritative servers before the TCP hold and can carry covert data through an authorized resolver. Node root is trusted. The TLS plaintext gate uses OpenSSL/Go uprobes, was evaluated only on loopback TLS 1.2 with a placeholder content model, and was not validated cluster-wide. It does not prove complete egress prevention.
