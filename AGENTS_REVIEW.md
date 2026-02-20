# Repo Reality Check + AGENTS Guidance Refresh

## 1) What this repository actually is (clear picture)
This repo is a **RAG cookbook / workshop sandbox**, not a traditional Python package.

Evidence from the tree:
- Notebook-first structure across `langchain/`, `llamaindex/`, and `workshop_series/`.
- Multiple language variants of the same city-corpus RAG workflow (English/French/Chinese/Polish).
- Local Milvus infrastructure files (`docker-compose.yml`, `standalone_embed.sh`, `embedEtcd.yaml`) for vector DB experiments.
- Tiny root README (`# rag_cookbooks`) with no setup or run guidance.

In practice, this is a **demo/training repo for retrieval workflows**: baseline RAG, multilingual RAG, and multimodal RAG experiments.

## 2) Is the previous AGENTS review useful and up to date?
### Useful parts
Yes—the previous review correctly flagged process risks:
- stale manual skill inventories,
- ambiguous trigger wording,
- missing version/validation metadata,
- unclear precedence.

### What was missing (and why the result felt weak)
It was too generic and did not anchor recommendations to this repo’s real shape:
- no acknowledgement that this repo is mostly notebooks,
- no mention of Milvus dependency and Docker-first flow,
- no practical updates to make onboarding usable for workshop users.

## 3) Targeted revisions (repo-specific)

### A) Replace the root README with an actionable one-page guide
Add:
1. **What this repo is** (RAG cookbook/workshop).
2. **Quick start paths**:
   - Milvus via `docker-compose up -d`
   - optional single-container flow via `bash standalone_embed.sh start`
3. **Notebook map** by intent:
   - beginner (`workshop_series/basic_rag.ipynb`)
   - quality tuning (`workshop_series/improving_rag.ipynb`)
   - multimodal (`workshop_series/multimodal_rag.ipynb`)
   - framework demos (`langchain/*`, `llamaindex/*`)
4. **Environment variables** needed by cloud-model notebooks.
5. **Known caveats** (notebooks may contain executed outputs / transient states).

### B) Add a repo-level AGENTS.md tailored to notebook repos
Include explicit rules for:
- minimal, deterministic notebook diffs (clear outputs unless needed),
- where to put generated data/artifacts,
- required validation command before commit (e.g., notebook JSON sanity + git diff check),
- when to avoid touching large data files.

### C) Normalize naming + entry points
Current structure is useful but discovery is hard. Add a short `docs/NOTEBOOK_INDEX.md` with tags:
- `beginner`, `multilingual`, `multimodal`, `milvus`, `faiss`, `llamaindex`, `langchain`.

### D) Pin infra versions intentionally
`docker-compose.yml` pins Milvus/MinIO/etcd images; keep that, but add a note in README stating the tested version set.

## 4) Three revision options (with creative flair)

### Option 1 — **“Airport Terminal”** (best for workshops)
Design docs like signage in an airport:
- **Start Here** (quick start)
- **Choose Your Route** (notebook tracks)
- **Before Takeoff** (env vars)
- **Delays & Disruptions** (common errors)

Why it works: fast orientation for newcomers under time pressure.

### Option 2 — **“Chef’s Tasting Menu”** (best for cookbook branding)
Frame repository flow as courses:
- **Amuse-bouche**: `basic_rag.ipynb`
- **Main course**: `improving_rag.ipynb`
- **Chef’s special**: `multimodal_rag.ipynb`
- **Regional flights**: multilingual city-data demos

Why it works: memorable progression and consistent with “cookbook” identity.

### Option 3 — **“Lab Protocol”** (best for reproducibility)
Use scientific protocol style:
- **Materials** (Docker + API keys)
- **Procedure** (exact run steps)
- **Expected observations** (sample outputs)
- **Troubleshooting controls** (if X fails, do Y)

Why it works: strongest for repeatable internal training and CI-friendly checks.

## 5) Recommended option
Pick **Option 1 (Airport Terminal)** for immediate usability.
Then borrow Option 3’s troubleshooting table for reliability.
