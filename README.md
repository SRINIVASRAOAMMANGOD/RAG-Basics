# Retrieval-Augmented Generation (RAG) Learning Journey

This repository documents my hands-on learning journey in Retrieval-Augmented Generation (RAG), starting from embeddings and semantic search to building a complete PDF Question Answering system using LangChain, ChromaDB, and open-source Large Language Models (LLMs).

---

## Learning Objective

Build a complete RAG pipeline capable of:

* Loading PDF documents
* Splitting documents into meaningful chunks
* Generating embeddings
* Storing embeddings in a vector database
* Retrieving relevant context
* Generating context-aware answers using an LLM

---

## Repository Structure

```text
.
├── RAG-Fundamentals.ipynb
├── Semantic Search and chromeDB.ipynb
├── Chunking.ipynb
├── Embeddings_+_ChromaDB_+_Retrieval.ipynb
├── LangChain_RAG.ipynb
├── NBayesLogReg.pdf
└── README.md
```

---

## Recommended Learning Order

### 1. RAG-Fundamentals.ipynb

Topics Covered:

* Embeddings
* Sentence Transformers
* Cosine Similarity
* Semantic Similarity

Key Learning:
Understand how text is converted into numerical vectors and how semantic similarity is measured.

---

### 2. Semantic Search and chromeDB.ipynb

Topics Covered:

* Semantic Search
* Similarity Search
* Query Embeddings
* ChromaDB Basics

Key Learning:
Build a semantic search engine capable of retrieving relevant information based on meaning rather than keywords.

---

### 3. Chunking.ipynb

Topics Covered:

* Text Chunking
* RecursiveCharacterTextSplitter
* Chunk Size
* Chunk Overlap
* PDF Processing

Key Learning:
Learn how large documents are divided into smaller chunks before embedding and retrieval.

---

### 4. Embeddings_+*ChromaDB*+_Retrieval.ipynb

Topics Covered:

* PDF Loading
* Chunk Embeddings
* Vector Storage
* ChromaDB Collections
* Retrieval

Key Learning:
Create a complete retrieval pipeline capable of finding relevant chunks from a document.

---

### 5. LangChain_RAG.ipynb

Topics Covered:

* LangChain
* HuggingFaceEmbeddings
* Chroma Vector Store
* Retriever
* Prompt Construction
* FLAN-T5 Integration

Key Learning:
Build a complete end-to-end RAG system using LangChain.

---

## RAG Pipeline Built

```text
PDF
↓
Chunking
↓
Embeddings
↓
ChromaDB
↓
Retriever
↓
Context Creation
↓
Prompt
↓
LLM (FLAN-T5)
↓
Answer
```

---

## Technologies Used

* Python
* Google Colab
* LangChain
* ChromaDB
* Sentence Transformers
* Hugging Face Transformers
* FLAN-T5
* PyPDF
* NumPy

---

## Dataset

Document Used:

* NBayesLogReg.pdf

Topics Covered in the Document:

* Naive Bayes
* Logistic Regression
* Generative Classifiers
* Discriminative Classifiers

---

## Skills Acquired

* Retrieval-Augmented Generation (RAG)
* Semantic Search
* Embeddings
* Sentence Transformers
* Vector Databases
* ChromaDB
* Document Chunking
* Information Retrieval
* LangChain
* Prompt Engineering
* LLM Integration
* PDF Question Answering Systems

---

## Key Concepts Learned

### Embeddings

Numerical vector representations of text that capture semantic meaning.

### Semantic Search

Retrieving information based on meaning rather than exact keyword matching.

### Chunking

Splitting large documents into smaller, meaningful pieces for retrieval.

### ChromaDB

A vector database used to store and retrieve embeddings efficiently.

### Retriever

A component that finds the most relevant chunks for a user query.

### FLAN-T5

An instruction-following Large Language Model used to generate answers from retrieved context.

### LangChain

A framework used to build applications powered by LLMs and retrieval systems.

---

## Current Progress

Completed:

* Embeddings
* Sentence Transformers
* Cosine Similarity
* Semantic Search
* ChromaDB
* Chunking
* Retrieval
* LangChain RAG
* PDF Question Answering

Upcoming Topics:

* Advanced Retrieval
* Different Chunking Strategies
* Reranking
* LangGraph
* Agentic RAG

---

## Outcome

Successfully built a complete PDF-based RAG system capable of retrieving relevant information from a document and generating context-aware answers using an open-source LLM.
