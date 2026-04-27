# Tran Hoang Soft

**Senior Software Engineer | AI-Powered Financial Systems**

Building production-grade intelligent platforms that combine real-time AI, financial data pipelines, and scalable cloud architecture.

---

### 🚀 Featured Project: **2winai**

Full-stack AI platform for financial market analysis, intelligent conversation, and automated risk & alert management.  
Supports **Web (Flask)** and **Mobile (React Native)** with a unified backend deployed on **Google Cloud Run**.

2winai is composed of **3 independent, self-contained systems** — each operates autonomously with no dependency on the others:

---

#### 🤖 System 1 — AI Chatbot Engine

A conversational AI interface for market queries and in-depth financial analysis.

- Natural language understanding with intent and entity recognition (Rasa NLU)
- **Two independent modes**, each with its own dedicated system prompt:
  - **Normal Chat** — General financial Q&A
  - **Expert Analysis** — Deep-dive queries with enriched live market context
- Security validation applied on all user inputs before processing
- Multi-LLM backend with primary/fallback strategy *(see LLM Strategy below)*

---

#### ⚠️ System 2 — Risk Analysis Engine

Automated, multi-dimensional risk assessment — runs independently, triggered on demand or via scheduled jobs.

- Analyzes multiple risk dimensions using LLM inference (API-based only — **no model training**)
- Background processing with real-time UI progress: each dimension result appears incrementally as it completes
- Designed to be modular; dimensions can be extended or reconfigured without affecting other systems

---

#### 🔔 System 3 — Alert & Watchlist Agent

Autonomous background agent for continuous market monitoring — fully decoupled from Systems 1 and 2.

- Monitors user watchlists on a scheduled basis
- Detects significant trend changes and signal anomalies using LLM inference (API-based only — **no model training**)
- Delivers timely notifications via **email** and **in-app alerts**
- Operates entirely in the background with no user interaction required

---

### 🧠 Multi-LLM Strategy

| Role | Models |
|---|---|
| **Primary** | One of: **Grok**, **Gemini**, or **ChatGPT** — selected based on reliability and performance |
| **Fallback** | The remaining models activate automatically when the primary is unavailable, slow, or degraded |
| **Extended** | **OpenRouter** used occasionally for additional model access |

- The caller (chat, risk, alert) always knows which model is active — fallback is explicit and logged, not hidden
- All LLMs are consumed via **API inference only — no fine-tuning, no training, no custom model development**

---

### 🏗️ Architecture Overview

```
┌──────────────────────────────────────────────────────────────┐
│                        2winai Platform                        │
│                (Google Cloud Run + Docker + CI/CD)            │
├───────────────────┬──────────────────┬───────────────────────┤
│   System 1        │   System 2       │   System 3            │
│   AI Chatbot      │   Risk Analysis  │   Alert & Watchlist   │
│   Engine          │   Engine         │   Agent               │
│                   │                  │                       │
│ • Rasa NLU        │ • Multi-dim      │ • Scheduled Agent     │
│ • Normal mode     │   Risk Scoring   │ • Trend Detection     │
│ • Expert mode     │ • Real-time      │ • Email + In-app      │
│ • System prompts  │   Progress UI    │   Notifications       │
│ • Input security  │ • Background     │ • Fully autonomous    │
│                   │   Processing     │                       │
└───────────────────┴──────────────────┴───────────────────────┘
          │                  │                   │
          └──────────────────┴───────────────────┘
                      (each system independent)
                             │
              ┌──────────────▼──────────────┐
              │       Multi-LLM Layer        │
              │  Primary: Grok / Gemini /    │
              │  ChatGPT  +  Fallback chain  │
              └──────────────┬──────────────┘
                             │
              ┌──────────────▼──────────────┐
              │   Financial Data APIs        │
              │   PostgreSQL (Cloud SQL)     │
              └─────────────────────────────┘
```

---

### 💼 Technical Expertise

- **Backend & Architecture**: Python, Flask, PostgreSQL, Background threading, Real-time streaming progress, Modular independent service design
- **AI Layer**: Rasa NLU, Multi-LLM orchestration, Prompt engineering, Dedicated system prompts per mode, Input security validation
- **Data & Integration**: Multiple financial market APIs, Real-time data enrichment pipelines
- **Cloud & DevOps**: Google Cloud Run, GitHub Actions CI/CD, Docker, Cloud SQL
- **Security & Scalability**: Google OAuth, JWT, Rate limiting, PayPal payment & subscription management, Usage quota enforcement

---

### 📈 Engineering Philosophy

I focus on **simplicity, reliability, and clear user value**.  
Each system is independently deployable and maintainable — observable in production, designed to fail gracefully, and built to deliver visible results step-by-step.

---

### 📫 Get in Touch

- Location: Vietnam
- Open to: Senior Software Engineer / AI Engineer / Full-Stack Fintech roles (remote or onsite)
- Email: tranhoangsoft@gmail.com

---

*Last updated: April 2026*

---

**"Crafting intelligent systems that deliver clear value — one reliable component at a time."**
