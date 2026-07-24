# 🤖 AI Customer Support Agent (n8n)

Autonomous AI customer support automation system built with n8n and self-hosted Gemma4 LLM. Reads emails, classifies intent, fetches orders, and replies automatically — 96% accuracy on real customer data.

---

## 📊 The Results

| Metric | Value |
|--------|-------|
| **Accuracy** | 96% (started at 77%) |
| **Iterations** | 4 test cycles |
| **Manual Support Reduced** | 3 agents → 0.5 agents |
| **Response Time** | Seconds (vs hours) |
| **Deployment** | Self-hosted (Docker) |

---

## 🧠 What It Does

1. Reads unprocessed emails from Gmail
2. Cleans HTML, forwarding chains, and Shopify metadata
3. Extracts: Order ID, Email, Phone Number
4. Classifies intent (30+ types) and tone using Gemma4 LLM
5. Fetches order data from Shopify API (23-hour token cache)
6. Scrapes live tracking status from Shipway
7. Builds personalized replies
8. Logs everything to Google Sheets
9. Removes Gmail label to prevent re-processing

---

## ⚙️ Tech Stack

- **Orchestration:** n8n (Docker)
- **LLM:** Gemma4 (Ollama, self-hosted)
- **Email:** Gmail API
- **E-commerce:** Shopify API
- **Tracking:** Shipway
- **Logging:** Google Sheets
- **Cache:** n8n global static data (23-hour TTL)

---

## 🔥 Edge Cases Handled

| Problem | Solution |
|---------|----------|
| "cancer it" → cancel | Regex mapping |
| Shopify token expiry | 23-hour cache |
| Malformed Gmail threadIds | Sanitization |
| # vs no # in order IDs | Normalization |
| "already sent video" | Intent override |
| Multi-order detection | Context-based scanning |
| Legal threats (FIR/police) | Escalation flag |

---

## 📈 Accuracy Journey

| Iteration | Accuracy |
|-----------|----------|
| v1 | 77% |
| v2 | 85% |
| v3 | 91% |
| v4 (Current) | **96%** |

---

## 📁 Repository Structure
