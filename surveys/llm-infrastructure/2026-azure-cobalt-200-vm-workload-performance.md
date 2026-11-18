**English** | [日本語](2026-azure-cobalt-200-vm-workload-performance.ja.md)

# Azure Cobalt 200 VMs: workload performance and availability

## Overview

- **What it is** Microsoft's general availability announcement for Cobalt 200 Arm VMs.
- **What it says** The launch lists 14 regions and vendor-reported improvements over Cobalt 100.
- **Caveat** Workload examples and customer statements have different evidence and scope.

## Practical reading (six lines)

- The planned 23 regions by year-end are a rollout target.
- Microsoft reports up to 1.5× performance for agent tool execution versus Cobalt 100.
- The examples focus on CPU-side work such as tool sandboxes and compilation.
- The processor mode trades consistent frequency for opportunistic boost.
- Confirm Arm64 images, native dependencies, and the required VM size.
- Benchmark equivalent workloads with tail latency and cost per successful job.

## Source and reading scope

Rani Borkar and Arun Kishan, Microsoft Azure Blog, November 17, 2026. Checked the announcement's workload, processor mode and availability sections on November 19, 2026 JST.

## Evidence and limitations

The announcement gives up to 1.5× for web serving, up to 1.6× for Java and 1.9× for database workloads, versus Cobalt 100. Detailed settings for those headline figures are not provided in the announcement. Quotes from customers describe their deployments. No independent benchmark or deployment was checked.

## Application and free check

Proposed and untried. Start with an offline comparison sheet for a representative build or tool job. Specify cores, memory, I/O, concurrency, and a performance target before pricing candidate sizes.

Usage status is proposed. This reading note did not include deployment or independent reproduction.

## Sources

- [Microsoft Azure announcement](https://azure.microsoft.com/en-us/blog/azure-cobalt-200-vms-now-available-proven-on-real-workloads-and-built-for-the-agentic-era/)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
