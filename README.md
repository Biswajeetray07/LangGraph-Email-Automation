# 🚀 LangGraph Email Automation

A powerful system built with **LangGraph**, **LangChain**, and **RAG** (Retrieval-Augmented Generation) to automate and enhance customer support email handling.

## 📩 Overview

This system leverages multiple specialized AI agents working in a coordinated workflow to:
- **Monitor** a Gmail inbox for new customer inquiries.
- **Categorize** incoming emails (e.g., Complaints, Inquiries, Feedback).
- **Retrieve** relevant business information via RAG to provide accurate answers.
- **Draft** personalized, high-quality responses.
- **Verify** email quality and formatting before sending.

## ✨ Features

### 🤖 Intelligent Email Handling
- **Automated Categorization**: Sorts emails into 'customer complaint', 'product inquiry', 'customer feedback', or 'unrelated'.
- **Smart Filtering**: Automatically handles irrelevant noise to keep the support queue clean.

### 📚 Knowledge-Enriched Responses
- **RAG Integration**: Uses a vector database (ChromaDB) to answer technical or product-specific questions using your own data.
- **Dynamic Drafting**: Tailors response tone and content based on the email category and retrieved context.

### ✅ Quality Assurance
- **AI Proofreader**: Ensures every message meets professional standards, follows formatting rules, and addresses the customer's core needs.

## 🛠️ Tech Stack

- **Orchestration**: LangChain & LangGraph
- **LLMs**: Groq (Llama 3) & Google Gemini
- **Database**: ChromaDB (Vector Store)
- **APIs**: Google Gmail API, FastAPI (via LangServe)

## 🚀 Getting Started

### Prerequisites
- Python 3.9+
- Groq API Key
- Google Gemini API Key (for embeddings)
- Gmail API Credentials (`credentials.json`)

### Installation & Setup

1. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

2. **Configure Environment:**
   Create a `.env` file in the root directory:
   ```env
   MY_EMAIL=your_email@gmail.com
   GROQ_API_KEY=your_groq_api_key
   GOOGLE_API_KEY=your_gemini_api_key
   ```

3. **Enable Gmail API:**
   Follow [this guide](https://developers.google.com/gmail/api/quickstart/python) to enable the Gmail API and download `credentials.json` to the project root.

### Usage

- **Run the Workflow**: `python main.py`
- **Deploy as API**: `python deploy_api.py`
- **Build Vector Store**: Add your documents to `data/` and run `python create_index.py`.

## ⚙️ Customization

- **Prompts**: Modify agent behavior in `src/prompts.py`.
- **Graph Logic**: Adjust the workflow state and nodes in `src/graph.py` and `src/nodes.py`.
- **Knowledge Base**: Update `./data/agency.txt` with your business details and re-run the indexer.
