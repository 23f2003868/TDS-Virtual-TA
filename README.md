# 📚 TDS Virtual TA – RAG-Based Q&A System

A full-stack Retrieval-Augmented Generation (RAG) system built with **FastAPI**, designed to help students query knowledge from IITM’s **TDS course content and TDS Discourse**.

It preprocesses raw content into vector embeddings, stores them in a SQLite database, and provides an LLM-backed API endpoint (`/query`) to answer natural language questions using **OpenAI-compatible APIs via AIPipe**.

---

## 🚀 Features

- 🧠 RAG-based querying over Discourse + Markdown content
- 🔎 Local chunk-level semantic search using cosine similarity
- 🧾 Support for both TDS Discourse posts and course `.md` notes
- 🧵 Adjacent-chunk enrichment for deeper LLM context
- 🧠 Uses `text-embedding-3-small` + `gpt-4o-mini` from [AIPipe](https://aipipe.org)
- 🖼️ Supports multimodal queries with base64-encoded images
- ⚡ FastAPI backend with `/query` and `/health` endpoints
- 🔒 Environment-based API key management via `.env`

---

## 📂 Folder Structure
.
├── app.py # FastAPI app (LLM query interface)
├── discourse_scrap.py
├── tds_scrap.py
├── knowledge_base.db
├── requirements.txt
├── LICENSE 
└── README.md 

---


## ⚙️ Setup & Usage

### 🔧 1. Install Requirements

```bash
python -m venv env
env\Scripts\activate  # On Windows
pip install -r requirements.txt
```

---

### 🧠 2. Create a .env file
```bash
API_KEY="your_aipipe_or_openai_key"
```

---

### 🚀 3. Run the API
```bash
uvicorn app:app --host 0.0.0.0 --port 8000 --reload
```