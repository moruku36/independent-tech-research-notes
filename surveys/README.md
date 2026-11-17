# Survey notes

**English** | [日本語](README.ja.md)

Reading notes on research papers, technical articles, and presentations. Choose a theme below to find the individual notes.

[New additions](../docs/reading-history.md) · [Full reading and application list](../docs/reading-list.md) · [Repository overview](../README.md)

## Themes

### AI agents and software development

| Theme | What you will find |
| --- | --- |
| [Coding agents and software engineering](coding-agents/README.md) | Code generation, review, repair, and verification |
| [Human-AI collaboration](human-ai-collaboration/README.md) | AI at work, learning, attention, and shared goals |
| [AI agent safety](agent-safety/README.md) | Authorization, attacks, misalignment, and reward hacking |
| [Deception and LLM defense](deception-defense/README.md) | Decoys and deceptive information for defense |

### Infrastructure, operations, and security

| Theme | What you will find |
| --- | --- |
| [LLM infrastructure](llm-infrastructure/README.md) | Serving, memory, caching, cost, and orchestration |
| [Cloud resilience and SRE](cloud-resilience/README.md) | Fault injection, recovery, cloud, and DevOps |
| [Security governance](security-governance/README.md) | Privacy, credentials, organizational controls, and cloud security |

### Models, industry, and economics

| Theme | What you will find |
| --- | --- |
| [Generative models and 3D environments](generative-modeling/README.md) | Generation, editing, datasets, and evaluation |
| [Forecasting and benchmarks](forecasting/README.md) | Time-series forecasting, datasets, and uncertainty |
| [Events, articles, and work research](articles/README.md) | Releases, technical reports, events, and workplace research |

Related collection: [economics and corporate disclosures](../economics/README.md), kept outside `surveys/`.

## Principles for research notes

- Do not write "reproduced" when no experiment was run.
- Do not confuse a paper's simulation results with attacks that succeed in real operation.
- Always keep the primary URL and verification status of cited works.
- Every note has a Japanese counterpart (`*.ja.md`).
- Every note opens with a three-line **Overview** (what it is / what it says / caveat), placed right after the title.

Academic papers/preprints, research articles, practitioner reports, and corporate materials retain their source-type labels. The theme indexes and reading list hold the individual entries.

## Where files live

| Path | Contents |
| --- | --- |
| `surveys/<theme>/<year>-<slug>.md` | English note |
| `surveys/<theme>/<year>-<slug>.ja.md` | Japanese counterpart |
| `surveys/<theme>/README.md` / `README.ja.md` | Notes in that theme |
| [docs/](../docs/reading-list.md) | Cross-theme reading lists, research plans, and checklists |

Use the [note template](template.md) for the source URL, verification status, summary, limitations, and practical ideas.

[Repository README](../README.md) · [Reading history](../docs/reading-history.md) · [Reading list](../docs/reading-list.md)
