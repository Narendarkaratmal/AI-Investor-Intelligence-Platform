# 🚀 AI-Powered Investor Intelligence Platform

<img width="1044" height="691" alt="image" src="https://github.com/user-attachments/assets/b4ea5285-e0e2-4f2b-9b7a-0dd131ccaf4d" />


## 📌 Overview

The **AI-Powered Investor Intelligence Platform** is an AI-driven financial analysis system designed to transform company annual reports into structured and actionable investor insights.

The platform combines **document processing, semantic search, Retrieval-Augmented Generation (RAG), Azure OpenAI, Azure AI Search, and PostgreSQL** to help users analyze financial reports and interact with company data through natural-language queries.

Instead of manually reading lengthy annual reports, users can upload financial documents and ask questions about revenue, profitability, financial performance, growth drivers, and risk factors.

---

## ✨ Key Features

### 📄 Annual Report Processing

* Upload company annual reports in PDF format.
* Extract and clean text from financial documents.
* Convert documents into structured text.
* Perform semantic chunking for efficient retrieval.

### 🤖 AI-Powered KPI Extraction

Extract important financial metrics using Azure OpenAI, including:

* Revenue
* Net Income
* Operating Income
* Operating Cash Flow
* Total Assets
* Total Liabilities
* Other financial KPIs

### 🔎 Semantic Search

Uses **Azure AI Search** to retrieve the most relevant sections of annual reports based on the user's query.

This enables contextual search instead of relying only on exact keyword matching.

### 🧠 RAG-Based Investor Chatbot

The platform uses **Retrieval-Augmented Generation** to answer financial questions using information retrieved from company reports.

Example:

```text
User:
"What were Apple's major growth drivers in 2024?"

        ↓

Semantic Search

        ↓

Relevant Annual Report Sections

        ↓

Azure OpenAI

        ↓

Context-Aware Investor Insight
```

### 📊 Investor Dashboard

The dashboard provides a visual overview of company performance, including:

* Revenue
* Net Income
* Operating Income
* Operating Cash Flow
* Total Assets
* Total Liabilities
* Growth Drivers
* Risk Factors
* AI-generated financial insights

### 💾 Financial Data Storage

Extracted financial KPIs are stored in **PostgreSQL**, allowing structured financial data to be maintained and queried efficiently.

---

# 🏗️ System Architecture

```text
                         ┌─────────────────────┐
                         │     Investor/User    │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │  Investor Dashboard │
                         │      AI Chatbot     │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │       FastAPI       │
                         │       Backend       │
                         └──────────┬──────────┘
                                    │
                  ┌─────────────────┼─────────────────┐
                  │                 │                 │
                  ▼                 ▼                 ▼
          ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
          │     RAG      │  │ KPI Extractor│  │  PostgreSQL  │
          │   Pipeline   │  │              │  │   Database   │
          └──────┬───────┘  └──────┬───────┘  └──────────────┘
                 │                 │
                 ▼                 ▼
          ┌──────────────┐  ┌──────────────┐
          │ Azure AI     │  │ Azure        │
          │ Search       │  │ OpenAI       │
          └──────────────┘  └──────────────┘
```

---

# 🔄 Data Processing Pipeline

```text
Annual Report PDF
       │
       ▼
PDF Text Extraction
       │
       ▼
Text Cleaning
       │
       ▼
Semantic Chunking
       │
       ▼
Azure AI Search Index
       │
       ├───────────────► KPI Extraction
       │                       │
       │                       ▼
       │                  PostgreSQL
       │
       ▼
User Question
       │
       ▼
Semantic Retrieval
       │
       ▼
Relevant Context
       │
       ▼
Azure OpenAI
       │
       ▼
Investor Answer
```

---

# 🛠️ Technology Stack

## Backend

* Python 3.12+
* FastAPI
* Pydantic

## AI & RAG

* Azure OpenAI
* Retrieval-Augmented Generation
* Semantic Search
* LLM-based KPI extraction

## Search

* Azure AI Search

## Database

* PostgreSQL

## Document Processing

* PDF processing
* Text extraction
* Semantic chunking

## Frontend

* HTML
* CSS
* JavaScript

## DevOps & Cloud

* Docker
* Azure Container Registry
* Kubernetes
* Azure Kubernetes Service

## Package Management

* UV

---

# 📁 Project Structure

```text
AI-Investor-Intelligence-Platform/
│
├── .github/
│   └── workflows/
│       └── deploy.yaml
│
├── config/
│   └── settings.yaml
│
├── data/
│   ├── markdown/
│   └── raw_pdfs/
│
├── database/
│   ├── create_table.py
│   ├── metrics.py
│   ├── postgres_sql.py
│   └── save_metrics.py
│
├── ingestion/
│   ├── ingest_documents.py
│   ├── pdf_to_markdown.py
│   └── semantic_chunker.py
│
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
│
├── llm/
│   └── azure_openai.py
│
├── rag/
│   ├── kpi_extractor_rag.py
│   └── retrieval_debug.py
│
├── routes/
│   ├── chat.py
│   ├── dashboard.py
│   ├── health.py
│   └── ingestion.py
│
├── static/
│   └── style.css
│
├── templates/
│   └── dashboard.html
│
├── vectorstore/
│   ├── azure_ai_search.py
│   └── create_index.py
│
├── app.py
├── main.py
├── dockerfile
├── requirements.txt
└── README.md
```

