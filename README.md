# Support Desk AI Assistant

An AI-powered support assistant that helps customer support teams automatically
classify ticket urgency, retrieve relevant FAQ information, and decide the
appropriate action for each support ticket.

The system combines Machine Learning, Retrieval-Augmented Generation (RAG),
a lightweight agentic workflow, and a FastAPI application.

---

## 1. Problem Statement

Customer support teams receive many support tickets that must be manually
read, prioritized, and answered.

Low-priority questions and urgent incidents often enter the same queue.
Support agents also spend significant time answering questions that are
already covered in FAQ or help documentation.

This can increase response time and reduce support team efficiency.

## 2. Proposed Solution

Support Desk AI Assistant provides an intelligent workflow that:

1. Receives a support ticket.
2. Predicts its urgency as Low, Medium, or High.
3. Detects whether the ticket is a question.
4. Searches the FAQ knowledge base when appropriate.
5. Retrieves relevant information using RAG.
6. Uses a lightweight agent to decide the next action.
7. Returns a structured response to the user.

### Expected Benefits

- Faster ticket triage
- Automatic handling of common FAQ questions
- Faster identification of urgent tickets
- Reduced repetitive work for support agents
- Consistent support workflow

---

## 3. System Architecture

```text
                    ┌─────────────────────┐
                    │      User/Ticket    │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │     FastAPI API     │
                    │     app/main.py     │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Support Agent     │
                    │     agent.py        │
                    └───────┬───────┬─────┘
                            │       │
                 ┌──────────┘       └──────────┐
                 ▼                             ▼
       ┌──────────────────┐          ┌──────────────────┐
       │ ML Classifier    │          │   RAG Retriever  │
       │ TF-IDF +         │          │ TF-IDF +         │
       │ Logistic         │          │ Cosine           │
       │ Regression       │          │ Similarity       │
       └────────┬─────────┘          └────────┬─────────┘
                │                             │
                ▼                             ▼
       ┌──────────────────┐          ┌──────────────────┐
       │ Urgency          │          │ FAQ Knowledge    │
       │ Prediction       │          │ Base             │
       └────────┬─────────┘          └────────┬─────────┘
                │                             │
                └──────────────┬──────────────┘
                               ▼
                    ┌─────────────────────┐
                    │ Agent Decision      │
                    │ & Final Response    │
                    └─────────────────────┘
