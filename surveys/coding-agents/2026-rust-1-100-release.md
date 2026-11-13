**English** | [日本語](2026-rust-1-100-release.ja.md)

# Rust 1.100: language, allocation and Cargo changes

## Overview

- **What it is** Official Rust 1.100.0 release announcement.
- **What it says** It stabilizes never-type and allocator facilities and updates Cargo’s dependency and build handling.
- **Caveat** Release features and migration considerations are described; performance on this workspace was not measured.

## Practical reading (six lines)

- The never type `!` is stable; fallback changes also affect pre-2024 editions.
- Core custom-allocation support covers `Vec` and `Box`; broader collection support remains ongoing.
- `DropGuard` provides closure-based cleanup when a value is dropped.
- Cargo reports unused dependencies under target-coverage conditions and revises its build-cache layout.
- Opt-in publication-age filtering excludes `cargo install` and registry entries without publication timestamps.
- Proposed application: check compatibility, dependency resolution and worktree builds before adopting the toolchain.

## Source and reading scope

The Rust Release Team, *Announcing Rust 1.100.0*, 2026-11-12. Checked 2026-11-14 JST. Official article partially read, focusing on never type, allocation, cleanup and Cargo. Full API audit and local compilation were not performed.

## Method, evidence and limitations

The unused-dependency warning does not cover dev-dependencies. Cache layout changes can affect scripts that assume internal paths. Publication cooldowns reduce some dependency risks but do not establish package safety. These are release-team statements, not comparative benchmark results.

## Related notes

- [Correctness and complexity](2016-correctness-and-complexity.md)
- [Git infrastructure for agents](2026-github-git-infrastructure-agent-scale.md)

## Free check and usage status

Proposed, untried. On a disposable local branch, first record toolchain and minimum supported Rust version, then plan the existing tests and build targets under the old and new versions. Inspect fallback warnings, lockfile changes and scripts using cache paths. A tiny local fixture can examine cleanup and allocation APIs without production dependencies. No toolchain was installed or upgraded. Next check the full release notes, affected target platforms and dependency fixes.

## Sources

- [Official announcement](https://blog.rust-lang.org/2026/11/12/Rust-1.100.0/)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
