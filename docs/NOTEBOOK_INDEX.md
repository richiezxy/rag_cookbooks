# Notebook Index

A practical map of every notebook in this repository, grouped by learning goal.

## Recommended path (first-time users)
1. [`workshop_series/basic_rag.ipynb`](../workshop_series/basic_rag.ipynb)
2. [`workshop_series/improving_rag.ipynb`](../workshop_series/improving_rag.ipynb)
3. [`workshop_series/multimodal_rag.ipynb`](../workshop_series/multimodal_rag.ipynb)

---

## Workshop series

| Notebook | Focus | Tags |
|---|---|---|
| [`workshop_series/basic_rag.ipynb`](../workshop_series/basic_rag.ipynb) | Intro RAG setup and flow | `beginner`, `rag` |
| [`workshop_series/improving_rag.ipynb`](../workshop_series/improving_rag.ipynb) | Retrieval/prompt quality improvements | `intermediate`, `evaluation` |
| [`workshop_series/multimodal_rag.ipynb`](../workshop_series/multimodal_rag.ipynb) | Image + text retrieval workflows | `multimodal`, `vision` |

---

## LangChain notebooks

| Notebook | Focus | Tags |
|---|---|---|
| [`langchain/starwars_faiss.ipynb`](../langchain/starwars_faiss.ipynb) | FAISS-based RAG example | `langchain`, `faiss` |
| [`langchain/may_the_fourth_be_w_you.ipynb`](../langchain/may_the_fourth_be_w_you.ipynb) | Themed LangChain demo | `langchain`, `demo` |
| [`langchain/mixtral_milvus_octoai.ipynb`](../langchain/mixtral_milvus_octoai.ipynb) | Milvus + hosted model integration | `langchain`, `milvus` |

### Multilingual LangChain variants

| Notebook | Focus | Tags |
|---|---|---|
| [`langchain/chinese_examples/chinese_rag.ipynb`](../langchain/chinese_examples/chinese_rag.ipynb) | Chinese corpus RAG | `langchain`, `multilingual`, `zh` |
| [`langchain/chinese_examples/support_chinese_wiki_scrape.ipynb`](../langchain/chinese_examples/support_chinese_wiki_scrape.ipynb) | Chinese data preparation | `langchain`, `data-prep`, `zh` |
| [`langchain/french_examples/french_rag.ipynb`](../langchain/french_examples/french_rag.ipynb) | French corpus RAG | `langchain`, `multilingual`, `fr` |
| [`langchain/french_examples/support_french_wiki_scrape.ipynb`](../langchain/french_examples/support_french_wiki_scrape.ipynb) | French data preparation | `langchain`, `data-prep`, `fr` |
| [`langchain/polish_examples/polish_rag.ipynb`](../langchain/polish_examples/polish_rag.ipynb) | Polish corpus RAG | `langchain`, `multilingual`, `pl` |
| [`langchain/polish_examples/support_polish_wiki_scrape.ipynb`](../langchain/polish_examples/support_polish_wiki_scrape.ipynb) | Polish data preparation | `langchain`, `data-prep`, `pl` |

---

## LlamaIndex notebooks

| Notebook | Focus | Tags |
|---|---|---|
| [`llamaindex/solar_milvus_mpnet.ipynb`](../llamaindex/solar_milvus_mpnet.ipynb) | LlamaIndex + Milvus example | `llamaindex`, `milvus` |

---

## Infra references used by notebooks

- Milvus stack: [`docker-compose.yml`](../docker-compose.yml)
- Alternate startup: [`standalone_embed.sh`](../standalone_embed.sh)
- Embedded etcd config: [`embedEtcd.yaml`](../embedEtcd.yaml)

Back to project overview: [`README.md`](../README.md)
