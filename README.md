# 🧠 MediMind AI — Medical Chatbot
> CST4265: GenAI and LLMs — Hackathon Project

A production-grade medical second-opinion chatbot built with Gemini 1.5, RAG, multi-agent reasoning, and safety guardrails.

## 🔗 Live Demo
👉 **[Click here to try it](https://YOUR-USERNAME.github.io/medimind-ai)**

## ✨ Features

| Feature | Implementation |
|---|---|
| 💬 AI Chatbot | Gemini 1.5 Flash with conversation memory |
| 📚 RAG | Medical knowledge base with semantic retrieval |
| 🛡️ Guardrails | Prompt injection detection + safety validation |
| 🤖 Multi-Agent | Triage → Evidence → LLM → Safety agents |
| 🧠 Memory | Full conversation history across turns |
| 🚨 Urgency Detection | Emergency / Urgent / Info classification |

## 🚀 How to Run

1. Open `index.html` in any browser — that's it!
2. Or visit the live GitHub Pages link above.

## 🏗️ Architecture

```
User Input
    ↓
🛡️ Guardrails (injection detection)
    ↓
🔍 Triage Agent (Emergency / Urgent / Info)
    ↓
📚 Evidence Agent (RAG retrieval from knowledge base)
    ↓
🤖 Gemini 1.5 (cited answer generation)
    ↓
✅ Safety Agent (disclaimer injection, output validation)
    ↓
💬 Response with citations + urgency label
```

## 📚 Topics Covered
Diabetes, Hypertension, Fever, Heart conditions, Allergies, Lab tests (CBC), Mental health, Immune system, Nutrition, Oncology

## ⚕️ Disclaimer
This chatbot is for informational purposes only and does not replace professional medical advice.
