# 🤖 Support Desk AI Assistant

An AI-powered support ticket system that analyzes tickets, predicts urgency, retrieves relevant FAQ information, and recommends the next support action.

## 🚀 Features

* 🎫 Support ticket analysis
* 🧠 ML-based urgency prediction
* 📚 RAG-based FAQ retrieval
* 🤖 AI agent decision-making
* ⚡ FastAPI backend
* 🌐 Web interface
* 🐳 Docker support

## 🛠️ Tech Stack

**Python • FastAPI • Scikit-learn • Pandas • RAG • TF-IDF • Logistic Regression • Docker**

## ▶️ Run Locally

```bash
git clone https://github.com/YOUR_USERNAME/support-desk-ai.git
cd support-desk-ai
pip install -r requirements.txt
uvicorn app.main:app --reload
```

Open:

```text
http://localhost:8000
```

API Documentation:

```text
http://localhost:8000/docs
```

## 📊 Result & Output

The system successfully:

* Predicts ticket urgency as **Low, Medium, or High**
* Retrieves relevant answers from the FAQ knowledge base
* Automatically answers matching FAQ questions
* Escalates tickets when no relevant knowledge is found
* Provides API responses through FastAPI
* Displays ticket analysis through the web interface

### Example Output

```text
Ticket: Password reset email not received

Urgency: Medium
FAQ Match: Found
Action: Auto Answered from FAQ
```

## 🎯 Objective

To automate customer support workflows using **Machine Learning, RAG, and Agentic AI**, reducing manual effort and improving ticket prioritization.

