**English** | [日本語](2026-google-cloud-sovereign-ai-europe.ja.md)

# Google Cloud sovereign AI in Europe: deployment and control boundaries

## Overview

- **What it is** A Google Cloud announcement about European sovereign AI options.
- **What it says** It distinguishes public-cloud controls, partner-operated infrastructure, and customer-site deployment.
- **Caveat** Availability and qualification vary by service, deployment, and region.

## Practical reading (six lines)

- Data Boundary adds controls to the public cloud. Dedicated uses a local operator. Distributed Cloud runs on customer premises.
- Gemini for Dedicated was announced as forthcoming.
- S3NS announced general availability of managed model serving on France’s PREMI3NS for open or customer-provided models.
- Confidential External Key Management was in preview. Customers or partners retain root key control.
- The Swiss Data Boundary framework was available. The EU DORA framework was planned.
- Review controls per workload and verify that the relevant service is inside the claimed qualification scope.

## Source and reading scope

Jai Haridas, Google Cloud Blog, November 17, 2026. Checked the canonical article and the linked S3NS announcement on November 21, 2026 JST. Status labels are from those announcements.

## Evidence and limitations

S3NS describes its underlying infrastructure as SecNumCloud 3.2-qualified and says extension to the new managed AI service layer was still in progress. Google describes cEKM as keeping root key control outside Google Cloud while running key operations in an attested environment. These are provider descriptions. Operational performance and workload-specific compliance were not independently tested.

## Application and free check

Proposed and untried. Build a local worksheet for one fictional workload with fields for operator, processing and storage location, key custody, audit evidence, service stage, and reported qualification scope.

## Related note

- [AWS Well-Architected Foundations and Workloads](../cloud-resilience/2026-aws-well-architected-foundations-workloads.md)

## Sources

- [Google Cloud announcement](https://cloud.google.com/blog/products/identity-security/sovereign-ai-on-your-terms-made-with-europe)
- [S3NS managed inference announcement](https://www.s3ns.io/en/news/ai-PREMI3NS-model)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
