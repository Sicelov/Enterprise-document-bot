# Enterprise Document Q&A bot

## Table of Contents

- [Overview](#overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Data Analysis](#data-analysis)
- [Key Findings](#key-findings)
- [Conclusion](#conclusion)

### Overview

This project involved developing a Document Q&A chatbot powered by Large Language Models (LLMs). The bot allows users to upload internal documents (PDFs, DOCX, etc.) and ask natural language questions to retrieve precise answers grounded in the uploaded content. This simulates real-world enterprise use cases like legal, HR, and compliance document intelligence.

![Enterprise Document Q&A bot](https://github.com/Sicelov/Enterprise-document-bot/blob/main/Document-bot.png)

### Data Sources

- User-uploaded documents (PDF, Word, Text)
- Sample corporate documents (e.g., contracts, HR manuals, product policies)

### Tools

- LangChain for chaining document retrieval and LLMs
- OpenAI GPT-4 for natural language response generation
- FAISS for vector-based semantic search
- HuggingFace Transformers for embedding generation
- Streamlit for the frontend UI
- Python-dotenv and .streamlit/secrets.toml for secret management
- pypdf for extracting text from PDF files

### Data Cleaning

- Extracted raw text from documents using PyPDFLoader (PDFs)
- Removed empty pages, headers/footers, and irrelevant whitespace
- Split long documents into overlapping text chunks using RecursiveCharacterTextSplitter to maintain context
- Embedded cleaned chunks using Sentence Transformers (all-MiniLM-L6-v2)

### Data Analysis

- Text Extraction: Loads document and extracts content.
- Chunking + Embedding: Splits content into manageable sections and converts them into dense vector representations.
- Vector Indexing: Stores embeddings in FAISS vector store for fast semantic retrieval.
- User Query: Converts user’s question into an embedding and retrieves the most relevant document chunks.
- LLM Response: Sends both the query and retrieved context to OpenAI’s GPT-4 to generate a grounded and accurate answer.
- Frontend: Streamlit provides an interactive interface for document upload and Q&A.

### Key Findings

- Chunk size and overlap significantly affect answer accuracy and hallucination rate.
- FAISS provides fast and reliable context retrieval even on large documents.
- Using open-source embeddings like HuggingFace models eliminates dependency on OpenAI's embeddings, reducing cost.

### Conclusion

The Enterprise Document Q&A Bot successfully showcases how LLMs can be integrated into business workflows to automate information retrieval. It demonstrates applied skills in NLP, vector search, embeddings, and deploying production-ready LLM systems. 


