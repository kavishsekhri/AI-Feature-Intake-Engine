# AI Feature Intake Engine  
*n8n + Google Sheets (Trigger) + Google Drive + Gemini AI + Jira*

## Overview
This project is an **AI-powered Feature Intake Engine** that converts user product requests into **reviewable, structured Jira-ready tickets**, with a **human-in-the-loop approval step**.

It is designed for Product, Engineering, and TPM teams who want speed **without losing control**.

---

## What this solves
- Users or POs write messy feature ideas  
- AI turns them into structured technical specs after reviewing internal documents  
- Humans review, edit, approve or reject  
- Only approved specs reach Jira  

No hallucinated tickets. No blind automation.

---

## Architecture
The system is intentionally split into **three independent workflows** for clarity, safety, and scale.

### 1. Main Intake Flow (AI Generation)
**Google Sheets → Filter → Google Drive Files → Gemini → Code → Email**

- Reads feature requests from Google Sheets
- The workflow triggers when a new row is added in the Request Intake sheet
- Internal Google Drive documents, like product features and technical architecture, are analyzed first  
- Gemini AI generate:
  - Architectural summary  
  - Technical task breakdown  
- Normalizes AI output into a strict internal schema  
- Sends an email with a secure **Review Draft link**

---

### 2. Review Draft Flow (Human-in-the-loop)
**GET Webhook → HTML Review Form → Respond to Webhook**

- Opens a clean HTML review page  
- Pre-fills AI-generated summary and tasks  
- Reviewer can:
  - Edit content  
  - Approve or reject  
  - Add rejection reason if needed  

This step prevents deterministic AI behavior from pushing bad specs downstream.

---

### 3. Submission Flow (Decision Engine)
**POST Webhook → IF → Jira / Rejection Email**

- If approved → Create Jira issue  
- If rejected → Send rejection email with feedback to the requester 
- Fully auditable and reversible

---

## Key Design Principles
- **Schema-first AI handling**  
  Gemini output is normalized and flattened before use.

- **Non-deterministic AI, deterministic system**  
  AI can vary. The workflow cannot.

- **Human control at the right moment**  
  Review happens before Jira, not after.

- **Separation of concerns**  
  Generation, review, and execution are decoupled.

---

## Tech Stack
- **n8n** – Workflow orchestration  
- **Google Gemini** – AI spec generation  
- **Google Sheets** – Intake source
- **Google Drive** – Internal document repository
- **Jira** – Execution system  
- **HTML + Webhooks** – Review UI  

---

## Demo
🎥 Watch the full workflow demo on Loom:  
👉 [https://www.loom.com/share/YOUR_VIDEO_ID](https://www.loom.com/share/dfac4237b23d4684941629f1f5b55095)

🎥 The walkthrough shows:
- End-to-end workflow execution  
- AI generation  
- Review & approval flow  
- Jira ticket creation  

---

## Who this is for
- Product Managers  
- Technical Program Managers  
- Engineering Leads  
- Teams experimenting with AI safely in production workflows  

---

## Why this matters
This is not “AI replacing PMs.”

This is **AI doing the boring 80%**, while humans keep ownership of decisions.

---

## 💼 Need Help Getting Started?

Setting up the **AI-Feature-Intake-Engine** can be complex. I offer personalized setup sessions to help you get up and running quickly.

### 📅 Book a Setup Session

**30-Minute Quick Help — $50**  
Perfect for quick questions, troubleshooting, or guidance on specific features.  
👉 https://cal.com/kavish-sekhri/30min

**60-Minute Deep Dive — $100**  
Comprehensive setup assistance, configuration, and Q&A.  
👉 https://cal.com/kavish-sekhri/60min

### What’s Included
- ✅ One-on-one video consultation  
- ✅ Personalized setup assistance for your team  
- ✅ Configuration guidance for your specific use case  
- ✅ Live Q&A  
- ✅ Follow-up support via email  
