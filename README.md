# RAG Pipeline from Scratch (LangChain + ChromaDB)

This project implements a complete Retrieval-Augmented Generation (RAG) data ingestion pipeline from scratch, following Krish Naik’s RAG tutorial series. It loads raw documents (PDF / text), converts them into LangChain `Document` objects, chunks them, generates dense embeddings using a Hugging Face sentence-transformer model, and stores them in a ChromaDB vector store for efficient semantic retrieval. [web:51][web:70][web:73]

## Features

- Document loading for text and PDF files via LangChain loaders. [web:51][web:71]
- Uniform `Document` structure with `page_content` and rich `metadata`. [web:51]
- Chunking of long documents using `RecursiveCharacterTextSplitter`. [web:16]
- Embedding generation with `sentence-transformers/all-MiniLM-L6-v2`. [web:70][web:75]
- Persistent vector store using ChromaDB collections. [web:73][web:75]
- Modular Python classes for:
  - Embedding manager (model loading + batch encoding)
  - Vector store manager (add documents + metadata into Chroma) [web:73]

## Tech Stack

- **Language:** Python
- **RAG Framework:** LangChain
- **Embeddings:** `sentence-transformers/all-MiniLM-L6-v2` (SentenceTransformers) [web:70]
- **Vector Database:** ChromaDB (persistent client + collections) [web:73][web:75]
- **Environment / deps:** `uv`, `requirements.txt`, Jupyter Notebook / VS Code

## Project Structure (example)

```text
.
├─ data/
│  ├─ text_files/
│  └─ pdf_files/
├─ notebooks/
│  └─ rag_pipeline.ipynb
├─ src/
│  ├─ embedding_manager.py
│  └─ vector_store.py
├─ requirements.txt
└─ README.md

Setup & Installation
Clone the repository:

bash
git clone https://github.com/Pratyaksh-soni-05/RAG-test.git
cd RAG-test
Create and activate a virtual environment (or use uv as in the tutorial). [web:51]

Install dependencies:

bash
pip install -r requirements.txt
Make sure your data/ folder contains the sample PDFs / text files you want to index.

How to Run
Open the notebook:

bash
jupyter notebook notebooks/rag_pipeline.ipynb
Run the cells in order to:

Load documents (TXT + PDF).

Convert them into Document objects.

Apply chunking and generate embeddings.

Persist them into the ChromaDB vector store.

Use the resulting vector store in your RAG / Q&A pipeline to perform similarity search and retrieve relevant chunks at query time. [web:73]

Acknowledgements
Inspired by Krish Naik’s “Build RAG Pipeline From Scratch – Data Ingestion to Vector DB Pipeline” tutorial. [web:51]

Uses Hugging Face SentenceTransformers and ChromaDB for open-source embeddings and vector storage. [web:70][web:73]
