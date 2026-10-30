# Retrieval-Augmented Generation (RAG) – PDF Question Answering System

## 1. Project Overview

This project implements a Retrieval-Augmented Generation (RAG) system for answering questions from uploaded PDF documents.

The system retrieves relevant information from a PDF using semantic similarity search and generates answers using a Large Language Model (LLM).

The implementation is based on the core methodology of the research paper **"Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks" by Patrick Lewis et al. (2020).**

This is an educational adaptation of the paper's core RAG methodology, not a complete reproduction of the original research model.

## 2. Objectives

- Understand the architecture and working of RAG.
- Extract text from PDF documents.
- Divide documents into smaller text chunks.
- Generate embeddings using Sentence Transformers.
- Store and retrieve vectors using FAISS.
- Generate context-based answers using Groq AI.
- Display source page references for retrieved information.

## 3. Technologies Used

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| Google Colab | Notebook-based implementation |
| Streamlit | User interface |
| PyPDF | PDF text extraction |
| Sentence Transformers | Text embedding generation |
| FAISS | Vector similarity search |
| Groq API | AI-based answer generation |
| NumPy | Numerical operations |
| Pandas | Evaluation result handling |

## 4. System Architecture

**Workflow:**

PDF Upload → Text Extraction → Text Chunking → Embedding Generation → FAISS Vector Index → Similarity Retrieval → Context Construction → Groq LLM → Generated Answer


## 5. Implementation Methodology

1. **PDF Extraction:** Extracts text from uploaded PDF documents using PyPDF.
2. **Text Chunking:** Divides the extracted text into chunks of 500 words with 100 words of overlap.
3. **Embedding Generation:** Uses the all-MiniLM-L6-v2 model to convert text chunks into numerical vectors.
4. **Vector Indexing:** Stores embeddings in a FAISS IndexFlatIP index.
5. **Information Retrieval:** Retrieves the top three relevant chunks based on semantic similarity.
6. **Answer Generation:** Uses the Groq API with the openai/gpt-oss-20b model to generate answers from retrieved context.
7. **Source References:** Displays the page numbers associated with retrieved passages.

## 6. Installation and Execution

### Step 1: Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/RAG-Research-Paper-Implementation.git
```

### Step 2: Open the project folder

```bash
cd RAG-Research-Paper-Implementation
```

### Step 3: Create a virtual environment (optional)

```bash
python -m venv venv
```

### Step 4: Install dependencies

```bash
pip install -r requirements.txt
```

### Step 5: Configure the Groq API key

Create a `.env` file in the project folder:

```text
GROQ_API_KEY=your_groq_api_key
```

Keep the `.env` file private. Never upload your API key to GitHub.

### Step 6: Run the Streamlit application

```bash
streamlit run app.py
```

**Google Colab:** Open `RAG_Implementation.ipynb` in Google Colab and execute the notebook cells sequentially. Add your Groq API key through Colab Secrets using the name `GROQ_API_KEY`.

## 7. Features

- PDF document upload and text extraction.
- Automatic text chunking.
- Semantic search using embeddings.
- FAISS-based vector retrieval.
- AI-generated answers using retrieved context.
- Source page references.
- Multiple-question evaluation.
- Retrieval performance measurement.

## 8. Limitations

- The current implementation processes one PDF at a time.
- Scanned PDFs may require OCR.
- Retrieval quality depends on document content and chunking.
- Generated answers may occasionally contain unsupported information.
- Groq API access requires an internet connection.


## 9. Future Scope

- Support multiple PDF documents.
- Implement OCR for scanned documents.
- Improve retrieval using reranking.
- Add persistent chat history.

## 10. Research Paper Reference

Lewis, P. et al. (2020). **Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks.** Advances in Neural Information Processing Systems (NeurIPS).

Research Paper: https://arxiv.org/abs/2005.11401

## 11. Author

**Name:** Tanishka Vishnu Tapkir

**PRN:** 202401110071

**Branch:** Artificial Intelligence and Machine Learning
