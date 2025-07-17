# 🧠 Mini LLM-Powered RAG QA System

## ✅ Project Overview
This is a Retrieval-Augmented Generation (RAG) pipeline designed to answer clinical questions using a WHO ICD-10 PDF document as the sole knowledge base. The system integrates embeddings, semantic search, and an open-source local LLM to deliver accurate answers to user queries.

---

## 🧩 Components

### 1. Document Ingestion & Chunking
- **Tool:** PyPDF2
- Extracted 377-page ICD-10 PDF text
- Chunked into ~300-token blocks with 50-token overlap
- Total chunks created: **379**

### 2. Embedding & Vector Store
- **Model:** `all-MiniLM-L6-v2` from SentenceTransformers
- **Vector store:** FAISS (flat L2 index)
- Each chunk embedded and indexed for semantic similarity search

### 3. Query Interface
- Simple script/Notebook input via Python
- Top-k relevant chunks retrieved based on semantic similarity

### 4. LLM Integration
- **Tool:** [Ollama](https://ollama.com/)
- **Model Used:** `mistral`
- Retrieved context + user query sent to local LLM via `ollama.chat()`
- Final response generated using RAG prompt structure

---

## 🧪 Sample Queries and Outputs

### 🔹 Query 1:
**Q:** *Give me the correct coded classification for the following diagnosis: “Recurrent depressive disorder, currently in remission”*  
**A:** ``` The correct coded classification for 'Recurrent depressive disorder, currently in remission' is F33.4 according to ICD-10.```

---

### 🔹 Query 2:
**Q:** *What are the diagnostic criteria for Obsessive-Compulsive Disorder (OCD)?*  
**A:**  ``` Obsessions or compulsions must be present on most days for at least 2 consecutive weeks. They must cause significant distress or interfere with daily activities. The thoughts must be recognized as the individual's own. At least one thought or act must be unsuccessfully resisted. The thoughts or acts must not be pleasurable. Obsessions (thoughts/images) must be repetitive, intrusive, and unpleasant. ``` 



---

## 🤖 AI Tools Disclosure
- **ChatGPT** was used to guide architecture and debugging decisions.
- Code was written from scratch in Jupyter Notebook based on this guidance.
- **No Copilot or pre-written GitHub code used.**

---

## ⚠️ Limitations
- No GUI due to time constraint (Gradio can be added later)
- No reranking or caching implemented
- PDF parsing is basic — advanced preprocessing could improve performance

---

## ✅ Tools Used
- `PyPDF2`, `SentenceTransformers`, `FAISS`, `Ollama`, `NumPy`, `pickle`

---

## 📬 Submission
- Code file: `rag_pipeline.ipynb` or `rag_pipeline.py`
- This README file

