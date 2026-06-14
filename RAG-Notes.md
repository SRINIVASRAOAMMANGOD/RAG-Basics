# RAG (Retrieval-Augmented Generation) - Complete Notes

## What is RAG?

RAG = Retrieval Augmented Generation.

Instead of relying only on an LLM's training data:

```text
User Question
↓
Retrieve Relevant Information
↓
Give Retrieved Information to LLM
↓
Generate Answer
```

Purpose:

* Answer questions from private documents
* Reduce hallucinations
* Use external knowledge
* Keep knowledge updated

---

# Complete RAG Workflow

```text
PDF
↓
Load Document
↓
Chunking
↓
Embeddings
↓
Vector Database (ChromaDB)
↓
Retriever
↓
Context Creation
↓
Prompt Creation
↓
Tokenizer
↓
LLM
↓
Answer
```

This is the complete RAG pipeline.

---

# Libraries Learned

## Document Loading

```python
PyPDFLoader
```

Package:

```python
langchain_community.document_loaders
```

---

## Chunking

```python
RecursiveCharacterTextSplitter
```

Package:

```python
langchain_text_splitters
```

---

## Embeddings

```python
SentenceTransformer
```

Package:

```python
sentence-transformers
```

LangChain version:

```python
HuggingFaceEmbeddings
```

---

## Vector Database

```python
chromadb
```

LangChain version:

```python
Chroma
```

---

## LLM

```python
transformers
```

Classes:

```python
AutoTokenizer
AutoModelForSeq2SeqLM
```

---

# Models Used

## Embedding Model

```python
all-MiniLM-L6-v2
```

Purpose:

```text
Text
↓
Vector Embedding
```

Output Dimension:

```text
384
```

---

## LLM

```python
google/flan-t5-base
```

Purpose:

```text
Context + Question
↓
Answer
```

---

# Embeddings

Definition:

Numerical representation of text.

Example:

```text
"I love AI"

↓

[0.23, -0.41, 0.67, ...]
```

Properties:

```text
Similar Meaning
↓
Similar Vectors
```

Used For:

* Semantic Search
* Retrieval
* Similarity Search

---

# Chunking

Definition:

Split large documents into smaller pieces.

Why?

```text
Large Document
↓
Too Big For Efficient Retrieval
↓
Split Into Chunks
```

---

# RecursiveCharacterTextSplitter

Used:

```python
RecursiveCharacterTextSplitter(
    chunk_size=500,
    chunk_overlap=50
)
```

Separators:

```text
1. \n\n
2. \n
3. Space
4. Character
```

Why Recursive?

It keeps trying smaller separators until the chunk size requirement is met.

---

# ChromaDB

Definition:

Vector Database.

Stores:

```text
Chunk
+
Embedding
```

Example:

```text
Chunk 1
Embedding 1

Chunk 2
Embedding 2
```

Purpose:

Fast Similarity Search.

---

# Retrieval

Definition:

Find the most relevant chunks.

Process:

```text
Question
↓
Embedding
↓
Similarity Search
↓
Top K Chunks
```

Example:

```python
retriever.invoke(query)
```

---

# Semantic Search

Traditional Search:

```text
Keyword Match
```

Semantic Search:

```text
Meaning Match
```

Example:

Question:

```text
What is Logistic Regression?
```

Retriever finds relevant chunks even if wording differs.

---

# Retriever

Definition:

Component that fetches relevant chunks.

Create:

```python
retriever = vectorstore.as_retriever()
```

Use:

```python
docs = retriever.invoke(query)
```

Output:

```python
Document Objects
```

---

# Context Creation

Retrieved Chunks:

```python
docs
```

Convert To Context:

```python
context = "\n\n".join(
    doc.page_content
    for doc in docs
)
```

Result:

```text
One Large Context Block
```

---

# Prompt Creation

```python
prompt = f"""
Context:
{context}

Question:
{query}

Answer:
"""
```

Purpose:

```text
Give Context
+
Give Question
↓
LLM Generates Answer
```

---

# Tokenizer

Definition:

Converts text into tokens.

Example:

```text
Hello World

↓

["Hello", "World"]
```

or

```text
["Hel", "lo", "World"]
```

depending on tokenizer.

Used before model inference.

---

# FLAN-T5

Definition:

Instruction-following LLM from Google.

Type:

```text
Seq2Seq (Sequence-to-Sequence)
```

Flow:

```text
Input Text
↓
Output Text
```

Example:

```text
Question
↓
Answer
```

Why Used?

* Free
* Open Source
* Runs in Colab
* Good for Learning RAG

---

# Important Classes Learned

## Embeddings

```python
SentenceTransformer
HuggingFaceEmbeddings
```

## Chunking

```python
RecursiveCharacterTextSplitter
```

## Vector Database

```python
PersistentClient
Collection
Chroma
```

## Retrieval

```python
Retriever
```

## LLM

```python
AutoTokenizer
AutoModelForSeq2SeqLM
```

---

# Important Code Patterns

## Embedding

```python
embedding_model.encode(text)
```

---

## Store In Chroma

```python
collection.add(
    embeddings=embeddings,
    documents=chunks,
    ids=ids
)
```

---

## Retrieval

```python
collection.query(
    query_embeddings=[query_embedding],
    n_results=3
)
```

---

## LangChain Retrieval

```python
retriever.invoke(query)
```

---

## Generation

```python
outputs = model.generate(
    **inputs,
    max_new_tokens=100
)
```

---

# LangChain

Definition:

Framework for building LLM applications.

Provides:

* Document Loaders
* Chunkers
* Embeddings
* Vector Stores
* Retrievers
* Chains
* Agents

---

# Was LangChain Used?

YES.

Used Components:

```python
PyPDFLoader
RecursiveCharacterTextSplitter
HuggingFaceEmbeddings
Chroma
Retriever
```

Therefore:

```text
Manual RAG
✅ Learned

LangChain RAG
✅ Learned
```

Not Learned Yet:

```text
LangGraph
Agents
Agentic RAG
Production LangChain
```

---

# Learning Roadmap Recap

Completed:

```text
Embeddings
Sentence Transformers
Cosine Similarity
Semantic Search
ChromaDB
PDF Loading
Chunking
RecursiveCharacterTextSplitter
Embeddings Generation
Vector Storage
Retrieval
Context Creation
Prompt Creation
Tokenizer
FLAN-T5
Manual RAG
LangChain RAG
```

Current Level:

```text
RAG Fundamentals      ✅ Complete
Basic RAG Projects    ✅ Ready
Intermediate RAG      🔄 Started
Advanced RAG          ⬜ Not Started
```

---

# Final Interview Mental Model

Remember This Diagram:

```text
PDF
↓
Chunks
↓
Embeddings
↓
ChromaDB
↓
Retriever
↓
Context
↓
Prompt
↓
Tokenizer
↓
FLAN-T5
↓
Answer
```

If you understand this flow, you understand the RAG system you built.
