# autorag-m365
Self-optimizing RAG pipelines for Microsoft 365

=======================================
1. REPO: autorag-m365
=======================================
README.md
AutoRAG-M365

Self-optimizing retrieval-augmented generation engineered for Microsoft 365 and SharePoint environments.

1. Problem

Organizations depend on SharePoint and M365 as their knowledge backbone, yet traditional RAG systems suffer from:

• High hallucination rates
• Retrieval failures due to poor chunking or irrelevant matches
• Performance degradation as content grows
• Expensive LLM calls with redundant queries
• No built-in feedback loops or self-tuning behavior

Without constant manual tuning, accuracy drops, latency increases, and costs rise.

2. Solution

AutoRAG-M365 is a fully autonomous retrieval system that continuously learns and adjusts itself based on real-world usage patterns.

It includes:

• Adaptive chunking & dynamic reranking
• Auto-routing between multiple retrievers
• Drift detection & continuous evaluation
• Built-in semantic caching using similarity thresholds
• Native integration with SharePoint & M365 permissions
• End-to-end metrics (precision, recall, hallucination rate, latency)

This turns RAG from a static pipeline into a self-improving enterprise system.

3. Architecture

Core components:

Document Ingestion Pipeline

SharePoint/M365 connector

Chunker with adaptive sizing

Embedding generation & indexing

Retrieval Engine

Hybrid search (vector + keyword)

Multi-retriever scoring

Reranker (Cross-Encoder)

Semantic cache

LLM Orchestration Layer

Context assembly

Guardrails

Response synthesizer

Evaluation Loop

Automatic precision/recall checks

Hallucination scoring using judge model

Drift detection

Monitoring

Latency, token usage, cost per query

Retrieval quality metrics

4. Features

• Auto-tuning retrieval based on past queries
• Semantic cache reducing redundant LLM calls
• Works with Azure OpenAI or OSS models
• Teams-ready API layer
• Enterprise-grade logging and metrics
• Entra ID-authenticated demo interface

5. Repository Structure
autorag-m365/
│
├── app/
│   ├── api/
│   ├── retrievers/
│   ├── chunking/
│   ├── embeddings/
│   ├── reranker/
│   ├── cache/
│   └── evaluation/
│
├── infra/
│   ├── Dockerfile
│   ├── docker-compose.yaml
│   ├── azure-appservice.json
│   └── github-actions.yml
│
├── docs/
│   ├── architecture.png
│   ├── pipeline-sequence.md
│   ├── metrics.png
│   └── notes.md
│
└── README.md

6. Deployment
docker build -t autorag-m365 .
docker run -p 8000:8000 autorag-m365


Azure deployment instructions in:
infra/azure-appservice.json

7. Screenshots
docs/screenshots/query-demo.png
docs/screenshots/metrics-dashboard.png
docs/screenshots/cache-hitrate.png
