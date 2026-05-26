# RAG Chatbot with Knowledge Base

A production-style **Retrieval-Augmented Generation (RAG)** chatbot built on a fictional insurance company ("Insurellm") knowledge base of 70+ markdown documents — company info, products, employees, and contracts.

Ships with **two RAG implementations** for comparison and a **full evaluation dashboard**.

## Features

- **Baseline RAG** — LangChain + Chroma + OpenAI embeddings + fixed-size chunking
- **Pro RAG** — LLM-based semantic chunking, query rewriting, dual retrieval, LLM reranking, parallel ingestion
- **Evaluation harness** — MRR, nDCG, keyword coverage (retrieval) + LLM-as-judge accuracy/completeness/relevance (answers)
- **Two Gradio UIs** — chat interface and an evaluation dashboard with category-level metrics

## Quickstart

```bash
# 1. Install
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt

# 2. Configure
cp .env.example .env
# edit .env and add your OPENAI_API_KEY

# 3. Build the vector store (baseline)
python -m implementation.ingest

# 4. Launch the chatbot
python app.py
