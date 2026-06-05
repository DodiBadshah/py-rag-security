# py-rag-security

[![Python](https://img.shields.io/badge/python-3.11%2B-blue)](https://www.python.org/)
[![Status](https://img.shields.io/badge/status-in%20development-orange)]()
[![Phase](https://img.shields.io/badge/phase-2%20of%203-blueviolet)]()

> **Status: In Development**
> This repository is actively being built.
> Follow along or check back soon.

Phase 2 of a three-phase LLM security portfolio.
Extends [py-prompt-injection](https://github.com/DodiBadshah/py-prompt-injection)
with a RAG pipeline to test LLM vulnerabilities that require document context.

## What this will do

Fire structured attack payloads through a ChromaDB retrieval pipeline at any
OpenAI or Anthropic model, score responses using both heuristics and an
LLM-as-judge, and generate HTML and PDF security reports.

## OWASP LLM Top 10 coverage

| ID | Category | Requires |
|---|---|---|
| LLM03 | Training Data Poisoning | Poisoned documents injected into vector store |
| LLM09 | Misinformation | Grounded RAG context manipulated to produce false output |

## Three-phase portfolio

| Phase | Repository | OWASP Coverage | Status |
|---|---|---|---|
| Phase 1 | [py-prompt-injection](https://github.com/DodiBadshah/py-prompt-injection) | LLM01, LLM02, LLM06, LLM08 | Complete |
| Phase 2 | [py-rag-security](https://github.com/DodiBadshah/py-rag-security) | LLM03, LLM09 | In Development |
| Phase 3 | py-llm-load | LLM04, LLM10 | Planned |

## What is being reused from Phase 1

- `adapters/` - OpenAI and Anthropic adapters unchanged
- `scoring/heuristics.py` - extended, not replaced
- `reporting/` - existing HTML and PDF pipeline reused
- MLflow experiment tracking spans both phases

## What is new in Phase 2

- `store/` - ChromaDB vector store, OpenAI embeddings, retriever
- `poisoner/` - document builder and injector for attack context
- `scoring/judge.py` - LLM-as-judge scorer

## License

MIT
