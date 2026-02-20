# rag_cookbooks

> A notebook-first **RAG lab** for experimenting with retrieval, vector databases, and multimodal workflows.

If you landed here and thought “what is this actually?”, this is the short answer:
- This is **not** a packaged app or library.
- This **is** a curated set of notebooks for learning and demoing Retrieval-Augmented Generation (RAG).
- You can start fast with [`workshop_series/basic_rag.ipynb`](workshop_series/basic_rag.ipynb), then level up from there.

---

## TL;DR Start Here

1. Start vector infrastructure (Milvus stack):
   ```bash
   docker compose up -d
   ```
   Uses [`docker-compose.yml`](docker-compose.yml).

2. Open Jupyter and run this path:
   - 1️⃣ [`workshop_series/basic_rag.ipynb`](workshop_series/basic_rag.ipynb)
   - 2️⃣ [`workshop_series/improving_rag.ipynb`](workshop_series/improving_rag.ipynb)
   - 3️⃣ [`workshop_series/multimodal_rag.ipynb`](workshop_series/multimodal_rag.ipynb)

3. Browse all notebook options in [`docs/NOTEBOOK_INDEX.md`](docs/NOTEBOOK_INDEX.md).

---

## What this repo contains

### Learning tracks
- **Workshop track**: [`workshop_series/`](workshop_series/) (beginner → improved → multimodal)
- **LangChain track**: [`langchain/`](langchain/) (including multilingual variants)
- **LlamaIndex track**: [`llamaindex/`](llamaindex/)

### Data
- Base city corpus: [`city_data/`](city_data/)
- Language-specific corpora:
  - Chinese: [`langchain/chinese_examples/chinese_city_data/`](langchain/chinese_examples/chinese_city_data/)
  - French: [`langchain/french_examples/french_city_data/`](langchain/french_examples/french_city_data/)
  - Polish: [`langchain/polish_examples/polish_city_data/`](langchain/polish_examples/polish_city_data/)

### Infrastructure (local vector DB)
- Compose stack: [`docker-compose.yml`](docker-compose.yml)
- Embedded single-container startup script: [`standalone_embed.sh`](standalone_embed.sh)
- Embedded etcd config: [`embedEtcd.yaml`](embedEtcd.yaml)

---

## Concept map: what you are practicing

RAG in this repo follows a recurring pattern:

1. **Load documents** (city data files, wiki-scraped text, or mixed media).
2. **Chunk/split text**.
3. **Create embeddings** with a model.
4. **Store vectors** in Milvus/FAISS.
5. **Retrieve top-k context** for a question.
6. **Generate answer** with an LLM constrained by retrieved context.
7. Optionally **evaluate/improve** retrieval quality and prompt strategy.

If you're new to these concepts:
- RAG overview: <https://www.promptingguide.ai/research/rag>
- Milvus docs: <https://milvus.io/docs>
- LangChain docs: <https://python.langchain.com/docs/introduction/>
- LlamaIndex docs: <https://docs.llamaindex.ai/>

---

## Setup details

### Prerequisites
- Python environment with Jupyter
- Docker Engine or Docker Desktop
- Provider API keys (varies by notebook; check first code cells)

### Milvus startup options

#### Option A (recommended): Docker Compose
```bash
docker compose up -d
```
This launches etcd + minio + milvus (see [`docker-compose.yml`](docker-compose.yml)).

#### Option B: Embedded standalone script
```bash
bash standalone_embed.sh start
```
Useful if you want the one-container embedded mode (see [`standalone_embed.sh`](standalone_embed.sh)).

Stop/cleanup examples:
```bash
docker compose down
bash standalone_embed.sh stop
bash standalone_embed.sh delete
```

---

## Repo navigation guide

- Need a complete notebook menu? → [`docs/NOTEBOOK_INDEX.md`](docs/NOTEBOOK_INDEX.md)
- Need beginner flow? → [`workshop_series/basic_rag.ipynb`](workshop_series/basic_rag.ipynb)
- Need multilingual examples? → [`langchain/chinese_examples/`](langchain/chinese_examples/), [`langchain/french_examples/`](langchain/french_examples/), [`langchain/polish_examples/`](langchain/polish_examples/)
- Need vector infra details? → [`docker-compose.yml`](docker-compose.yml)

---

## ⚡ GlitchHealer (10% mode)

When things wobble, here’s the fast triage pass:

1. **Milvus not reachable?**
   - run `docker compose ps`
   - verify `19530` and `9091` are exposed in [`docker-compose.yml`](docker-compose.yml)
2. **Notebook can’t call model API?**
   - check env vars/API keys in the notebook's first setup cells
3. **Retrieval quality feels bad?**
   - inspect chunk size/overlap + embedding model choice
4. **Notebook output looks weird/stale?**
   - clear outputs and re-run clean from top

Think of this repo as a **workbench**: experiments first, polish second.

---

## License

See [`LICENSE`](LICENSE).
