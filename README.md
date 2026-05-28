# Document Ingestion & RAG Platform (NotebookLM-Style)

A production-oriented document intelligence platform for enterprise knowledge workflows.  
It is designed to ingest multi-format documents, convert them into structured artifacts, build searchable knowledge bases, and support grounded question answering with citations, images, and optional knowledge graph augmentation.

## Overview

This platform focuses on the full document ingestion lifecycle:

**upload -> parse -> artifact storage -> chunking -> embedding -> indexing -> retrieval/chat**

It supports enterprise-style document processing where raw files must be preserved, parsed outputs must remain traceable, and retrieval must stay reliable, explainable, and scalable.

## Key Technical Highlights

- **End-to-end ingestion pipeline** for document upload, parsing, artifact generation, chunking, embedding, indexing, and retrieval
- **Multi-parser architecture** with support for **Docling, Marker, MinerU, PaddleOCR, MarkItDown, and Chandra**
- **Structured parser artifact contract** using normalized outputs such as **Markdown, HTML, manifest, and extracted assets**
- **Hybrid retrieval pipeline** combining **vector search + lexical retrieval**, with support for **reranking**
- **Grounded chat experience** with **inline citations** and **image evidence** resolved from parsed document assets
- **Workspace-based knowledge isolation** for multi-team or multi-domain usage
- **Access control and document permissions** for secure collaboration
- **Document versioning, ingestion job tracking, and analytics** for operational visibility
- **Optional Knowledge Graph ingestion** powered by **LightRAG**
- **Separated service architecture** designed for local development and Kubernetes deployment

## Architecture

The system is built around a modular, ingestion-first architecture:

- **FastAPI backend** for orchestration, APIs, and retrieval workflows
- **Asynchronous worker pipeline** for ingestion and indexing jobs
- **Dedicated parser services** that can scale independently by parser type or compute profile
- **MinIO / S3-compatible object storage** for original files and parsed artifacts
- **PostgreSQL** for document metadata, jobs, ACL, and conversational state
- **Chroma or Qdrant** for vector indexing and retrieval
- **Optional Knowledge Graph layer** for graph-based exploration and enriched retrieval
- **React + TypeScript frontend** for workspace management, document operations, analytics, and chat


## Target Architecture 
![img-5](assets/923f06e6c4fd45a31cec.jpg)

## Show case

Below are tested examples from the current system:

![img-7](assets/fffce76dca0d4b53121c.jpg)
![img-1](assets/301082d2afb22eec77a3.jpg)
![img-2](assets/3635289282b603e85aa7.jpg)
![img-4](assets/6b3772ea09c3889dd1d2.jpg)
![img-6](assets/ab51b18ccaa54bfb12b4.jpg)

## Use Cases

- Build an **internal knowledge base** from PDFs, scanned files, reports, SOPs, and business documents
- Deploy a **document-grounded chatbot** with transparent citations and supporting evidence
- Support **re-ingestion and re-indexing workflows** when changing parsers, embeddings, or retrieval strategies
- Separate knowledge by **workspace, team, or business domain**
- Explore extracted entities, relationships, and document insights through **analytics and knowledge graph views**

## Tech Stack

**Backend:** FastAPI, Python  
**Frontend:** React, TypeScript  
**Storage & Data:** MinIO, PostgreSQL  
**Retrieval & Indexing:** Chroma, Qdrant, hybrid retrieval, reranking  
**Knowledge Graph:** LightRAG  
**Deployment:** Docker, Kubernetes


## **Related Project: Financial Assistant**
![img-3](assets/375a8661f8d3768d2fc2.jpg)