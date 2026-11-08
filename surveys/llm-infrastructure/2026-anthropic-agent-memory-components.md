[日本語](2026-anthropic-agent-memory-components.ja.md) | **English**

# The components of agent memory

- The article distinguishes raw logs, agent-written notes, structured representations such as wikis, and a small context injected into the next session.
- Offline “dreaming” repairs and organizes external memory; it does not update model weights.
- Combining wikis with search helps in some reported evaluations, alongside preparation costs, stale notes, and losses from concurrent overwrites.

## Practical interpretation (7 lines)

- Retain original logs so memory errors can be traced and corrected.
- Treat notes as fallible predictions of what future tasks will need.
- Compare wikis on cross-document reasoning separately from single-file lookup.
- Keep injected context small and retrieve detail when needed.
- Account separately for memory creation, maintenance, retrieval, and answering.
- Test concurrent overwrites and stale facts alongside answer quality.
- The proposal below is unperformed; product functionality and reported performance were not independently verified.

## Metadata and verification

- Author: Lance Martin, Anthropic.
- Published: November 6, 2026. Corporate engineering/research article, not a peer-reviewed paper.
- Checked: November 8, 2026 JST.
- Scope: primary article text, figures, experimental conditions, and examples reviewed; no code execution or reproduction.
- Definition: experience retained between sessions as external context. Weight updates, within-conversation learning, and compaction are outside the article's scope.

## Question and architecture

What should an agent save, how should it organize it, and what should it read next time? The article separates original transcripts, agent-authored notes, structured linked representations, and a small injected context. These layers serve different purposes rather than replacing everything with one summary.

Dreaming uses offline or idle computation to compare notes with logs, correct errors, merge and prune material, construct wikis, and promote a compact index into injected context. External files change. This does not demonstrate a biological sleep mechanism or training of model weights.

## Reported evidence

### Database tasks and notes

On the CL-Bench 1.0 database task, each question starts a fresh session with only a persistent memory directory carried over. Correct solutions are supplied after answers. Opus 5 improves from 0.564 without memory to 0.828 with memory; Opus 5.5 improves from 0.655 to 0.838, and Sonnet 5.5 from 0.644 to 0.833.

Sonnet 4.6 improves from 0.330 to 0.364, or 0.641 when instructed to read notes and test theories. Supplying memory alone does not ensure that a model uses it effectively. Recording only failures reduces the gains. These findings concern this task and feedback setup, not all of CL-Bench.

### Repairing notes from logs

Pokémon Red examples illustrate correcting a mistaken location note by consulting original transcripts. A roughly 10,000-step comparison uses one run each of Sonnet 3.7 and Fable 5: the former produces 413 files in 225 folders and earns one badge; the latter uses 10 total files in two folders plus global memory and earns four badges. Model capability changes too, so this is not evidence that fewer files cause better performance.

### Wikis and search

On private internal Stainless documentation, approximately 350,000 files and 420 million tokens, a 25-question evaluation increases wiki-only criteria fulfillment from 13% to 48% when dreaming grows from two to 128 sessions. Wiki plus search rises from 54% to 61%, compared with 53% for search alone. Criteria fulfillment is not equivalent to the percentage of questions answered correctly.

The reported saving of about 20,000 tokens per question concerns answering. Wiki preparation and maintenance are separate, and dreaming computation increases; a reduction in total cost is not established. The private corpus limits external reproduction.

Harvey legal examples show improvements on some cross-document reasoning criteria, but no clear gain on some single-document lookups. In one merger-agreement example, a 68-page, 203 KB wiki is larger than its ten source documents totaling 115 KB. Concurrent writers overwrite terms, leaving 41 of 57 criteria fulfilled, or 72%. Task-specific instructions, including one agent per contract and separate pages preserving exact terms, make it possible to meet all 57 criteria in this example. This repair is not a general completeness guarantee.

## Limitations

The article combines experiments and examples with different models, tasks, and instructions rather than a uniform comprehensive comparison. Repeated runs, confidence intervals, and full cost accounting are not provided consistently. It does not establish that longer or more elaborate memory is always better.

Wrong notes can persist across sessions, and wikis that omit details are incomplete substitutes for original evidence. Update frequency, staleness, unused injected memory, broken links, writer coordination, and maintenance costs remain design problems.

## Related notes

- [Raw-RAG versus agentic memory](2026-raw-rag-agentic-memory.md): motivates original-history retrieval as a strong baseline. Different tasks and models prevent direct numerical comparison.
- [Google Sleep and continual learning](2026-google-sleep-continual-learning.md): studies consolidation into model weights, a different update target from the external files here.

## Free or low-cost verification proposal — not performed

Prepare synthetic logs containing facts that are corrected later. Compare original-log retrieval, notes, and wiki plus search. Start with small manually authored memories and check whether answers trace back to evidence and valid times, avoid superseded facts, and preserve clauses during concurrent edits. Automated model-based organization would be a separate evaluation.

Measure answer quality, omissions and stale facts, evidence traceability, and time/tokens for creation, repair, and answering separately. This is our proposed check, not a reported experiment from the source.

- Use status: proposed only; no implementation or reproduction.
- Open questions: tasks where structure helps, update frequency, and total cost-effectiveness over retrieval alone.

## Primary source

- [Anthropic article](https://www.anthropic.com/research/components-of-agent-memory)
