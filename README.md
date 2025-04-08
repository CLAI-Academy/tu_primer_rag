# 🚀 Building Your First Advanced RAG System

A step-by-step guide to creating a powerful Retrieval-Augmented Generation system with mixed document types.

## 📖 Overview

This repository contains a comprehensive implementation of an advanced RAG (Retrieval-Augmented Generation) system capable of processing multiple document types. Our example project builds a knowledge base from two distinct PDFs: one on decoder architectures and another on machine learning models for analysis.

## ⚙️ Architecture

RAG systems operate in two main phases:

### 1. ETL Pipeline (Extract, Transform, Load)
This phase processes your documents and prepares them for efficient retrieval:

```
Documents → Chunking → Embedding → Vector Database
```

### 2. Inference Pipeline
This phase handles user queries and generates relevant responses:

```
User Query → Embedding → Retrieval → Context-Enhanced Prompt → LLM → Response
```

## 🔧 Implementation Guide

### ETL Phase

1. **Set Up Embedding Model**
   - Recommended: OpenAI embeddings API
   - Alternative: Any embedding model of your choice
   - [OpenAI Embeddings Documentation](https://platform.openai.com/docs/guides/embeddings)

2. **Document Processing**
   - Option A: Build custom pipeline (detect tables, images, text)
   - Option B: Use Docling for structured document parsing
   - Maintain references to original PDF page numbers

3. **Transform to LangChain Documents**
   - Convert images to text descriptions
   - Format tables as markdown
   - Split large text into appropriate chunks

4. **Index in Vector Database**
   - Store embedded chunks in a vector database
   - Include metadata for source tracking

### Inference Phase

1. **Configure LLM**
   - Option A: OpenAI API (GPT models)
   - Option B: Groq API (free alternative)

2. **Build Retriever**
   - Option A: Manual implementation (encode query → vector similarity search)
   - Option B: LangChain integration with Qdrant

3. **Create Prompt Template**
   - Design a template that combines:
     - Original user query
     - Retrieved document chunks
     - System instructions

4. **Query Flow**
   - Process user question
   - Retrieve relevant document chunks
   - Fill prompt template
   - Generate response with LLM

5. **Optional: Implement Reranking**
   - Add a second-stage ranking system to improve retrieval quality

## 📊 Visualization

ETL Pipeline:
![ETL Pipeline](../img/ETL.png)

Inference Pipeline:
![Inference Pipeline](../img/Inference.png)

## 🚀 Getting Started

1. Clone this repository
2. Install dependencies: `pip install -r requirements.txt`
3. Configure your API keys in `.env`
4. Run the notebook to build your first RAG system

## 📚 Resources

- [LangChain Documentation](https://python.langchain.com/docs/get_started/introduction)
- [OpenAI API Documentation](https://platform.openai.com/docs/introduction)
- [Qdrant Vector Database](https://qdrant.tech/documentation/)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.