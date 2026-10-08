# Traditional-RAG-and-Agentic-RAG
Implementation of Traditional RAG and Agentic RAG systems using Python, LangChain, LLMs, embeddings, vector databases, and intelligent retrieval workflows.
# Traditional RAG and Agentic RAG

This repository contains implementations of **Traditional Retrieval-Augmented Generation (RAG)** and **Agentic RAG** using Python, LangChain, vector databases, embeddings, and Google Gemini models.

The project demonstrates how information can be retrieved from documents using semantic search and then provided to an LLM to generate context-aware answers. It also demonstrates an agentic workflow where the system can decide whether retrieval is required before generating an answer.

## Projects

### 1. Traditional RAG

The Traditional RAG implementation demonstrates a complete retrieval-augmented generation pipeline:

**Documents → Chunking → Embeddings → Vector Database → Retrieval → LLM → Answer**

Key components include:

- Loading TXT and PDF documents
- Document chunking using `RecursiveCharacterTextSplitter`
- Text embeddings using `SentenceTransformer`
- Vector storage using **ChromaDB**
- Semantic similarity search
- Retrieval of relevant document chunks
- Context-based answer generation

### 2. Agentic RAG

The Agentic RAG implementation extends the traditional RAG approach using **LangGraph** to create a stateful workflow.

The workflow consists of:

**Question → Retrieval Decision → Retrieve / Generate → Answer**

The system:

- Receives a user question
- Determines whether document retrieval is required
- Retrieves relevant documents when necessary
- Uses retrieved context to generate an answer
- Generates a direct answer when retrieval is not required

The workflow is implemented using `StateGraph` and conditional routing.

### 3. MongoDB RAG

The repository also includes a MongoDB-based RAG implementation demonstrating vector search with **MongoDB Atlas**.

Pipeline:

**PDF → Chunking → Gemini Embeddings → MongoDB Vector Search → Retrieved Context → Gemini LLM**

It includes:

- PDF document loading
- Document chunking
- Gemini embeddings
- MongoDB document storage
- MongoDB Atlas Vector Search
- Semantic retrieval
- Context-aware response generation

## Technologies Used

- Python
- LangChain
- LangGraph
- Google Gemini
- Gemini Embeddings
- Sentence Transformers
- ChromaDB
- MongoDB Atlas Vector Search
- FAISS
- PyPDF / PyMuPDF
- Jupyter Notebook

## Repository Structure

```text
Traditional-RAG-and-Agentic-RAG/
│
├── traditionalrag.ipynb
├── agentic_rag.ipynb
├── ragmongodb.ipynb
│
├── README.md
└── requirements.txt
```

## RAG Architecture

```text
Documents
    ↓
Document Loading
    ↓
Text Chunking
    ↓
Embedding Generation
    ↓
Vector Database
    ↓
Similarity Search
    ↓
Relevant Context
    ↓
LLM
    ↓
Generated Answer
```

## Agentic RAG Architecture

```text
User Question
      ↓
Retrieval Decision
      ↓
 ┌────┴─────┐
 ↓          ↓
Retrieve   Generate
 ↓          ↑
 └────┬─────┘
      ↓
   Answer
```

## Getting Started

### Clone the repository

```bash
git clone https://github.com/<your-username>/Traditional-RAG-and-Agentic-RAG.git
cd Traditional-RAG-and-Agentic-RAG
```

### Create a virtual environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Configure API Keys

Create a `.env` file:

```env
GOOGLE_API_KEY=your_google_api_key
```

**Do not commit API keys, passwords, MongoDB connection strings, or other secrets to GitHub.**

## Running the Notebooks

Open Jupyter Notebook:

```bash
jupyter notebook
```

Then run:

```text
traditionalrag.ipynb
agentic_rag.ipynb
ragmongodb.ipynb
```

## Learning Objectives

This project demonstrates practical understanding of:

- Retrieval-Augmented Generation
- Semantic search
- Text embeddings
- Vector databases
- Document processing
- LLM-based generation
- LangChain
- LangGraph
- Conditional AI workflows
- Agentic AI concepts
- MongoDB Vector Search

## Future Improvements

- Add hybrid search combining keyword and semantic retrieval
- Improve retrieval decision logic using an LLM-based router
- Add conversation memory
- Add document upload functionality
- Add reranking for retrieved documents
- Add evaluation metrics for RAG quality
- Build a Streamlit web interface
- Add citation and source tracking

## Author

**Shashank MN**

Electronics and Communication Engineering | AI/ML | Generative AI | Agentic AI | VLSI

---

⭐ If you find this project useful, consider giving the repository a star.
