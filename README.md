# n8n-whatsapp-ai-bot
 Official Output OS blueprint for a 24/7 autonomous WhatsApp AI assistant in n8n.
# 🤖 n8n WhatsApp AI Assistant (Official Output OS Blueprint)

Build a 24/7 autonomous WhatsApp AI assistant inside n8n without paying for third-party subscription wrappers.

---

## ⚡ Quick Setup Guide

### 1. Import the Workflow
1. Open your n8n dashboard.
2. Click **Workflows** -> **Import from File** (or copy raw text from `workflow.json` and paste directly onto your n8n canvas).

### 2. Configure Node Credentials

* **Node 1: Webhook Trigger (Meta WhatsApp API)**
  - Set HTTP Method to `POST`.
  - Copy your generated n8n Webhook URL into your Facebook Developer Console under WhatsApp Configuration.

* **Node 2: Code Node (Data Sanitizer)**
  - Automatically extracts the sender's phone number and message payload from Meta's nested JSON structure.

* **Node 3: OpenAI / Anthropic Chat Node**
  - Add your API Key credentials.
  - Set System Prompt: `"You are an expert AI assistant operating on behalf of Output OS. Keep responses under 3 sentences."`

* **Node 4: HTTP Request Node (WhatsApp Send Reply)**
  - Endpoint URL: `https://graph.facebook.com/v17.0/YOUR_PHONE_NUMBER_ID/messages`
  - Authentication: Bearer Token (Meta Permanent Access Token).
  - Body JSON payload mapping sender phone and AI output text.

---

## 📺 Video Tutorial
Watch the full architectural breakdown on YouTube: [Output OS Channel](https://youtube.com/@OutputOS)

---

## 📄 License
MIT License - Free for commercial and personal use.
