# rag_cookbooks

Build your own smart AI that can read documents and answer questions.

This repository is a **beginner-friendly, notebook-based course + lab** for Retrieval-Augmented Generation (RAG):

**AI + Search + Your Data = Smarter Answers**

---

## Course Goal

By the end of this course path, you will build a simple AI assistant that can:
- read documents,
- search for relevant information,
- answer questions using that information.

No prior AI experience required.

---

## TL;DR (Fast Start)

1. Start the vector database stack:
   ```bash
   docker compose up -d
   ```
   (uses [`docker-compose.yml`](docker-compose.yml))

2. Open Jupyter and run these notebooks in order:
   1. [`workshop_series/basic_rag.ipynb`](workshop_series/basic_rag.ipynb)
   2. [`workshop_series/improving_rag.ipynb`](workshop_series/improving_rag.ipynb)
   3. [`workshop_series/multimodal_rag.ipynb`](workshop_series/multimodal_rag.ipynb)

3. Explore all notebook options in [`docs/NOTEBOOK_INDEX.md`](docs/NOTEBOOK_INDEX.md).

---

## Course Structure

## Unit 1 — What is AI and How Does It Answer Questions?

### Lesson 1.1 — What is AI?
**Learn:**
- What AI is
- Familiar examples: ChatGPT, Siri, Alexa

**Activity:**
- Ask an AI assistant a few questions.
- Observe how responses are generated.

### Lesson 1.2 — Why AI Sometimes Gets Things Wrong
**Learn:**
- AI predicts from patterns.
- AI does not automatically know your private documents.

**Simple example:**
AI cannot know your homework unless you provide your homework.

### Lesson 1.3 — What is RAG (Big Idea)
**Formula:**

**AI + Search + Your Data = Smart Answers**

**Concepts:**
- Your data = a library
- Retriever = search engine
- LLM = answer generator

---

## Unit 2 — Teaching AI Using Documents

### Lesson 2.1 — Loading Documents
**Learn:**
How to provide data such as:
- `.txt` files (see [`city_data/`](city_data/))
- multilingual corpora (see [`langchain/chinese_examples/chinese_city_data/`](langchain/chinese_examples/chinese_city_data/), [`langchain/french_examples/french_city_data/`](langchain/french_examples/french_city_data/), [`langchain/polish_examples/polish_city_data/`](langchain/polish_examples/polish_city_data/))

**Goal:**
AI can access your information source.

### Lesson 2.2 — Splitting Documents into Pieces (Chunking)
**Why:**
Models do not process giant files efficiently in one shot.

So we split documents into chunks.

**Analogy:**
Book → chapters/pages.

### Lesson 2.3 — Turning Words into Numbers (Embeddings)
**Simple explanation:**
Text is converted into vectors (numbers) so similarity can be measured.

This enables semantic search (“meaning match,” not just keyword match).

---

## Unit 3 — Building AI Memory (Vector Database)

### Lesson 3.1 — What is a Vector Database?
Think of it as a smart library index that stores meaning-aware vectors.

In this repo, Milvus is the primary vector store path:
- [`docker-compose.yml`](docker-compose.yml)
- [`standalone_embed.sh`](standalone_embed.sh)
- [`embedEtcd.yaml`](embedEtcd.yaml)

(You may also see FAISS examples, e.g. [`langchain/starwars_faiss.ipynb`](langchain/starwars_faiss.ipynb)).

### Lesson 3.2 — Saving Knowledge
Typical pipeline:
1. Load documents
2. Split into chunks
3. Create embeddings
4. Store vectors

Now your AI can retrieve relevant context before answering.

---

## Unit 4 — Teaching AI to Search

### Lesson 4.1 — Finding the Right Information
When a user asks a question, the retriever finds top-matching chunks.

### Lesson 4.2 — Why Search Makes AI Smarter
- Without retrieval: model may guess ❌
- With retrieval: model can ground answers in provided data ✅

---

## Unit 5 — Making the AI Answer Questions

### Lesson 5.1 — Combining Search + AI Brain
Process:

User asks question
↓
Retriever finds relevant context
↓
LLM reads context
↓
LLM answers with evidence

### Lesson 5.2 — Build Your First QA Bot
Use a notebook to build a bot that answers questions from:
- class notes,
- short stories,
- local text docs.

Best starting point: [`workshop_series/basic_rag.ipynb`](workshop_series/basic_rag.ipynb)

---

## Unit 6 — Improving the AI

### Lesson 6.1 — Make Answers More Accurate
Common levers:
- better chunk sizing,
- better retrieval settings,
- clearer prompts.

Practice notebook: [`workshop_series/improving_rag.ipynb`](workshop_series/improving_rag.ipynb)

### Lesson 6.2 — Reducing Mistakes
Constrain outputs to retrieved/source context where possible.

---

## Unit 7 — Advanced Features (Optional)

### Lesson 7.1 — Chat with PDFs
Pattern extension: parse PDFs, chunk, embed, retrieve, answer.

### Lesson 7.2 — Chat with Multiple Documents
Search over multiple sources/corpora in one retrieval layer.

### Lesson 7.3 — Add Memory
Add conversational memory/state for multi-turn assistants.

---

## Final Project

Build your own study assistant that can:
- read documents,
- answer questions,
- help with homework/study prep.

Project ideas:
- Homework helper
- Book question bot
- Study guide bot

---

## Where each concept lives in this repo

- Beginner flow: [`workshop_series/`](workshop_series/)
- LangChain examples: [`langchain/`](langchain/)
- LlamaIndex example: [`llamaindex/solar_milvus_mpnet.ipynb`](llamaindex/solar_milvus_mpnet.ipynb)
- Full notebook map: [`docs/NOTEBOOK_INDEX.md`](docs/NOTEBOOK_INDEX.md)

---

## Tools used in this repo

- Python + Jupyter notebooks
- LLM APIs (varies by notebook)
- Vector stores:
  - Milvus (primary local infra path)
  - FAISS (example notebook path)

---

## Simple Visual Summary

Documents 📄

↓

Split into chunks ✂️

↓

Convert to vectors 🔢

↓

Store in vector DB 📚

↓

User asks question ❓

↓

Retrieve context 🔍

↓

AI answers 🤖

---

## ⚡ GlitchHealer (quick troubleshooting)

1. Milvus not reachable?
   - run `docker compose ps`
   - verify ports in [`docker-compose.yml`](docker-compose.yml) (especially `19530`, `9091`)
2. Notebook can’t call model API?
   - check env vars/API keys in notebook setup cells
3. Answers feel weak?
   - tune chunk size, retriever top-k, and prompt constraints
4. Notebook feels stale/inconsistent?
   - restart kernel and re-run top-to-bottom

---

## License

See [`LICENSE`](LICENSE).
