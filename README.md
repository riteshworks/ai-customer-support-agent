# AI Customer Support Agent

Autonomous AI customer support system built with **n8n**, **Gemma 4**, and **Shopify API**. The workflow reads incoming support emails, classifies customer intent, retrieves order information, checks shipment status, and generates personalised responses automatically.

---

## Overview

This project automates the complete first-line customer support workflow for a Shopify-based e-commerce business.

### Workflow

1. Reads new emails from Gmail.
2. Cleans HTML, signatures, forwarded content, and Shopify metadata.
3. Extracts order number, customer email, and phone number.
4. Classifies customer intent and sentiment using a self-hosted Gemma 4 LLM (30+ intents).
5. Retrieves order information from the Shopify API.
6. Fetches live shipment status from Shipway.
7. Generates personalised responses.
8. Logs all interactions to Google Sheets.
9. Removes Gmail labels to prevent duplicate processing.

---

## Results

| Metric | Value |
|--------|-------|
| Intent Classification Accuracy | **96%** |
| Initial Accuracy | 77% |
| Optimisation Iterations | 4 |
| Average Response Time | Seconds |
| Deployment | Self-hosted (Docker) |

---

## Technology Stack

| Component | Technology |
|----------|------------|
| Workflow Automation | n8n |
| Language Model | Gemma 4 (Ollama) |
| Email Integration | Gmail API |
| E-commerce | Shopify API |
| Shipment Tracking | Shipway |
| Logging | Google Sheets |
| Deployment | Docker |
| Database | PostgreSQL |
| Cache | n8n Static Data (23-hour TTL) |

---

## Engineering Challenges

| Challenge | Solution |
|-----------|----------|
| Misspelled customer requests (e.g. "cancer it") | Regex normalisation before intent detection |
| Shopify access token expiry | 23-hour token caching |
| Malformed Gmail Thread IDs | Input sanitisation |
| Inconsistent order number formats | Order ID normalisation |
| Duplicate customer replies | Intent override logic |
| Multiple orders in one email | Context-aware order detection |
| Legal escalation keywords | Automatic escalation flagging |

---

## Accuracy Progress

| Version | Accuracy |
|---------|---------:|
| v1 | 77% |
| v2 | 85% |
| v3 | 91% |
| **v4** | **96%** |

---

## Repository Structure

```text
.
├── Workflow.json
├── docker-compose.yml
├── credentials_template.env
└── llm_prompt.txt
```

---

## Key Features

- Autonomous customer support workflow
- Self-hosted LLM using Ollama
- 30+ customer intent classifications
- Automated order lookup
- Live shipment tracking
- Personalised AI-generated responses
- Google Sheets logging
- Token caching for Shopify authentication
- Production-tested workflow with iterative optimisation

---

## Future Improvements

- Retrieval-Augmented Generation (RAG) for policy lookup
- Multi-language support
- Customer memory and conversation history
- Analytics dashboard
- Human-in-the-loop review workflow
- Multi-store Shopify support
