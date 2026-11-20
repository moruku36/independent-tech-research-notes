**English** | [日本語](2026-openai-adversarial-distillation-defenses.ja.md)

# OpenAI’s adversarial distillation defenses and evaluation

## Overview

- **What it is** An OpenAI safety report on defending against unauthorized model distillation.
- **What it says** OpenAI combines protections for individual interactions with investigations of coordinated abuse.
- **Caveat** The published extraction rates compare different model-and-safeguard combinations.

## Practical reading (six lines)

- Unauthorized distillation can transfer capabilities to models operated with weaker safeguards.
- The request-level controls include model training, input and output classifiers, and API access boundaries.
- The output checks cover tool-call arguments as well as messages.
- Investigations look for coordinated activity and inform updates to safeguards.
- In the internal adaptive black-box tests, extraction of earlier reasoning fell from 54.0% to 0.2%, and current reasoning from 22.9% to 0.9%.
- Treat extraction resistance, abuse prevalence, and legitimate-user impact as separate outcomes.

## Source and reading scope

OpenAI, *Combatting adversarial distillation*, November 20, 2026. On November 21 JST, checked the public report’s request and campaign defenses, comparative extraction table, and limits. No production logs or independent evaluation were checked.

## Evidence and limitations

- **Evaluation scope.** The table aggregates internal adaptive black-box tests across six attacker models. It compares GPT-6 Astra with original safeguards to GPT-6.2 Astra with updated safeguards. The table does not isolate one defense or establish the production abuse rate.
- **Enforcement scope.** The article reports weekly enforcement on thousands to tens of thousands of accounts. Account actions measure enforcement volume. The report gives no denominator for estimating prevalence or detection recall from those counts.

## Application and free check

Proposed and untried. Use a mock service with synthetic markers to check that intended explanations remain available while restricted fields stay out of user responses and mock tool arguments. Record false blocks and missed protections separately.

## Related note

- [OpenAI’s frontier AI risk controls](../agent-safety/2026-openai-frontier-risk-model-lifecycle.md)

## Sources

- [OpenAI’s public safety report](https://openai.com/index/combatting-adversarial-distillation/)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
