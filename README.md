<div align="center">

# LLM Engineering — 8-Week Core Track

**A structured, project-driven journey through Large Language Model engineering**

*Based on Ed Donner's LLM Engineering Core Track · Udemy*

[![Course](https://img.shields.io/badge/Course-Ed%20Donner%20%7C%20Udemy-blue?style=flat-square)](https://www.udemy.com/course/llm-engineering-master-ai-and-large-language-models/)
[![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Status](https://img.shields.io/badge/Status-In%20Progress-f39c12?style=flat-square)]()
[![LinkedIn](https://img.shields.io/badge/LinkedIn-ashishpanda2028-0077B5?style=flat-square&logo=linkedin)](https://linkedin.com/in/ashishpanda2028)

</div>

---

## About This Repository

This repository documents my complete 8-week journey through the **LLM Engineering Core Track** by Ed Donner. Each week contains hands-on code, a project, and structured notes covering the concepts learned.

**Who I am:** Ashish Panda — B.Tech CSE (Cybersecurity), Semester 4, ITER · SOA University, Bhubaneswar. I am working toward Agentic AI Engineering and AI Security roles, with this course forming the technical foundation of my learning path.

**Why this course:** LLM Engineering bridges theory and production. Each week builds on the last — from raw API calls all the way to multi-agent systems — which directly supports my flagship project, **XAI-IDS** (Explainable AI Intrusion Detection System).

---

## Table of Contents

- [Repository Structure](#repository-structure)
- [8-Week Journey](#8-week-journey)
- [Flagship Project — XAI-IDS](#flagship-project--xai-ids)
- [Tech Stack](#tech-stack)
- [Setup & Installation](#setup--installation)
- [Progress Tracker](#progress-tracker)
- [Career Direction](#career-direction)
- [Connect](#connect)

---

## Repository Structure

```
llm-engineering/
│
├── week1/              # LLM Foundations & First AI App
├── week2/              # Tool Calling & Function Calling
├── week3/              # Building AI Products & Frontends
├── week4/              # Evaluations & Structured Outputs
├── week5/              # RAG — Retrieval Augmented Generation
├── week6/              # Fine-Tuning LLMs
├── week7/              # Open Source Models & Local Inference
├── week8/              # Multi-Agent Systems
│
├── .env.example        # Environment variable template (copy to .env)
├── requirements.txt    # Python dependencies
└── README.md
```

Each week folder contains:
- `notebooks/` — Jupyter notebooks with exercises
- `projects/` — The week's main project
- `notes.md` — Key concepts and personal takeaways

---

## 8-Week Journey

> ⭐ marks the three priority weeks most directly tied to Agentic AI Engineering.

---

### Week 1 — LLM Foundations & First AI App

**What I learned:**
- How LLMs work internally: Transformer architecture, tokenization, embeddings
- Making API calls to OpenAI, Anthropic Claude, and Google Gemini
- Prompt engineering basics: system, user, and assistant roles
- Difference between base models and instruction-tuned models
- Running local models with Ollama (`llama3.2`, `deepseek-r1:1.5b`)

**Project — Webpage Summarizer**
> Scrapes any URL using BeautifulSoup and summarizes the content using a local Ollama model — no API cost, fully offline.

---

### Week 2 — Tool Calling & Function Calling ⭐

**What I learned:**
- How LLMs invoke external tools using structured JSON schemas
- The ReAct pattern: Reason → Act → Observe
- Building agents that decide *when* and *which* tool to call
- Handling multi-turn tool conversations

**Project — Tool-Augmented Assistant**
> An LLM agent connected to external tools (weather, calculator, search). The model reasons about which tool to use and assembles the final answer from tool results.

**Why this matters:** Tool calling is the core primitive behind every agentic system. Without it, LLMs can only generate text — with it, they can act.

---

### Week 3 — Building AI Products & Frontends

**What I learned:**
- Building AI UIs rapidly with Gradio and Streamlit
- Streaming LLM responses token by token
- Designing good UX for AI applications
- Deploying AI apps to Hugging Face Spaces

**Project — Interactive AI Chat App**
> A Gradio-based chat interface with real-time streaming, model switching between providers, and persistent conversation history.

---

### Week 4 — Evaluations & Structured Outputs

**What I learned:**
- Why evaluation is the hardest and most important part of LLM engineering
- The LLM-as-judge pattern for automated quality scoring
- Structured outputs using Pydantic to guarantee JSON format
- Building feedback loops and automated test pipelines

**Project — Eval Pipeline**
> An automated evaluation framework that uses a separate LLM to judge and score another model's outputs against a ground truth dataset.

---

### Week 5 — RAG: Retrieval Augmented Generation ⭐

**What I learned:**
- Vector databases and how semantic search works (ChromaDB, FAISS)
- Text chunking strategies: fixed-size, recursive, semantic
- Embedding models and cosine similarity
- The full RAG pipeline: ingest → chunk → embed → store → retrieve → generate
- Hybrid search: combining keyword and semantic retrieval

**Project — Document Q&A System**
> A RAG pipeline that ingests any PDF or text document, embeds it into a vector store, and answers natural language questions with source citations.

**Connection to XAI-IDS:** Stage 2 of XAI-IDS adds a RAG layer over a threat intelligence knowledge base, enabling the system to explain detections with referenced CVEs and attack patterns.

---

### Week 6 — Fine-Tuning LLMs

**What I learned:**
- When to fine-tune vs use RAG vs improve prompts
- LoRA and QLoRA: parameter-efficient fine-tuning techniques
- How to prepare and format a fine-tuning dataset
- 4-bit quantization to train on consumer hardware (RTX 3050, 4GB VRAM)

**Project — Domain-Fine-Tuned Model**
> Fine-tuned an open-source LLM on a domain-specific dataset using QLoRA — adapted the model's output style without retraining all parameters.

**Key insight:** Fine-tuning teaches the model *how* to respond (style, format, tone). RAG gives it *what* to say (knowledge). They solve different problems.

---

### Week 7 — Open Source Models & Local Inference

**What I learned:**
- Hugging Face Transformers library in depth
- Model quantization tradeoffs: FP16 → INT8 → INT4
- GGUF format and llama.cpp for efficient local inference
- Comparing open-source vs proprietary LLMs across tasks
- Ollama model management and custom Modelfiles

**Project — Fully Local AI Stack**
> A completely offline AI system: Ollama serves the model locally, a Gradio frontend provides the UI — no internet connection required after setup.

---

### Week 8 — Multi-Agent Systems ⭐

**What I learned:**
- Agentic AI architecture: chains vs agents vs multi-agent networks
- Agent orchestration using LangGraph and AutoGen
- Agent memory types: short-term (context), long-term (vector store), episodic
- Model Context Protocol (MCP) as a universal tool integration standard
- Human-in-the-loop design patterns

**Project — Multi-Agent Research System**
> A network of four specialized agents — Planner, Researcher, Analyst, Writer — each with dedicated tools and memory, orchestrated via LangGraph to produce structured research reports.

**Connection to XAI-IDS:** Stage 3 of XAI-IDS replaces the single-model architecture with a multi-agent network: a Detection Agent, an Explanation Agent, and a Reporting Agent — each with a defined role and memory.

---

## Flagship Project — XAI-IDS

Everything in this course feeds directly into **XAI-IDS** — my primary portfolio project.

**XAI-IDS** is an Explainable AI Intrusion Detection System that combines machine learning-based network traffic classification with explainability tools (SHAP), so security analysts can understand *why* a detection was flagged — not just *that* it was flagged.

| Stage | Stack | Status |
|-------|-------|--------|
| Stage 1 — Core Detection | Flask + Scikit-learn + SHAP | 🔨 In Progress |
| Stage 2 — Knowledge Layer | + RAG + ChromaDB | 📋 Planned |
| Stage 3 — Agentic Layer | + Multi-Agent + MCP | 📋 Planned |
| Stage 4 — Production | Docker + CI/CD + Monitoring | 📋 Planned |

---

## Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python 3.11 |
| LLM APIs | OpenAI, Anthropic Claude, Google Gemini |
| Local Models | Ollama — llama3.2, deepseek-r1:1.5b |
| Vector Databases | ChromaDB, FAISS |
| Frameworks | LangChain, LangGraph, Gradio, Streamlit |
| Fine-Tuning | Hugging Face Transformers, PEFT, QLoRA |
| Dev Environment | Cursor, JupyterLab, Anaconda |
| Hardware | Lenovo laptop · NVIDIA RTX 3050 (4GB VRAM) |

---

## Setup & Installation

**Prerequisites:** Python 3.11, Anaconda, Git. Optionally: Ollama for local models.

```bash
# 1. Clone the repository
git clone https://github.com/Ashish10102006/llm-engineering.git
cd llm-engineering

# 2. Create and activate the conda environment
conda create -n llms python=3.11
conda activate llms

# 3. Install dependencies
pip install -r requirements.txt

# 4. Configure environment variables
cp .env.example .env
# Open .env and add your API keys:
# OPENAI_API_KEY=...
# ANTHROPIC_API_KEY=...
# GOOGLE_API_KEY=...

# 5. (Optional) Pull local models via Ollama
ollama pull llama3.2
ollama pull deepseek-r1:1.5b
```

Each week's folder contains its own `README.md` with specific setup steps if needed.

---

## Progress Tracker

| Week | Topic | Status |
|------|-------|--------|
| Week 1 | LLM Foundations & First AI App | ✅ Complete |
| Week 2 | Tool Calling & Function Calling | 🔄 In Progress |
| Week 3 | Building AI Products & Frontends | ⏳ Upcoming |
| Week 4 | Evaluations & Structured Outputs | ⏳ Upcoming |
| Week 5 | RAG — Retrieval Augmented Generation | ⏳ Upcoming |
| Week 6 | Fine-Tuning LLMs | ⏳ Upcoming |
| Week 7 | Open Source Models & Local Inference | ⏳ Upcoming |
| Week 8 | Multi-Agent Systems | ⏳ Upcoming |

---

## Career Direction

I am working toward **Agentic AI Engineering** and **AI Security** roles, combining my Cybersecurity specialization with hands-on LLM Engineering skills.

Target roles include:
- Agentic AI Developer
- RAG Engineer
- LLM Engineer
- AI Security Engineer / AI Red Teamer

Targeting AI-first companies and Global Capability Centers across India.

---

## Connect

| Platform | Link |
|----------|------|
| LinkedIn | [linkedin.com/in/ashishpanda2028](https://linkedin.com/in/ashishpanda2028) |
| GitHub | [github.com/Ashish10102006](https://github.com/Ashish10102006) |
| University | ITER, SOA University · B.Tech CSE (Cybersecurity) · Graduating 2028 |

---

<div align="center">
  <sub>Built with consistency, one week at a time.</sub>
  <br><br>
  If this repository helped you, consider giving it a ⭐
</div>
