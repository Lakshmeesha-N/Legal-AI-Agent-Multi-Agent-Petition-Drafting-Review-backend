# Opandz AI — Backend

Production backend for **Opandz AI**, a LangGraph-based multi-agent platform for automated legal document drafting, layout/style extraction, and cross-document review. Built and maintained solo, from architecture through deployment.

Currently serving 15+ beta users across legal and professional domains.

---

## What it does

Opandz AI ingests source documents, extracts layout and style rules, and generates production-ready output (DOCX/PDF) through a coordinated pipeline of specialized agents. Core capabilities:

- **Document extraction** — parses layout, formatting, and structural rules from uploaded documents
- **Automated drafting** — generates legal petitions and structured documents based on extracted rules and user input
- **Clause-level review** — specialized agents review generated content at the clause level
- **Cross-document consistency checks** — validates new drafts against prior documents for consistency
- **Multi-step reasoning** — LangGraph state graphs manage multi-agent orchestration and tool invocation across the full drafting workflow

## Architecture

- **Orchestration:** LangGraph (state graphs, multi-agent coordination, tool calling)
- **Backend:** FastAPI (async)
- **Storage:** Google Cloud Storage, Firestore
- **Deployment:** Google Cloud Run
- **CI/CD:** Automated deployment on every push to main

```
Client
  │
  ▼
FastAPI (async)
  │
  ▼
LangGraph Multi-Agent Orchestrator
  ├── Extraction Agent   → parses layout/style rules from source docs
  ├── Drafting Agent      → generates document content
  ├── Review Agent        → clause-level review
  └── Consistency Agent   → cross-checks against prior documents
  │
  ▼
Output: DOCX / PDF
  │
  ▼
Google Cloud Storage / Firestore
```

## Tech Stack

| Layer | Technology |
|---|---|
| Agent orchestration | LangGraph, LangChain |
| API | FastAPI (async) |
| Cloud infrastructure | Google Cloud Run, Cloud Storage, Firestore |
| CI/CD | Automated pipeline, deploy-on-push |
| Language | Python |

## Status

Actively developed. Solo-owned end-to-end — architecture, agent design, deployment, and infrastructure.

## Getting Started

> Update this section with actual setup steps once finalized.

```bash
git clone https://github.com/Lakshmeesha-N/Opandz-ai-backend.git
cd Opandz-ai-backend
pip install -r requirements.txt
```

Set required environment variables (GCP credentials, API keys) in a `.env` file, then run:

```bash
uvicorn main:app --reload
```

## Roadmap

- [ ] Expand agent specialization for additional document types
- [ ] Add evaluation harness for drafting/review accuracy
- [ ] Public API documentation

---

**Author:** Lakshmeesha N — [GitHub](https://github.com/Lakshmeesha-N) · [LinkedIn](https://linkedin.com/in/lakshmeesha--n)
