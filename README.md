# Moroccan Cuisine RAG Assistant

## Overview

This project implements a Retrieval-Augmented Generation (RAG) system focused on Moroccan cuisine.

The system uses:
- Qdrant as a vector database
- Sentence Transformers for embeddings
- A local ingestion pipeline
- A Streamlit interface for interaction

The goal is to retrieve relevant culinary knowledge and generate context-aware responses.

---

## Architecture

The system follows this pipeline:

1. Documents are processed and embedded using Sentence Transformers
2. Embeddings are stored in Qdrant
3. User queries are embedded
4. Relevant documents are retrieved from Qdrant
5. Retrieved context is passed to the generation module
6. The final answer is returned to the user

---

## Technologies Used

- Python
- Docker
- Qdrant
- sentence-transformers
- qdrant-client
- Streamlit

---

## Project Structure


├── scripts/
│ ├── ingest.py
│ └── chat.py
├── ui.py
├── requirements.txt
└── README.md


---

## Installation & Setup

### 1. Start Qdrant (Vector Database)

Open Terminal 1:


docker run -p 6333:6333 qdrant/qdrant


Qdrant will be available at:
http://localhost:6333

---

### 2. Install Dependencies

Open Terminal 2:


py -m pip install streamlit sentence-transformers qdrant-client


---

### 3. Ingest Documents into Qdrant


cd scripts
py ingest.py


This step:
- Loads documents
- Splits them into chunks
- Generates embeddings
- Stores them in Qdrant

---

### 4. Run Chat Interface (CLI)


py chat.py


---

### 5. Run Streamlit Interface

Go back to root folder:


cd ..
py -m streamlit run ui.py


Streamlit will open in your browser.

---

## How the RAG Works

- Query → Embedding
- Vector Search in Qdrant
- Retrieve top-k relevant chunks
- Pass context to generation model
- Return response

---

## Future Improvements

- Improve chunking strategy
- Tune top-k retrieval
- Use a stronger embedding model
- Improve prompt engineering
- Add reranking
- Improve UI experience

---

## Author

Assia Mouad  
Master ISI – AI Project  
Academic Year 2025/2026