---

# ⚙️ Installation & Setup

## Prerequisites

Make sure the following are installed:

* Python 3.12+
* Git
* UV Package Manager
* Docker (optional)
* Azure account and required services

---

## 1. Install UV

### Windows

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### macOS / Linux

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Verify:

```bash
uv --version
```

---

## 2. Clone the Repository

```bash
git clone https://github.com/Narendarkaratmal/AI-Investor-Intelligence-Platform.git
```

```bash
cd AI-Investor-Intelligence-Platform
```

---

## 3. Create Virtual Environment

```bash
uv venv
```

### Windows

```powershell
.venv\Scripts\activate
```

### macOS / Linux

```bash
source .venv/bin/activate
```

---

## 4. Install Dependencies

```bash
uv pip install -r requirements.txt
```

---

# 🔐 Environment Variables

Create a `.env` file in the project root.

Example:

```env
AZURE_OPENAI_API_KEY=your-api-key
AZURE_OPENAI_ENDPOINT=your-endpoint
AZURE_OPENAI_API_VERSION=your-api-version
AZURE_OPENAI_CHAT_DEPLOYMENT=your-deployment

AZURE_SEARCH_ENDPOINT=your-search-endpoint
AZURE_SEARCH_API_KEY=your-search-key

POSTGRES_HOST=your-postgres-host
POSTGRES_DATABASE=your-database
POSTGRES_USERNAME=your-username
POSTGRES_PASSWORD=your-password
POSTGRES_PORT=5432
```

> ⚠️ **Never commit `.env` files, API keys, passwords, or other secrets to GitHub.**

For production deployments, use secure secret-management solutions such as Azure Key Vault or Kubernetes Secrets.

---

# ▶️ Running the Application

Start the application:

```bash
python app.py
```

Depending on the configured entry point, you can also run:

```bash
python main.py
```

The FastAPI application can then be accessed through the configured local server.

---

# 💬 Example Investor Queries

The AI assistant can be used for questions such as:

```text
What was Apple's revenue in 2024?
```

```text
What were the major growth drivers?
```

```text
What are the company's biggest financial risks?
```

```text
Compare revenue and net income.
```

```text
What changed significantly in the company's financial performance?
```

```text
Summarize the company's financial position.
```

---

# 🐳 Docker Deployment

Build the Docker image:

```bash
docker build -t investor-intelligence .
```

Run the container:

```bash
docker run -p 8000:8000 investor-intelligence
```

---

# ☁️ Cloud Deployment

The project is structured to support deployment using Microsoft Azure.

Deployment architecture:

```text
Application
     │
     ▼
Docker Image
     │
     ▼
Azure Container Registry
     │
     ▼
Azure Kubernetes Service
     │
     ▼
Running Application
```

Kubernetes configuration is available under:

```text
k8s/
```

CI/CD configuration:

```text
.github/workflows/deploy.yaml
```

---

# 📊 Sample Data

The project includes sample annual reports for:

* Apple
* Microsoft
* Tesla

These documents demonstrate the ingestion, retrieval, and KPI extraction pipeline.

---

# 🔒 Security Considerations

* Store API keys in environment variables.
* Never commit `.env` files.
* Avoid hard-coding database credentials.
* Use Azure Key Vault for production secrets.
* Configure appropriate Azure access policies.
* Secure PostgreSQL access using proper firewall and authentication settings.

---

# 🚀 Future Enhancements

Potential improvements include:

* 📈 Historical financial trend analysis
* 🏢 Multi-company comparison
* 📊 Portfolio-level analytics
* 🔮 Financial forecasting
* 📰 Automated financial news integration
* ⚠️ Advanced risk scoring
* 📑 Automatic annual-report ingestion
* 🔐 Authentication and user management
* 📚 Improved source citations for AI responses
* 📱 Responsive mobile dashboard

---

# 🎯 Learning Outcomes

This project demonstrates practical implementation of:

* Retrieval-Augmented Generation
* Large Language Models
* Semantic Search
* Financial Document Processing
* NLP-based KPI Extraction
* FastAPI backend development
* Azure AI services
* PostgreSQL
* Docker
* Kubernetes
* Cloud deployment
* Modular software architecture

---

# ⚠️ Disclaimer

This platform is intended for **educational and engineering purposes**.

AI-generated financial insights should not be considered professional investment or financial advice.

---

## 👨‍💻 Author

**Narendar Karatmal**
Computer Science & Engineering
NIT Warangal

---

⭐ If you find this project useful, consider starring the repository!
