**English** | [日本語](2026-anthropic-claude-ship-review-approval.ja.md)

# Claude Ship: pull request review, remediation, and approval

## Overview

- **What it is**: Anthropic’s release announcement for a GitHub pull request workflow on Claude Team and Enterprise.
- **What it says**: Code Review reports findings, PR Steward works on fixes, and Claude Approvals applies a repository policy.
- **Caveat**: The two new components are in beta. Availability, charges, and approval authority depend on the organization and repository.

## Practical reading (six lines)

- Code Review is generally available and posts findings on pull requests.
- PR Steward is in beta and handles issues such as failed checks or review feedback. Its role stops before approval and merge.
- Claude Approvals is in beta and can approve routine changes when the repository policy allows it.
- Observe mode reports what it would decide. Required checks, branch protections, and permissions still govern merging.
- Anthropic lists Zero Data Retention, HIPAA configuration, and customer-managed encryption keys as exclusions. A policy can incur review charges in observe mode.
- Proposed use: compare observe-mode decisions with human reviews on past changes before relying on a required approval check.

## Source and reading scope

Anthropic, November 23, 2026. Checked the announcement and product page on November 24, 2026 JST. No repository settings were changed and no product trial or outcome replication was performed.

## Evidence and limitations

- **Roles and enforcement.** The announcement assigns findings to Code Review, corrective pushes to PR Steward, and approval decisions to Claude Approvals. Policies come from the connected repository’s default branch. Existing GitHub branch protections and required checks govern whether a pull request can merge.
- **Availability and evidence.** The launch focuses on GitHub repositories on Team and Enterprise. The article reports higher merged-PR volume and a lower share of reversions for the Claude Code team within a broader workflow. That comparison cannot establish the separate effect of Claude Ship. Observe-mode review can be billable when the policy invokes Code Review.

## Application and free check

Proposed. Classify fictional pull requests by whether a person must approve, bind review evidence to the current commit, and compare the proposed decisions with a human baseline. Include cases where CI was rerun or a policy change requires review.

## Related note

- [Claude Code verification practices](2026-claude-code-verification-practices.md)

## Sources

- [Claude Ship announcement](https://claude.com/resources/articles/introducing-claude-ship)
- [Requested Japanese page](https://claude.com/ja/resources/articles/introducing-claude-ship)
- [Claude Ship product page](https://claude.com/product/claude-ship)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
