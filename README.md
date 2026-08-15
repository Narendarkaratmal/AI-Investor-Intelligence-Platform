# 🚀 AI-Powered Investor Intelligence Platform

> An AI-powered financial intelligence platform that transforms company annual reports into actionable investor insights using **RAG, Azure OpenAI, Azure AI Search, and PostgreSQL**.

<img width="1906" height="945" alt="AI-Powered Investor Intelligence Platform Dashboard" src="https://github.com/user-attachments/assets/5024af81-e07e-47ed-a4ab-a40c439522f2" />

---

## 📌 Overview

The **AI-Powered Investor Intelligence Platform** helps investors analyze company annual reports without manually going through hundreds of pages of financial documents.

The platform allows users to:

- 📄 Upload and process company annual reports
- 🤖 Extract important financial KPIs using Azure OpenAI
- 🔎 Perform semantic search across financial documents
- 🧠 Ask natural-language questions using a RAG-based chatbot
- 📊 Analyze revenue, net income, operating income, assets, liabilities, and cash flow
- 📈 Identify business growth drivers and potential risk factors
- 💾 Store extracted financial metrics in PostgreSQL
- 🌐 Visualize insights through an interactive investor dashboard

---

## ✨ Key Features

### 📄 Annual Report Processing

Upload company annual reports in PDF format and automatically process their contents.

The document pipeline performs:

```text
PDF Upload
    ↓
Document Extraction
    ↓
Text Cleaning
    ↓
Semantic Chunking
    ↓
Search Indexing
