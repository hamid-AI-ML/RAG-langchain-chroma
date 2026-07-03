#  RAG Pipeline with LangChain

A simple Retrieval-Augmented Generation (RAG) project that demonstrates how to build a document question-answering pipeline using LangChain, Hugging Face embeddings, and ChromaDB.

The project loads a PDF document, splits it into chunks, generates embeddings, stores them in a vector database, and prepares the data for retrieval-based question answering.

---

## Features

- Load PDF documents
- Split documents into semantic chunks
- Generate embeddings using Sentence Transformers
- Store embeddings in Chroma Vector Database
- Prompt template for Retrieval-Augmented Generation (RAG)
- Easy to extend with any LLM (Gemini, OpenAI, Grok, etc.)

---

## Tech Stack

- Python
- LangChain
- HuggingFace Embeddings
- Sentence Transformers
- ChromaDB
- PyPDF
- Google Colab

---

## Project Workflow

```text
PDF
 │
 ▼
Load Document
 │
 ▼
Split into Chunks
 │
 ▼
Generate Embeddings
 │
 ▼
Store in ChromaDB
 │
 ▼
Retrieve Relevant Chunks
 │
 ▼
LLM Prompt
 │
 ▼
Answer Generation
```

---

## Installation

Install all required dependencies:

```bash
pip install \
langchain==1.3.1 \
langchain-community==0.4.1 \
langchain-core==1.4.0 \
langchain-text-splitters==1.1.2 \
langchain-classic==1.0.7 \
langchain-huggingface \
langchain-google-genai \
sentence-transformers \
chromadb \
pypdf \
"pydantic<=2.12.3" \
"numpy<2.1" \
opentelemetry-api \
opentelemetry-sdk \
langchain-xai
```

---

## Project Structure

```
.
├── rag.py
├── README.md
└── requirements.txt
```

---

## How It Works

1. Load a PDF document.
2. Split the text into overlapping chunks.
3. Generate embeddings using `all-MiniLM-L6-v2`.
4. Store vectors inside ChromaDB.
5. Retrieve relevant chunks for user queries.
6. Pass retrieved context to an LLM prompt.
7. Generate concise answers.

---

## Embedding Model

```
sentence-transformers/all-MiniLM-L6-v2
```

---

## Vector Database

```
ChromaDB
```

---

## Prompt Strategy

The system prompt instructs the model to:

- Answer using retrieved context only.
- Respond concisely.
- Say "I don't know" if the answer is unavailable.

---

## Future Improvements

- Streamlit or Gradio interface
- Persistent vector database
- Multiple PDF support
- Hybrid search
- Metadata filtering
- Conversational memory
- API deployment with FastAPI
- Support for OpenAI, Gemini, Grok, Claude, and Ollama

---

## License

MIT License
