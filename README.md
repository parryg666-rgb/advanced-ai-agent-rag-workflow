# Advanced AI Agent System Workflow

This project presents an advanced AI agent system architecture using an n8n workflow. The workflow demonstrates how a production-ready AI agent can process uploaded documents, build a RAG knowledge base, retrieve relevant information, use tools, manage memory, and control cost.

## Project Overview

The goal of this assignment is to design an AI agent workflow that maps the complete process from document ingestion to final response generation.

The system includes:

- Agent system overview
- Tool usage
- RAG pipeline
- Retrieval flow
- File ingestion and processing
- Short-term and long-term memory
- Cost and latency control
- Production use cases

## Workflow Parts

The n8n workflow has two main parts.

### 1. Document Ingestion Workflow

This part runs when a user uploads a document such as a PDF.

Steps:

1. Upload document
2. Validate uploaded file
3. Extract text from the document
4. Split text into smaller chunks
5. Create embeddings for each chunk
6. Store chunks in a vector database
7. Make the document searchable for future questions

### 2. Agent Chat Workflow

This part runs when a user asks a question.

Steps:

1. Receive user question
2. Check if an answer is already cached
3. Create an embedding for the question
4. Search the vector database
5. Retrieve relevant document chunks
6. Load short-term and long-term memory
7. Use tools such as CRM or ticket lookup if needed
8. Generate the final answer using the AI model
9. Save conversation memory
10. Cache the answer for future use

## Why Agents Use Tools

AI agents use tools because the AI model alone cannot access live systems, private databases, uploaded files, or external applications.

Tools help the agent:

- Search documents
- Read uploaded files
- Call APIs
- Look up customer or ticket data
- Summarize information
- Store and retrieve memory
- Perform real business actions

## RAG Pipeline

RAG stands for Retrieval-Augmented Generation.

In this project, RAG works like this:

```text
Upload Document
↓
Extract Text
↓
Split into Chunks
↓
Create Embeddings
↓
Store in Vector Database
↓
User Asks Question
↓
Retrieve Relevant Chunks
↓
Generate Answer
