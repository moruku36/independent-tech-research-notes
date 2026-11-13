**English** | [日本語](2026-facestealer-video-social-engineering.ja.md)

# FaceStealer: video impersonation and maintainer compromise

## Overview

- **What it is** News report on FaceStealer, a social-engineering campaign targeting crypto holders and software maintainers.
- **What it says** FBI reports over $400 million stolen in 18 months and over 900 seized webcam recordings.
- **Caveat** Official attribution and totals were cross-checked; the underlying incidents were not independently investigated.

## Practical reading (six lines)

- Hijacked trusted accounts lead targets into impersonated video meetings.
- A supposed technical fix is used to induce device compromise.
- FBI says stolen genuine footage remains predominant, alongside emerging synthetic video.
- Maintainer devices and repository accounts create a software-supply-chain exposure.
- FBI recommends official meeting applications and confirmation through another channel.
- Proposed application: rehearse a benign meeting-invite verification workflow and isolate repository credentials.

## Source and reading scope

Ravie Lakshmanan, The Hacker News, 2026-11-13. Checked 2026-11-14 JST. Article text available through search and a mobile result; selected FBI overview, FLASH summary/additional warnings/recommendations and DOJ release dated 2026-11-12 checked. No incident reproduction.

## Method, evidence and limitations

The loss total concerns the campaign, not a measured total caused solely by generated video. DOJ separately describes authorization to seize or restrain more than $1.2 billion from the Binance theft; it is a different event and measure. Additional interview-campaign anecdotes in the news were not all independently checked.

## Related notes

- [Agent approval and secret leakage](2026-apiiro-agent-approval-secret-leaks.md)

## Free check and usage status

Proposed, untried. Use a fictitious invitation and no executable payload to walk through checking the meeting app, confirming via a known alternate contact and declining in-call software-fix requests. Record which account could reach package publishing or repositories and where independent verification belongs. Next inspect existing recovery controls and the original incident evidence before making incident-specific claims. No accounts, credentials or security settings were changed.

## Sources

- [Submitted news report](https://thehackernews.com/2026/11/fbi-says-north-korean-hackers-stole.html)
- [FBI overview](https://www.fbi.gov/investigate/cyber/facestealer-cryptocurrency-theft-scheme)
- [FBI FLASH AC-111226-MS](https://www.ic3.gov/CSA/2026/261112.pdf)
- [DOJ announcement](https://www.justice.gov/opa/pr/justice-department-announces-actions-disrupt-north-koreas-massive-theft-cryptocurrency)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
