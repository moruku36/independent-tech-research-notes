**English** | [日本語](2026-google-llmjacking-cloud-resources.ja.md)

# Google/Mandiant: LLMJacking of cloud model resources

## Overview
- **What it is:** A Google Threat Intelligence Group and Mandiant incident-analysis article.
- **What it reports:** Attackers use exposed or stolen cloud identities to abuse and sometimes resell access to model resources.
- **Caveat:** It describes the company's observed cases, not a representative industry-wide prevalence or loss estimate.

## Source and scope
Christopher Romano, Codi Starks, Garrett Mahoney, John Wolfram, Josh Murchie, K Singh, Mathew Potaczek, Mike Lombardi and Rik Dolfing, [The Rise of LLMJacking: How Threat Actors Monetize Compromised Cloud and Model Resources](https://cloud.google.com/blog/topics/threat-intelligence/llmjacking-monetizing-compromised-cloud-models/?hl=en), Google Threat Intelligence Group / Mandiant, 2 November 2026. On 3 November 2026 JST, direct retrieval of the specified URL returned an internal error; selected text of the same official page was obtained in search results. Full page display, figures and exhaustive rule details were not verified; no independent validation.

## Incident pattern and evidence
Mandiant reports multiple 2026 incidents in which actors used cloud or LLM credentials to access model capacity. Some added permissions or credentials, ran high-volume inference or provisioned GPUs. GTIG also describes “LLM Mixers” that proxy and resell access. These are company observations and analysis, not independently established prevalence.

Google reports individual incidents exceeding USD 100,000 in fraudulent charges in one day and cumulative charges reaching USD 1 million at some organizations. The denominator is not specified, so these are not typical-loss estimates. The article also describes low-volume credential validation requests. Predictions about future growth and division of labor are GTIG's analysis, not established forecasts.

## Proposed applications
Inventory and monitor service accounts, keys, service enablement and privilege changes across cloud providers and model gateways. Use scoped identities, short-lived credentials where feasible, and close unnecessary public endpoints. Monitor both spend spikes and suspicious low-volume validation. Alerts do not guarantee a spending stop: verify actual quota, hard-limit and shutdown mechanisms per service. Prepare credential revocation, session invalidation, evidence preservation and billing investigation. These are proposals, not tested in the user's environment.

[Security governance index](README.md)
