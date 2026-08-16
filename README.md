# 🤖 Agentic RAG Document Intelligence Assistant

> An intelligent document Q&A system that combines **Agentic RAG, semantic retrieval, LangGraph orchestration, conversational memory, and persistent chat sessions** to provide context-aware answers from user-uploaded documents.

<p align="center">

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![LangGraph](https://img.shields.io/badge/LangGraph-Agentic_Workflow-orange)
![LangChain](https://img.shields.io/badge/LangChain-Framework-green)
![FAISS](https://img.shields.io/badge/FAISS-Vector_Search-red)
![Streamlit](https://img.shields.io/badge/Streamlit-UI-FF4B4B?logo=streamlit)
![LangSmith](https://img.shields.io/badge/LangSmith-Observability-purple)

</p>

---

## 📌 Overview

**Agentic RAG Document Intelligence Assistant** is an AI-powered document question-answering system designed to retrieve relevant information from uploaded documents and generate context-aware responses using an LLM.

The system combines:

- 📄 Document processing
- 🔍 Semantic search
- 🧠 Retrieval-Augmented Generation (RAG)
- 🤖 LangGraph-based agentic workflows
- 💬 Conversational memory
- 💾 Persistent chat sessions
- ⚡ Streaming responses
- 📊 LangSmith observability

Instead of relying only on the LLM's pretrained knowledge, the system retrieves relevant information from the user's documents and uses that context to generate grounded responses.

---

# ✨ Key Features

| Feature | Description |
|---|---|
| 📄 Document Q&A | Ask questions about uploaded documents |
| 🔍 Semantic Retrieval | Retrieves relevant document chunks using embeddings |
| 🧠 Agentic RAG | Uses LangGraph to orchestrate the reasoning/retrieval workflow |
| 💬 Conversational Memory | Maintains context across multiple questions |
| 💾 Persistent Sessions | Stores conversations for later continuation |
| ⚡ Streaming | Displays responses progressively |
| 🗂️ Vector Search | FAISS-based similarity search |
| 🖥️ Interactive UI | Streamlit-based chat interface |
| 📊 Observability | LangSmith tracing and monitoring |

---

# 🏗️ System Architecture

![Architecture](docs/architecture.png)

### High-Level Flow

```text
                 ┌──────────────────┐
                 │       USER       │
                 │ Upload + Query   │
                 └────────┬─────────┘
                          │
                          ▼
                ┌───────────────────┐
                │   Streamlit UI    │
                └─────────┬─────────┘
                          │
             ┌────────────┴────────────┐
             │                         │
             ▼                         ▼
      Document Upload             User Query
             │                         │
             ▼                         ▼
      Document Loader            Query Processing
             │                         │
             ▼                         │
       Text Chunking                   │
             │                         │
             ▼                         │
       Embeddings                      │
             │                         │
             ▼                         │
        FAISS Store ◄─────────────────┘
             │
             ▼
        Semantic Retrieval
             │
             ▼
       Relevant Context
             │
             ▼
      ┌───────────────┐
      │   LangGraph   │
      │    Workflow   │
      └───────┬───────┘
              │
              ▼
             LLM
              │
              ▼
       Context-Aware Answer
              │
              ▼
             USER


     ┌──────────────────────────┐
     │ Conversational Memory    │
     │ SQLite Persistence       │
     └──────────────────────────┘

     ┌──────────────────────────┐
     │      LangSmith           │
     │ Tracing & Observability  │
     └──────────────────────────┘
