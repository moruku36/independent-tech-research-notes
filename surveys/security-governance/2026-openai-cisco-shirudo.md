**English** | [日本語](2026-openai-cisco-shirudo.ja.md)

# Shirudo: temporary live protection while Linux patches roll out

## Overview

- OpenAI and Cisco introduced Shirudo as an open-source Linux runtime for temporary mitigations during patch rollout.
- Shirudo lets operators observe the likely impact of a shield, approve it, and apply targeted protection to a running service.
- The announcement reports a controlled demonstration. The repository describes the project as pre-release and lists production prerequisites.

## Six practical takeaways

- A shield gives service owners a temporary way to reduce exposure while they test and deploy a permanent patch.
- Shirudo uses eBPF for kernel-level observation and enforcement. The repository also describes signed Java upatches for application-level safeguards.
- Operators can observe proposed changes before enforcement and approve the shields that go into service.
- Signature verification checks provenance against trusted keys. TPM-signed evidence lets operators verify the measured set of loaded mitigations.
- The authors report that a Codex-generated shield stopped an attempt in their controlled Elasticsearch test while the service stayed running.
- A rollout review should cover legitimate traffic, application compatibility, load and latency, and removal after the permanent patch lands.

## Publication and review scope

OpenAI and Cisco announcement, November 23, 2026. Reviewed the announcement and the Shirudo project repository on November 25, 2026 JST. This note is based on public materials.

## Evidence and limitations

- The project separates authorization of an upatch from evidence of what a host has loaded. Assess coverage of vulnerable code paths and effects on valid traffic with workload-specific tests.
- The reported Elasticsearch test is one controlled case. The announcement gives no fleet-wide false-positive or service availability measurements.
- The project repository lists a Linux kernel with the signed-loader ABI and Shirudo patches plus TPM 2.0 for production targets. Host preparation and workload compatibility matter when interpreting the live deployment demonstration.

## Application and low-cost check

For a defensive evaluation, use benign representative requests in a staging service. Record behavior before and during enforcement, observe error rates and latency, and verify that an approved change can be removed and the measured state checked.

## Related notes

- [Ubuntu security layers](2026-npaka-ubuntu-security-layers.md)
- [Multi-cloud security architecture](2026-multi-cloud-security-architecture.md)

## Sources

- [OpenAI and Cisco announcement](https://openai.com/index/introducing-shirudo/)
- [Shirudo project repository](https://github.com/shirudo-dev/shirudo)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
