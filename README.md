# PDF Question-Answer ChatBot

This project is a **document-based AI chatbot** that lets you upload a PDF, search its content, and get **context-aware answers** to your questions in natural language.

The chatbot combines:
- **pdfplumber** → PDF text extraction  
- **SentenceTransformers** → Semantic embeddings (`all-MiniLM-L6-v2`)  
- **FAISS** → Vector similarity search  
- **Hugging Face Transformers** (`flan-t5-base`) → Q&A generation  
- **Gradio** → Interactive web UI  

---

## 🚀 Features
- 📄 **Upload PDFs** and extract their text
- 🔍 **Semantic search** to find relevant content
- 🤖 **Natural language Q&A** using a Transformer model
- 🌐 **Web interface** powered by Gradio
- ⚡ **Fast inference** with warmup at startup

---

## How It Works
-1. **PDF Processing**

The uploaded PDF is read page-by-page using pdfplumber.

Text is tokenized into sentences with NLTK.

-2. **Embedding & Indexing**

Sentences are converted to vectors using SentenceTransformer (all-MiniLM-L6-v2).

FAISS indexes the vectors for fast similarity search.

-3. **Answer Generation**

When you ask a question, the most relevant sentences are retrieved from FAISS.

A Transformer model (flan-t5-base) generates a final answer.

-4. **Gradio Interface**

Provides a user-friendly interface for uploading PDFs and chatting.
