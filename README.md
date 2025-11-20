# 🏥 SmartHealth RAG – Final Project Backend

**SmartHealth RAG** is a backend system that enables intelligent clinical queries using the **RAG (Retrieval-Augmented Generation)** pattern.  
The project combines real clinical data stored in PostgreSQL with vector searches powered by **pgvector**, integrating a Large Language Model (LLM) to generate responses strictly based on the information available in the database.

It includes JWT authentication, full auditing, a main endpoint for clinical queries, and WebSocket support for real-time responses. This backend is also designed to connect to a **basic chat-style frontend**, developed as part of the same project.

---

## 🧠 General Description

The system allows an authenticated user to query clinical information about a patient by sending the document type, document number, and a question.  
The backend handles:

- Retrieving clinical data from PostgreSQL  
- Performing semantic search with embeddings and pgvector  
- Building the context sent to the LLM  
- Generating a response in strict JSON format  
- Logging each query in the audit system  

The goal is to provide accurate, traceable, and data-driven answers based exclusively on existing records.

---

## 🏛 System Architecture

The project is built with:

- **FastAPI** as the main backend framework  
- **PostgreSQL** + **pgvector** for storage and vector search  
- **JWT** for authentication  
- **WebSocket** for token-by-token communication  
- **LLM** (local or via API) for response generation  

### Simplified flow:
1. User logs in  
2. Sends a clinical query  
3. Backend retrieves data + performs similarity search  
4. Context is generated and processed by the LLL  
5. Response is logged and sent back to the client  

---

## 🗂 Data & Auditing

- **users:** Stores system account information  
- **audit_logs:** Records each query, including session, question, and generated response  

This design ensures full traceability and control of system operations.

---

## 🔌 Main Endpoints

- **POST /auth/register** – User registration  
- **POST /auth/login** – JWT authentication  
- **POST /query** – Full RAG workflow and JSON response  
- **WS /ws/chat** – Real-time responses via WebSocket  

---

## 🎨 Frontend Integration

The backend is designed to connect with a **chat-style frontend**, which is part of the project.  
This frontend will support:

- User login  
- Sending clinical queries  
- Displaying responses in a chat interface  
- WebSocket communication for real-time streaming  

---

## 🧩 Main Components

- Secure JWT Authentication  
- RAG Engine (SQL query + vector search + LLM)  
- Full auditing system  
- Real-time streaming  
- Structured clinical database  

---

## 📎 Resources & Documentation

The project references official documentation on RAG, embeddings, PostgreSQL, pgvector, and modern API architecture.

---

## 👥 Team

Project developed for SmartHealth – 2025-2.