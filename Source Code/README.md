# Research Grant Management System – Agentic AI

An enterprise-grade, autonomous **Research Grant Management System** powered by specialized AI agents, developed according to the 14-Week Agentic AI Systems Lab Curriculum.

---

## 🏛️ Project Overview

The Research Grant Management System orchestrates the complete lifecycle of research grant discovery, literature synthesis, proposal drafting, fiscal budget planning, compliance auditing, and governance-gated submission.

The platform provides a dual-mode engine:
1. **Live LLM Execution:** Leverages OpenAI GPT-4o when `OPENAI_API_KEY` is present.
2. **Offline Domain Heuristics:** High-fidelity fallback engine with domain-specific engineering rules, guaranteeing 100% functionality without external API lock-in.

---

## 🤖 6 Specialized AI Agents

| Agent | Responsibility | Core Technology |
|---|---|---|
| **1. Funding Discovery Agent** | Discovers, scores, and ranks funding opportunities matching faculty profiles | SQL database filtering & similarity scoring |
| **2. Literature Review Agent** | Ingests PDF research papers, synthesizes evidence, and detects research gaps | RAG, 4-tier source quality weighting, contradiction detection |
| **3. Proposal Drafting Agent** | Authors structured NSF/DoD-compliant proposals (Abstract, Methodology, Specific Aims) | Modular skill execution & Markdown export |
| **4. Budget Planning Agent** | Builds line-item budgets, calculates institutional F&A indirect overhead, and generates justifications | Parametric calculation & category threshold limits |
| **5. Compliance Checking Agent** | Audits proposals against solicitation caps, mandatory file lists, ITAR, and IRB ethics rules | Multi-rule verification matrix & automated scoring |
| **6. Submission Agent** | Assembles final submission bundle and enforces strict human-in-the-loop sign-off | Human-gated governance & agency portal simulation |

---

## 🎓 14-Week Agentic AI Systems Implementation

Every single week of the curriculum is implemented as an independent, fully testable, and demonstrable module:

- **Week 1:** Agent vs Chatbot (Goal → Plan → Act → Observe → Revise loop; 2 feedback rounds & resource conflict detection)
- **Week 2:** Tool-Using Agent (Structured tool calling, schema validation, notification drafting, and multi-tool chaining)
- **Week 3:** Skill Creation (Reusable capability packages, competing multi-claim synthesis, and low-evidence rejection)
- **Week 4:** Memory and Retrieval (Multi-session persistent context, scoped namespaces, and staleness/TTL policies)
- **Week 5:** MCP-Style Connector (Discoverable tool integration server, directory sandboxing, and read-only DB protections)
- **Week 6:** OpenClaw-Style Agent Runtime (6-layer architecture, per-user rate limiting, and failure escalation)
- **Week 7:** Agentic Node Graph (Declared contracts, routing, ITAR security scan node, and retry thresholds)
- **Week 8:** Parallel Swarm (Concurrent multi-agent swarm, 5th Ethics Specialist role, and conflict resolution)
- **Week 9:** Deep Research Agent (RAG pipeline, PDF chunking, source-quality tier weighting, and contradiction comparison)
- **Week 10:** Cloud Operations Agent (Observe → Diagnose → Remediate, DB pool exhaustion, and severity alarm gates)
- **Week 11:** Agentic SDLC Factory (Automated feature lifecycle from user story to release with deliberate bug verification)
- **Week 12:** Safety, Evaluation & Governance (Least-privilege security, approval gates, cost thresholds, and re-evaluation triggers)
- **Week 13:** Discipline-Specific Engineering Agents (Cross-domain adaptation for CS, EE, ME, CE with trend-based escalation)
- **Week 14:** Final Capstone Studio (Full end-to-end integration of all 13 modules into the unified grant management platform)

---

## 🛠️ Technology Stack

- **Backend:** Python 3.14, FastAPI, SQLAlchemy, SQLite, Pydantic, PyMuPDF / pypdf, Pytest
- **Frontend:** React 18, Vite, TypeScript, Tailwind CSS (Navy Blue Enterprise Theme), Recharts, React Flow, Lucide Icons
- **AI / LLM:** Dual-mode service (OpenAI API or Offline Heuristics Engine)
- **Architecture:** Micro-service / modular architecture with decoupled API, agent, memory, tool, skill, and workflow layers

---

## 🚀 Quickstart & Setup Guide

### 1. Prerequisites
- Python 3.10+
- Node.js 18+ and npm

### 2. Backend Setup
```bash
cd backend

# Create and activate a virtual environment (optional but recommended)
python -m venv venv
# On Windows:
.\venv\Scripts\activate
# On Linux/macOS:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Configure environment variables (optional for real LLM mode)
cp .env.example .env
# Edit .env to add your OPENAI_API_KEY if desired

# Run all 30 automated tests
pytest -v

# Start the FastAPI backend server
uvicorn main:app --reload --host 127.0.0.1 --port 8000
```
Backend API will be available at: `http://127.0.0.1:8000`  
Interactive Swagger Docs: `http://127.0.0.1:8000/docs`

### 3. Frontend Setup
```bash
cd frontend

# Install packages
npm install

# Build for production
npm run build

# Start the Vite development server
npm run dev
```
Frontend will be available at: `http://localhost:5173`

---

## 🧪 Automated Test Verification

All 30 unit, lab, and end-to-end integration tests pass:
```bash
cd backend
pytest -v
```
Result: `30 passed in 2.16s` (2 tests per lab week + 2 full end-to-end integration tests).

---

## 🔒 Governance & Ethical Guardrails

- **Zero Hardcoded Keys:** All credentials are loaded from environment variables.
- **Strict Human-in-the-Loop:** Antigravity Governance Rule 12-B strictly restricts final grant dispatch without verified faculty PI credentials and electronic signature.
- **Sandboxed File Operations:** Path traversal protection and read-only query enforcement on MCP connectors.
