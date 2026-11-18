**English** | [日本語](2026-aws-emulator-wsl2-s3-lambda.ja.md)

# AWS Emulator on WSL2: S3 and Lambda behavior

## Overview

- **What it is** A practitioner's AWS Emulator trial on a Windows PC.
- **What it says** S3 object round-trips and a small Python Lambda ran on WSL2.
- **Caveat** The tested Lambda accepted a role that did not exist.

## Practical reading (six lines)

- The author installed Linux package 1.0.500 under Ubuntu on WSL2.
- The CLI targeted the local emulator with separate credentials.
- The S3 test uploaded an object and retrieved its contents.
- The Lambda call returned the expected result from Python code.
- Use this as a smoke-test pattern for the application path.
- Check authorization separately because local success leaves IAM behavior untested.

## Source and reading scope

N-Kyo, Qiita, November 18, 2026. Read the article in a browser and checked the AWS overview and fidelity documentation on November 19, 2026 JST.

## Evidence and limitations

This is a single setup and two small successful paths. AWS documents Docker for Windows and a Linux package for Linux. The WSL2 installation is the practitioner's route. AWS also documents that policy evaluation differs and that fidelity varies by operation, especially for service data paths.

## Application and free check

Proposed and untried. Draft an offline test matrix for object round-trips, handler output, and authorization failures, with a separate evidence column for each.

Usage status is proposed. This reading note did not include deployment or independent reproduction.

## Related note

- [Related repository note](2026-aws-emulator-local-testing.md)

## Sources

- [Qiita article](https://qiita.com/N-Kyo/items/a111d174a751506790e2)
- [AWS Emulator overview](https://docs.aws.amazon.com/emulator/latest/userguide/what-is-service.html)
- [AWS fidelity documentation](https://docs.aws.amazon.com/emulator/latest/userguide/fidelity.html)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
