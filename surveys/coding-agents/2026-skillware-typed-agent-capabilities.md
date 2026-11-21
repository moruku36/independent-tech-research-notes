**English** | [日本語](2026-skillware-typed-agent-capabilities.ja.md)

# Skillware: typed capability bundles and their benchmark limits

## Overview

- **What it is**: A preprint proposing versioned agent capabilities that bundle an input schema, executable code, instructions, data, and tests.
- **What it says**: The author reports benchmark pass rates of 58.2% for generated scripts, 71.4% for basic tool calls, and 91.8% for the full bundle in the comparison in Section 6.10.
- **Caveat**: The full setup changes several controls at once. The headline cost comparison changes the model and hosting, and its unit differs across the text and figure.

## Practical reading (six lines)

- The model selects a capability and supplies arguments, while ordinary code handles validation and execution.
- The author compares runtime script generation, basic calls to prepared functions, and full bundles with typed validation and review controls.
- In the three-arm comparison, reported pass rates are 58.2%, 71.4%, and 91.8%.
- The 97.3% cost claim compares a frontier cloud model with a local 8B model and uses different billing assumptions.
- The text prices 1,000 turns and Figure 9 labels the same prices per 1,000 tasks. The two units can differ for multistep work.
- Proposed use: compare the three setups on the same model with a small dry-run task and count incorrect arguments, end-to-end passes, and review effort.

## Source and reading scope

*Don't Prompt Your Agents. Equip Them: Skillware as a Modular Standard for Sovereign, Auditable, and Deterministic Capability Execution for Logical Systems*, Vladimiros Peilivanidis. arXiv v1, November 5, 2026. Checked November 22, 2026 JST, focusing on the architecture, cost comparison in Section 5.3 and Figure 9, and the three arms in Section 6.10. The benchmark repository and measurements were not independently reproduced.

## Evidence and limitations

- **Design.** Versioned bundles pair typed inputs with prepared Python code, instructions, data, and automated tests. The model still selects the action and supplies inputs. A typed contract can reject invalid inputs, while correct intent, external state, and repeated end-to-end outcomes remain separate checks.
- **Three-arm comparison.** The author reports 368 benchmark runs and pass rates of 58.2%, 71.4%, and 91.8% for runtime generation, basic function calls, and the full package. The full condition adds schema validation, confirmation, and other controls together. Its reported 0.0% parameter corruption is a scoped metric. Figure 6 separately reports 99.6% initial tool-call validity on its own sample. Neither measure establishes that every model-selected argument is semantically correct.
- **Cost comparison.** The 97.3% headline figure compares USD 15.58 for a cloud frontier setup with USD 0.42 in estimated local energy costs for a model with 8B parameters. The prose uses 1,000 turns and Figure 9 says 1,000 tasks. The comparison changes execution, model, and hosting together, so it does not isolate the bundle’s effect. Hardware, maintenance and review costs were not established by this ratio.

## Application and free check

Proposed. Use fictional inventory data for a dry-run query and change preview. Hold the model, instructions, task set, and scorer constant while comparing generated scripts, prepared functions, and functions with validation and a confirmation step. Record invalid arguments, task correctness, premature state changes in the mock system, token use, and review time. Keep results per task and per turn separately.

## Related note

- [Claude Code’s verification practices](2026-claude-code-verification-practices.md) covers independently checkable results in a different engineering setting.

## Sources

- [arXiv record](https://arxiv.org/abs/2611.07652)
- [Inspected v1 text](https://arxiv.org/html/2611.07652v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
