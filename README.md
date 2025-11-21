# Project Overview

This repository provides a simple, production-ready starter for building Agentic AI workflows using OpenAI models and LangChain. It is designed as a minimal yet practical foundation for developers who want to implement retrieval-augmented agents that combine memory, vector search, and web search.

The project integrates:
- FAISS vector database
- SerpAPI for web search
- LangChain-based agent architecture
- Lightweight conversational memory

Its primary goal is to serve as a clean, easy-to-extend baseline for agentic systems that retrieve information, reason over external data sources, and maintain contextual memory across interactions.

## Purpose

This project demonstrates how to:
1. Incorporate FAISS vector indexing and SerpAPI search tools into a unified LangChain agent.
2. Overcome typical chatbot limitations such as context forgetting and inability to reflect external or updated information.
3. Build an agent that can retain conversation history, query FAISS, and perform web search depending on user intent.

## Development Timeline
- 2024.04.04 — Initial structure and core implementation.

## Architecture
<p align="center">
  <img src="https://private-user-images.githubusercontent.com/74033655/361417236-30ff5e5c-7437-4f11-afd7-fe8bc400334f.png" width="80%">
</p>

## How to Use

### 1. Environment Setup
Install required packages using `requirements.txt` or the setup cells in `/build_rag/build_faiss_db.ipynb`.

### 2. Build the Vector Database
Create a FAISS index from your text data:
- Prepare `/build_rag/sample_faiss_db.txt`.
- Run `/build_rag/build_faiss_db.ipynb` to generate `/build_rag/faiss_index`.

### 3. Configure API Keys
Add your API keys:
- `/utilities/raig_lib/faiss.py` — OpenAI API key
- `/utilities/raig_lib/serp.py` — SerpAPI key

### 4. Configure Prompts & Tools
- Customize FAISS query prompts in `faiss.py`.
- Combine FAISS + SerpAPI tools to construct an agent in `/utilities/rag_lib/`.

### 5. Initialize Memory
`ConversationBufferWindowMemory` is configured in `/utilities/build_memory.py`.

### 6. Run the Agent
```bash
python run.py
```

## Module Description

### /RAG/util/faiss.py
Implements FAISS-based vector search and defines prompt templates for answering user queries.

### /RAG/util/serp.py
Provides a SerpAPI wrapper for Google search queries.

### /RAG/chat_response.py
Defines the main agent workflow.

### /RAG/build_memory.py
Configures conversational memory.

### /run.py
Main entry point for executing the agent.

### /build_faiss_db.ipynb
Notebook that builds a FAISS index from sample text.
