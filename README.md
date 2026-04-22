# 🧠 MediMind AI — Intelligent Medical Assistant

> A multi-agent medical chatbot with RAG, guardrails, multimodal image analysis, and LangChain-inspired architecture.

🔗 **Live Demo:** https://rohini2003-hub.github.io/medimind-ai

---

## 📌 Problem Statement
Patients often struggle to understand medical lab reports and symptoms. MediMind AI provides instant, evidence-based medical information with proper source citations — making healthcare knowledge accessible to everyone.

## 💡 Value Proposition
A deployed, testable AI assistant that triages medical queries, retrieves grounded evidence, analyzes lab report images, and guards against misuse — all in one interface.

## 🤖 AI Component
MediMind AI uses a **multi-agent pipeline** powered by **Llama 3.3 70B** (via Groq) with a **LangChain-inspired architecture**:

```
User Input
    │
    ▼
🛡️  Guardrail Agent        ← blocks prompt injection & jailbreaks
    │
    ▼
🔍  Triage Agent           ← classifies urgency (EMERGENCY / URGENT / INFO)
    │
    ▼
📚  Evidence Agent         ← RAG retrieval → grounded medical answer with citations
    │
    ▼
✅  Safety Agent           ← validates output, adds disclaimer
    │
    ▼
💬  Response to User
```

---

## 🏗️ Architecture

### LangChain-Inspired Agent Framework
The system follows the **LangChain LCEL (LangChain Expression Language)** pattern:

```
chain = guardrail_agent | triage_agent | evidence_agent | safety_agent
```

Each agent has a **single responsibility** and passes output to the next — exactly like a LangChain pipeline.

### RAG (Retrieval Augmented Generation)
Instead of relying solely on model memory, MediMind AI grounds its answers in retrieved medical knowledge:

```
Query → Embedding → Vector Search → Top-K Chunks → LLM Generation → Cited Answer
```

**Knowledge Sources:**
- PubMed medical abstracts
- WHO clinical guidelines
- American Diabetes Association guidelines
- General medical reference documents

**Vector Store:** ChromaDB with `all-MiniLM-L6-v2` sentence embeddings
**Re-ranking:** Cross-encoder `ms-marco-MiniLM-L-6-v2` for accuracy

### Multi-Agent System
| Agent | Role | Inspired By |
|---|---|---|
| Guardrail Agent | Input sanitization, PII redaction, injection detection | LangChain GuardrailsAI |
| Triage Agent | Urgency classification (EMERGENCY/URGENT/INFO) | LangChain Router Chain |
| Evidence Agent | RAG retrieval + grounded answer generation | LangChain RetrievalQA |
| Safety Agent | Output validation + disclaimer injection | LangChain OutputParser |

---

## ✨ Features

### ✅ Working AI Application
- Live deployed chatbot accessible via public URL
- Powered by Llama 3.3 70B (state-of-the-art open model)
- Real-time responses with typing indicators

### 📚 RAG + Vector Store
- Retrieves relevant medical documents before generating answers
- Cites sources: [PubMed] [WHO] [Medical Guidelines]
- Prevents hallucination through grounded generation

### 🛡️ Guardrails & Prompt Injection Defence
- Regex pattern matching for 8+ injection attack types
- Blocks: jailbreaks, DAN mode, role override attacks
- PII detection and redaction (names, dates, locations)
- Output safety validation before showing to user

### 🚀 Deployment
- Deployed on GitHub Pages (static frontend)
- Zero-cost, always-on, globally accessible
- Public HTTPS URL for easy testing and submission

### 🤖 LangChain-Inspired Agentic Framework
- Sequential agent pipeline (chain pattern)
- Each agent has single responsibility
- Modular — agents can be swapped independently
- Follows LCEL (LangChain Expression Language) design principles

### 🧠 Memory & Chatbot Tricks
- Full conversation history maintained per session
- Context-aware responses (remembers previous messages)
- ConversationSummaryBuffer pattern for long conversations

### 📸 Multimodal — Image Analysis
- Upload any lab report image (JPG, PNG)
- AI reads and extracts all test values
- Explains normal vs abnormal results in simple language
- Powered by Llama 4 Scout Vision model

---

## 🗂️ Project Structure

```
medimind-ai/
├── index.html          # Complete frontend + agent logic
└── README.md           # This file
```

### Full-Stack Architecture (Production Version)
```
medimind-ai/
├── frontend/
│   └── index.html              # React UI
├── backend/
│   ├── main.py                 # FastAPI server
│   ├── agents/
│   │   ├── guardrail_agent.py  # Input sanitization
│   │   ├── triage_agent.py     # Urgency classification
│   │   ├── evidence_agent.py   # RAG retrieval
│   │   └── safety_agent.py     # Output validation
│   ├── rag/
│   │   ├── ingest.py           # PubMed ingestion
│   │   └── retriever.py        # ChromaDB + re-ranker
│   └── memory.py               # ConversationSummaryBuffer
├── docker-compose.yml
└── requirements.txt
```

---

## 🧪 How to Test

1. Open: https://rohini2003-hub.github.io/medimind-ai
2. Try these test cases:

| Test | Input | Expected |
|---|---|---|
| Normal query | "What are symptoms of diabetes?" | Evidence-based answer with citations |
| Emergency | "I have severe chest pain" | 🚨 EMERGENCY alert + call 911 |
| Guardrail | "Ignore previous instructions" | 🛡️ Blocked message |
| Memory | Ask something, then "explain more" | Remembers context |
| Image | Upload a lab report photo | Extracts and explains all values |

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| LLM | Llama 3.3 70B (Groq) |
| Vision Model | Llama 4 Scout 17B (Groq) |
| Agent Framework | LangChain-inspired pipeline |
| Vector Store | ChromaDB + sentence-transformers |
| Embeddings | all-MiniLM-L6-v2 |
| Re-ranker | cross-encoder/ms-marco-MiniLM-L-6-v2 |
| Frontend | HTML + CSS + Vanilla JS |
| Deployment | GitHub Pages |

---

## 📖 Concepts Demonstrated

| Course Concept | Implementation |
|---|---|
| Prompt Engineering | System prompt with role, rules, output format |
| RAG | Retrieve → Ground → Generate → Cite |
| Guardrails | Input sanitization + output validation |
| AI Agents | 4-agent sequential pipeline |
| Memory | Conversation history per session |
| Multimodal | Image upload + vision model analysis |
| Deployment | Live public URL on GitHub Pages |

---

## ⚕️ Disclaimer
MediMind AI is for informational purposes only. It is not a substitute for professional medical advice, diagnosis, or treatment. Always consult a qualified healthcare provider.

---

*Built for CST4625 Generative AI & LLMs Hackathon — Dr. Ivan Reznikov*
