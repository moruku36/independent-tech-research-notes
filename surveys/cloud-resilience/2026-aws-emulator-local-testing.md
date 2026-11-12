**English** | [日本語](2026-aws-emulator-local-testing.ja.md)

# AWS Emulator for local application testing

## Overview

- **What it is** AWS’s announcement of a local AWS API emulator.
- **What it says** Existing SDK and CLI clients can use a local endpoint for testing, with embedded mode for Rust tests.
- **Caveat** API coverage and behavior are incomplete. IAM, cross-account and cross-Region behavior need cloud-side testing.

## Practical reading (six lines)

- The emulator supports local edit–test loops for developers and coding agents.
- A local endpoint supplies generated credentials and configuration.
- Separate embedded instances can isolate Rust test state.
- Unimplemented operations return an explicit error.
- A proposed harness trial compares local contract checks with later AWS integration tests.
- Windows and macOS use Docker in the documented installation path.

## Source and reading scope

Daniel Abib, AWS News Blog, 2026-11-11. Checked 2026-11-13 JST. The Japanese URL was unavailable to the web reader, so the English original and official overview were used. Selected workflow and limitation sections read.

## Content, evidence and limitations

The service announcement describes no additional emulator service fee. AWS resources used later remain billable. The launch article identifies IAM evaluation and cross-account or cross-Region behavior as limitations. Coverage grows through a development process using agents and review.

## Related notes

- [AI-generated Terraform guardrails](2026-ai-generated-terraform-guardrails.md)

## Free check and usage status

Proposed, untried. Define a small storage operation and its expected results using dummy data. Check local behavior before a separately scoped integration test. Next inspect operation coverage and differences in authorization and deployment behavior. No installation or cloud resources were created.

## Sources

- [Submitted Japanese URL](https://aws.amazon.com/jp/blogs/aws/test-your-applications-against-aws-locally-with-aws-emulator/)
- [English original](https://aws.amazon.com/blogs/aws/test-your-applications-against-aws-locally-with-aws-emulator/)
- [Official overview](https://docs.aws.amazon.com/emulator/latest/userguide/what-is-service.html)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
