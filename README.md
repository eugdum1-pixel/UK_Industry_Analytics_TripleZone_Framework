# 🚀 Local AI Architecture — MCP vs RAG
Architecting intelligence from raw data units for private, local-first semantic search

---

**Project Status:** Production-Ready  
**Data Integrity:** 99.90%  
**Architecture:** Retrieval-Augmented Generation (RAG) enabled

## Overview
This repository documents an end-to-end engineering pipeline that converts high-volume, unstructured industry data into a semantically aware knowledge system. The pipeline validates, enriches, vectorizes, and serves data via a local RAG-enabled query engine. The project is intended as a blueprint for private, reproducible, production-grade local AI.

### 🗺️ The Triple-Zone Framework
Explore the specialized analytical layers:

* 🏛️ **[ZONE A: PUBLIC POLICY & ETHICS](./ZONE_A_POLICY)**
* 💰 **[ZONE B: BUSINESS IMPACT](./ZONE_B_BUSINESS)**
* 🎓 **[ZONE C: WORKFORCE & SKILLS](./ZONE_C_WORKFORCE)**

Key metrics
- Total raw data units processed: **13,952**
- Successfully validated units: **13,938**
- Integrity rate: **99.90%**
- Vector embeddings stored: **13,938**

---

## Architecture at a glance
The system is organized as a five-stage pipeline:

1. Validation — Gatekeeper phase that enforces schema and data integrity.  
2. Semantic enrichment — Adds metadata and taxonomy labels to improve retrieval relevance.  
3. Vectorization — Converts text into neural embeddings for semantic search.  
4. Vector storage — Efficient local storage for sub-second retrieval.  
5. Inference & integration — Connects local LLM engines to generate grounded answers.

---

## Detailed pipeline stages

### Stage 1 — Data validation & schema enforcement
- Purpose: Ensure each data unit conforms to a strict JSON schema, remove duplicates, and fix encoding issues.  
- Result: 13,938 of 13,952 units validated (99.90% integrity).

### Stage 2 — Semantic taxonomy & enrichment
Data units are programmatically categorized into thematic Zones to improve retrieval precision.

| Zone   | Category        | Keywords / Signals                        | Goal                            |
|--------|------------------|-------------------------------------------|---------------------------------|
| Zone A | Public & Policy  | government, NHS, ethics, safety           | Surface regulatory guardrails   |
| Zone B | Business Impact  | investment, market, revenue, startups     | Surface economic signals        |
| Zone C | Future of Work   | skills, automation, jobs, training        | Surface labour & skills trends  |

Enrichment includes adding Zone labels and additional metadata used as filters during retrieval.

### Stage 3 — Neural vectorization
Text units are converted to dense vector embeddings for semantic matching.

Technical specifications:
- Model: `all-MiniLM-L6-v2` (Sentence-Transformers)  
- Dimensionality: 384  
- Total vectors: 13,938  
- Format: compressed NumPy archive (`.npz`)

### Stage 4 — Vector database & retrieval (RAG)
- Retrieval method: Cosine similarity over the 384-dimensional embeddings.  
- Engine: Local vector index optimized for sub-second retrieval.  
- Use case: When queried for policy-related topics (e.g., "Government safety standards for AI"), RAG returns high-relevance documents from Zone A while avoiding code/noise artifacts.

### Stage 5 — Inference & pipeline integration
- Local LLM engines (e.g., Ollama or other local models) are connected to provide grounded answers using retrieved context.  
- The system supports both RAG (vector + retrieval) and MCP (Model Context Protocol — direct model-context) integration patterns.

---

## Example result
- Query: "Government safety standards for AI"  
  Result: RAG retrieved high-relevance policymaking evidence from Zone A with contextual snippets and citations (e.g., international guidance references).

---

## Reproducing the pipeline
Ensure your environment has the required Python dependencies (see the Dependencies section).

1) Data validation
```bash
python validate_chunks.py
```
Ensures the 13,952 units meet the target integrity threshold.

2) Semantic enrichment
```bash
python enrich_metadata.py
```
Applies the Zone A/B/C taxonomy and other metadata to validated JSON units.

3) Neural vectorization
```bash
python create_embeddings.py
```
Generates 384-dimensional embeddings and writes them to `semantic_vectors.npz`.

4) RAG querying / interactive demo
```bash
python query_engine.py
```
Launches an interactive terminal to ask questions and retrieve context-aware answers.

Repository assets
- Core scripts: `validate_chunks.py`, `enrich_metadata.py`, `create_embeddings.py`, `query_engine.py`  
- Data store: `semantic_vectors.npz` (neural memory archive)  
- Reports: `stage_1_validation_report.md`

---

## Dependencies & environment
- Python 3.8+ recommended  
- Example packages: `sentence-transformers`, `numpy`, `faiss` or `annoy`, `orjson` or `ujson`  
- Install example:
```bash
python -m pip install -r requirements.txt
```

## Notes & best practices
- Keep raw data and vectors private — this repo is designed for local-first deployments.  
- Store the vector index and `.npz` archive securely if using sensitive data.  
- Version your schema and validation scripts to maintain reproducibility.  
- Add a short CHANGELOG when making schema or pipeline changes.

---

## Contributing & Feedback

This repository is primarily maintained as a personal portfolio and technical showcase.

Constructive feedback, technical discussions, or suggestions for improvement are welcome.

If you are interested in the architectural decisions, implementation details, or potential extensions of this project, feel free to open an issue or reach out directly.

For professional or collaboration-related inquiries, please use the contact details provided below.

---

## Contact / acknowledgements
- Author: eugdum1-pixel  
- For questions or collaboration requests, open an issue or contact the repository owner.

---

