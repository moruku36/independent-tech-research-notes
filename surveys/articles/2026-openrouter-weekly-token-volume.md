**English** | [日本語](2026-openrouter-weekly-token-volume.ja.md)

# OpenRouter usage: reading a weekly token snapshot

## Overview

- **What it is**: A news article ranking models by OpenRouter token volume.
- **What it says**: It reports 199T tokens so far for the week beginning November 9; 213T is a projection.
- **Caveat**: Token traffic is not user count, revenue, quality or industry-wide market share.

## Source and reading scope

- OfficeChai Team, *These Are The Top AI Models On OpenRouter By Number Of Tokens: November 2026*, November 15, 2026.
- Source URL: [Article / paper](https://officechai.com/ai/these-are-the-top-ai-models-on-openrouter-by-number-of-tokens-november-2026/).
- Article body and table checked on November 16, 2026. [OpenRouter's collection methodology](https://openrouter.ai/collections/programming/) was checked separately; its moving/category view does not authenticate this historical overall snapshot.

## Practical reading

- The question is which models account for a reported week's token traffic.
- The article summarizes an OpenRouter snapshot and a separate week-end projection.
- Its headline ranking concerns token volume, not model quality.
- Proposed use: preserve timestamp, period, category and model version with each comparison.
- Test candidates on fixed tasks using cost per accepted result before changing a default.
- Historical primary counts remain unverified; prose and table also disagree about second place.

## Method, evidence and limitations

The table leads with DeepSeek V4.1 Flash 1017 (55.4T, 27.8%), followed by Hy4. A prose claim that both top models are DeepSeek conflicts with that table. OpenRouter describes collection ranking by prompt plus completion tokens over a trailing seven days.

## Related reading and comparison

Keep this token-based snapshot separate from request- or spend-based production indexes; compare only after aligning metric, population and period.

[Vercel Production Index](2026-vercel-production-index-november.md)

## Free-to-run check

Free local check, proposed and unrun: transcribe the reported count, denominator, timestamp and forecast label into a small table; recompute shares and flag prose/table conflicts. A later live ranking is a new observation, not a correction of the earlier snapshot. No paid API call is needed.

- **Usage status**: Proposed / untrialed / not adopted. No implementation, reproduction or external-environment validation was performed.

## Unconfirmed points and next checks

Next: obtain a timestamped primary export for the exact historical window. User counts, spend and workload mix remain unverified; no causal explanation of popularity is established.

- Category index: [Index](README.md)
