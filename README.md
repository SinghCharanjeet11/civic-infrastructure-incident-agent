# 🏙️ Civic Infrastructure Incident Response Agent

> **An AI-powered agent that automatically triages civic service incidents — saving operators time, reducing noise, and delivering explainable, evidence-based decisions.**

Built with **Elasticsearch Agent Builder** · Powered by **ES|QL** · Designed for real-world civic operations

---

## 🚀 Demo

> The agent receives raw operational logs from civic services (e.g., water supply systems), reasons over them in multiple steps, and delivers a structured incident report with severity classification and a recommended action — all without human intervention.

---

## 🧩 The Problem

City infrastructure teams manage critical services around the clock. Every day, they wade through thousands of logs from water systems, power grids, and sanitation services to find what actually matters.

**The current reality:**
- ❌ Manual log triage is slow and error-prone
- ❌ Rule-based alerting floods operators with false positives
- ❌ Static thresholds don't adapt to context or time-of-day patterns
- ❌ Escalation decisions are inconsistent across shifts and operators

**The cost:** Delayed responses to real incidents, alert fatigue, and reduced operator trust in automated systems.

---

## 💡 Our Solution

We built a **context-driven, multi-step AI agent** using **Elasticsearch Agent Builder** that reasons over civic service logs like an experienced human operator — retrieving evidence, detecting patterns, and making explainable decisions.

No hardcoded thresholds. No black-box outputs. Just structured, transparent reasoning grounded in real data.

---

## 🔄 How It Works

The agent executes a structured **4-step reasoning workflow** on every query:

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│  1. CONTEXT RETRIEVAL                                           │
│     Elasticsearch Search → fetch logs by service, location,     │
│     and time window                                             │
│                                                                 │
│  2. PATTERN ANALYSIS                                            │
│     ES|QL → detect repeated errors, abnormal response times,    │
│     and time-based anomalies                                    │
│                                                                 │
│  3. SEVERITY CLASSIFICATION                                     │
│     Agent reasoning → assign Low / Medium / High / Critical     │
│     based on evidence, not static rules                         │
│                                                                 │
│  4. ACTION RECOMMENDATION                                       │
│     → Monitor only                                              │
│     → Investigate within 24 hours                               │
│     → Escalate immediately                                      │
│        (with a clear explanation for each decision)             │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

| Technology | Role |
|---|---|
| **Elasticsearch Agent Builder** | Orchestrates the multi-step agentic workflow |
| **Elasticsearch Search** | Retrieves relevant civic service logs |
| **ES|QL** | Performs expressive, time-aware log analytics |

> ✅ The entire agent runs within the Elasticsearch ecosystem — no external backend services required.

---

## ✨ Key Features

- **🔍 Intelligent Log Retrieval** — Filters logs by service type, location, and time range for focused analysis
- **📊 Pattern-Aware Analytics** — Uses ES|QL to detect trends a simple search would miss
- **🎯 Evidence-Based Severity** — Classifies incidents on a 4-level scale grounded in retrieved data
- **📋 Explainable Recommendations** — Every action recommendation includes a plain-language justification
- **🚫 No False Escalation** — The agent explains *why* it chose not to escalate when the evidence doesn't support it

---

## 📈 Impact

| Before | After |
|---|---|
| Manual log review taking hours | Instant structured incident report |
| Inconsistent escalation decisions | Standardized, evidence-based recommendations |
| Alert fatigue from false positives | Context-aware filtering reduces noise |
| Opaque automated decisions | Fully explained reasoning operators can trust |

---

## 🏗️ Architecture

```
Operator Query
      │
      ▼
┌─────────────────────┐
│  Elasticsearch      │
│  Agent Builder      │
│                     │
│  ┌───────────────┐  │
│  │Elasticsearch  │  │──► Log Retrieval
│  │    Search     │  │
│  └───────────────┘  │
│                     │
│  ┌───────────────┐  │
│  │    ES|QL      │  │──► Pattern Analysis
│  │   Analytics   │  │
│  └───────────────┘  │
│                     │
│  ┌───────────────┐  │
│  │  Agent LLM    │  │──► Severity + Action
│  │   Reasoning   │  │
│  └───────────────┘  │
└─────────────────────┘
      │
      ▼
Structured Incident Report
(Severity + Recommendation + Explanation)
```

---

## 🧠 Design Decisions

### Why Agent Builder over a simple RAG pipeline?
RAG retrieves and generates. Our agent **retrieves, queries, reasons, and decides** — a fundamentally different pattern suited for operational decision support.

### Why ES|QL over keyword search alone?
ES|QL allows us to express time-windowed aggregations and anomaly detection logic directly in the query layer — critical for identifying patterns in operational data.

### Why explainability matters here?
Civic infrastructure operators must trust and verify automated decisions. Every recommendation includes a clear rationale, including why more extreme actions were *not* taken.

---

## ⚡ Challenges We Overcame

- **Prompt engineering for balanced judgment** — Designing instructions so the agent is decisive but not reckless required multiple iterations
- **Grounding recommendations in evidence** — Preventing hallucinated justifications by anchoring reasoning to retrieved log data
- **Operator-friendly language** — Translating complex log patterns into clear, actionable language for non-technical operators

---

## 🔮 Future Work

- [ ] Real-time streaming ingestion from live civic sensors
- [ ] Historical incident learning to refine severity thresholds over time  
- [ ] Multi-service correlation (e.g., linking water pressure drops to pump failures)
- [ ] Operator feedback loop to improve recommendation quality

---

## 📄 License

This project is released under the [MIT License](LICENSE).

---

## 👥 Team

Built for the **Elasticsearch Agent Builder Hackathon**

---

*"The best incident is the one you catch before it becomes a crisis."*
