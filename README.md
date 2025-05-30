# 🚀 SmartRAG

**SmartRAG** is a terminal-based Retrieval-Augmented Generation (RAG) system built using [LangGraph](https://github.com/langchain-ai/langgraph). It routes user queries through a custom flow that includes message history, query transformation, and document retrieval from a vector store.

> 🔗 GitHub: [https://github.com/aimaster-dev/SmartRAG](https://github.com/aimaster-dev/SmartRAG)

---

## 🧠 Features

* LangGraph-powered RAG pipeline
* Smart routing of user queries
* PDF and Markdown ingestion support
* Optional webpage-to-PDF and PDF-to-Markdown conversion
* OpenAI GPT integration for natural language responses

---

## 🗂️ Project Structure

```
SmartRAG/
├── architecture/         # LangGraph RAG workflow logic
├── data/                 # Processed markdown or PDF content
├── modules/              # Core logic for query handling & doc processing
├── main.py               # Entry point
└── processDocs.py        # Document preprocessing script
```

---

## ⚙️ Setup

Follow the steps below to get SmartRAG up and running:

### 1. Clone the Repo

```bash
git clone https://github.com/aimaster-dev/SmartRAG.git
cd SmartRAG
```

### 2. Create Virtual Environment

```bash
python3.12 -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
choco install wkhtmltopdf  # for HTML to PDF conversion (Windows only)
```

### 4. Environment Setup

Copy and edit the `.env` file:

```bash
cp .env.example .env
```

Edit `.env` to include:

```env
OPENAI_API_KEY=your_openai_key
URLS=url1,url2         # Optional: URLs to fetch as PDF
GET_WEB_PAGES_TO_PDF=True
CONVERT_PDF_TO_MD=True
INTERMEDIATE_PDF_DIR=./pdfs
DATA_DIR=./data
```

### 5. Process Your Documents

```bash
python modules/processDocs.py
```

> ⚠️ Make sure to update `.env` parameters based on your use case.

### 6. Run SmartRAG

```bash
python main.py
```

---

## 🔍 How It Works

1. **User query** is passed into a LangGraph workflow.
2. **Message history** is cached and contextually enriched.
3. If needed, input is transformed for better retrieval.
4. Documents are pulled from a **vector store** using similarity search.
5. GPT model generates a context-aware answer.

---

## 🖼️ Architecture Overview

### 📄 Vector Store Creation

![Vector DB](https://github.com/aimaster-dev/SmartRAG/blob/main/architecture/RAG.png)

### 🧠 RAG Pipeline

![RAG Flow](https://github.com/aimaster-dev/SmartRAG/blob/main/architecture/RAG.png)

---

## 🤝 Contributing

We welcome contributions!

* Fork the repo
* Create a feature branch
* Submit a pull request

> Got a big idea? Open an issue to discuss it first.

---

## 📬 Contact

For questions, feedback, or collaboration ideas — feel free to open an issue or reach out through GitHub!

---
