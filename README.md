# 🚀 AI Feature Intake Engine  
**Turn raw product requests into Jira-ready stories in under 1 minute, with humans in control**

---

## ❌ The Problem

Great product ideas fail every day. Not because they’re bad, but because they **arrive too late, too vague, or lose context** before reaching the backlog.

Typical intake issues:
- Requests come in via email, chat, docs, or forms
- PMs and TPMs spend hours rewriting and clarifying
- Context gets lost between stakeholders
- By the time it reaches Jira, urgency is gone
- Engineers get half-baked tickets → rework and delays

**Speed without control is dangerous.  
Control without speed is expensive.**

---

## ✅ The Solution

The **AI Feature Intake Engine** accelerates product request review **without removing human judgment**.

In under **60 seconds**, it:
- Summarizes incoming requests
- Breaks them into Jira-ready technical tasks
- Surfaces ambiguities early
- Requires explicit human approval before action

AI does the heavy lifting.  
Humans make the decision.

---

## 🧠 How It Works (High Level)

1. **Request arrives**  
   From Google Sheets, form, or intake source

2. **AI enrichment**  
   Gemini studies internal product features and architecture and converts raw input into:
   - Architectural summary
   - Clear technical sub-tasks

3. **Human-in-the-loop review**  
   Reviewer:
   - Reads a clean, readable summary
   - Approves or rejects explicitly (no auto-creation)

4. **Outcome**
   - ✅ Approved → Jira-ready payload
   - ❌ Rejected → Context-aware rejection email

All of this happens **before backlog pollution**.

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

No brittle automation.  
No blind Jira creation.  
No black-box AI behavior.

---

## 🎯 Why This Matters (TPM / Technical PM Perspective)

From a delivery standpoint:
- Late or unclear requests create downstream chaos
- Engineers lose trust in product signals
- Backlogs fill with low-quality tickets
- Roadmaps drift due to rework

This engine **pulls quality forward**:
- Faster intake ≠ rushed decisions
- Context preserved at the point of review
- Clear ownership before Jira is touched
- Fewer surprises during delivery

This is **decision acceleration**, not task automation.

---

## ⏱️ Real Impact

- ⏳ Intake review time: **Hours → < 1 minute**
- 📉 Rework caused by unclear tickets: **Significantly reduced**
- 🧠 Human oversight: **100% preserved**
- ⚙️ Jira hygiene: **Protected**

---

## 🛠️ Built With

- **n8n** — workflow orchestration
- **Gemini** — structured AI summarization
- **Google Sheets** — lightweight intake source
- **Google Drive** — document repository
- **Jira** — final system of record
- **Strict JSON schemas** — deterministic AI output
- **HTML-based review UI** — no stray JSON, no confusion

---


## Demo
🎥 Watch the full workflow demo on Loom:  
👉 [https://www.loom.com/share/YOUR_VIDEO_ID](https://www.loom.com/share/dfac4237b23d4684941629f1f5b55095)

🎥 The walkthrough shows:
- Intake → AI processing
- Human approval step
- Jira-ready output
  
---
## 👤 Who This Is For

- Technical Product Managers
- TPMs / Delivery Leads
- Startup founders handling high request volume
- Teams tired of backlog chaos
- Anyone who wants **AI speed without losing control**

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
- ✅ Q&A  
- ✅ Follow-up support via email  
