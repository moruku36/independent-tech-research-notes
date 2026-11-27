**English** | [日本語](2026-aws-cognito-plus-availability-sla.ja.md)

# Amazon Cognito Plus: the 99.99% availability SLA and application monitoring

## Overview

- An AWS Security Blog article explaining the higher monthly availability commitment for Cognito Plus user pools.
- From 2026-11-01, Plus moved to 99.99% per Region per billing cycle. Essentials and Lite retain 99.9%.
- The SLA uses a defined set of service errors and exclusions. AWS’s historical figures are request-weighted across Regions.

## Six practical takeaways

- The 99.99% commitment applies automatically to existing Plus user pools as of 2026-11-01.
- For each Region, the SLA averages five-minute percentages based on HTTP 500 and 503 responses. Intervals without requests count as 100% available.
- A 30-day time-budget analogy yields 4.32 minutes at 99.99%, while the contractual result comes from request measurements and exclusions.
- AWS's published regional aggregate reached 99.99% in ten of twelve months between November 2025 and October 2026.
- Measure sign-in success from the application's perspective, including client and downstream dependencies, alongside the Cognito SLA.
- Before changing tiers through the API or CLI, retrieve the existing settings and preserve them in the update. Omitted parameters can reset to defaults.

## Source and verification scope

- Evidence status: primary sources checked on 2026-11-28. The note uses the English AWS Security Blog article and the official SLA.
- Bibliography: Brian Song and Chris Simmons, *Planning for 99.99 percent availability with the Amazon Cognito Plus feature plan*, AWS Security Blog, 2026-11-25.
- Sources: [AWS Security Blog](https://aws.amazon.com/blogs/security/planning-for-99-99-percent-availability-with-the-amazon-cognito-plus-feature-plan/) · [Amazon Cognito SLA](https://aws.amazon.com/cognito/sla/).

## Measurement and credits

The service commitment is regional over a billing cycle. The agreement describes eligibility, claim requirements, credit tiers, and exclusions. A count of elapsed downtime alone does not reproduce the contractual calculation.

## Historical evidence

AWS reported 99.988% in January 2026 and 99.979% in March 2026, the two months below the new threshold in its retrospective. It weighted regional figures by request volume. Individual accounts and Regions can experience different availability.

## Related note

[AWS Well-Architected 2026: cloud foundations and workloads](2026-aws-well-architected-foundations-workloads.md) discusses shared controls and workload scope. The Cognito example shows how a component contract and a workload-level availability target use different measurement boundaries.

## Proposed check

In a spreadsheet, model synthetic five-minute bins with an empty bin, a bin with some 500 or 503 responses, and a bin with a client-side login failure. Calculate the SLA-style average and an application sign-in success rate under explicitly chosen rules. Status: proposed. Customer-side outcomes and an actual tier change remain untested.
