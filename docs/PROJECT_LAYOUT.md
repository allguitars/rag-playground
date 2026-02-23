# Project Layout

本文件定義 `rag-playground` 專案的標準目錄結構與使用原則。  
本 repo 用於 RAG、LangChain、LangGraph 相關的學習、實驗與架構探索。

---

## Directory Structure

```shell
rag-playground/
├── langchain/          # LangChain-based RAG examples
├── langgraph/          # LangGraph / state-machine examples
├── observability/      # LangSmith / tracing / evaluation examples
├── examples/           # UI or usage demos (e.g. Gradio)
│
├── data/
│ ├── raw/              # Original source documents fed into RAG (never modified)
│ ├── processed/        # Intermediate artifacts (chunks, metadata, etc.)
│ └── chroma/           # Local vector store persistence
│
├── prompts/            # Prompt templates
├── shared/             # Shared utilities (loaders, splitters, vectorstores)
├── docs/               # Project documentation & notes
│
├── .env
├── .gitignore
└── README.md
```

## Structure Principles

- All source documents fed into RAG must be placed under `data/raw/`.
- Code must never directly modify files under `data/raw/`.
- Artifacts under `data/processed/` must be reproducible.
- Vector stores under `data/chroma/` can be safely deleted and rebuilt.
- Notebooks are for experimentation; stable logic should eventually be migrated to `.py`.
- Shared logic should live under `shared/` to avoid duplication across examples.

## Notes

This structure favors clarity, traceability, and long-term maintainability over short-term convenience.
