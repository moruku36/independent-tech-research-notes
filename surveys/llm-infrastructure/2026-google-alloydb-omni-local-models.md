**English** | [日本語](2026-google-alloydb-omni-local-models.ja.md)

# AlloyDB Omni: calling locally hosted models from SQL

## Overview

- Google Cloud shows how AlloyDB Omni can call a locally hosted language model from SQL.
- In its GKE example, Ollama serves Gemma 4 or Qwen3.8. AlloyDB Omni registers the model endpoint and exposes generation through `ai.generate`.
- The article illustrates a data path and includes a toy summarization example. Operational performance and deployment controls are left to the environment owner.

## Six practical takeaways

- AlloyDB Omni is a downloadable, self-managed edition of the PostgreSQL-compatible AlloyDB database.
- A database query can send a prompt constructed from row data to a model server hosted within the same environment.
- The GKE walkthrough enables the AI extension, runs Ollama as a separate service, and registers Gemma 4 with Qwen3.8 as an alternative.
- The example uses `ai.generate` to summarize short customer feedback rows and a transform to extract text from the model response.
- Google also describes ScaNN-backed vector search. The shown example is SQL-driven text generation.
- For a local deployment, check where model invocation and logs go, which roles can invoke the model, and the latency and resource cost per query.

## Publication and review scope

Rob Yavitch, Google Cloud Blog, November 23, 2026. Reviewed the article and AlloyDB Omni documentation on November 25, 2026 JST. This note is based on public materials.

## Evidence and limitations

- The walkthrough uses GKE, the AlloyDB Omni Kubernetes operator, the Google ML extension, and a separate Ollama service. The database sends prompts to the registered endpoint. Its sample feedback query shows the intended output and no comparative throughput or accuracy measurements.
- A local database and a local model server make it possible to keep the query payload and response inside a chosen environment. Network restrictions, artifact delivery and telemetry are deployment decisions. The GKE example does not establish that all of its dependencies are available offline.
- The database provides the SQL interface and vector capabilities. The serving stack still needs capacity and lifecycle management for model weights, requests, and timeouts.

## Application and low-cost check

With synthetic feedback in an isolated environment, verify network destinations and access privileges, then measure latency and model-server resource use at multiple batch sizes. Check timeouts and empty responses alongside summary quality.

## Related notes

- [Local Qwen3.8 inference with Unsloth](2026-unsloth-qwen38-local-inference.md)
- [Google Cloud sovereign AI in Europe](../security-governance/2026-google-cloud-sovereign-ai-europe.md)

## Sources

- [Google Cloud integration walkthrough](https://cloud.google.com/blog/products/databases/alloydb-omni-integration-with-local-models)
- [AlloyDB Omni documentation](https://docs.cloud.google.com/alloydb/omni/containers/current/docs/overview)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
