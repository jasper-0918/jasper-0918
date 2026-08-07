# Hi, I'm Jasper John Paitan 👋
### AI Automation Specialist & AI Developer · Computer Engineer who ships systems that run

I build **AI automation**: the systems that take a workflow somebody is doing by hand every day and
turn it into software that runs on its own. Most of it lives in **no-code and low-code platforms**,
because that is where a business can actually see and own what it bought. I run a **self-hosted n8n
instance**, author workflows as JSON and deploy them through n8n's own REST API, and build
**Make.com** scenarios that fan a single webhook out to Sheets, Slack and Airtable.

Where a platform runs out of room, I keep going. The **AI development** side is mine too:
tool-calling agents, multi-provider LLM routing with failover, RAG, and local on-device models,
written in Python rather than assembled from a template.

**My edge:** a real engineering foundation, a Computer Engineering degree and systems work from
Python to embedded C, so what I hand over is debugged, secured, and maintainable, not
prompt-and-pray.

🎓 Computer Engineering, La Salle University – Ozamiz (2026) &nbsp;|&nbsp; 📍 Philippines (UTC+8),
**available for remote work worldwide**
🌐 [Portfolio](https://jasper-0918.github.io/) &nbsp;|&nbsp; 📧 jasper.paitan0918@gmail.com &nbsp;|&nbsp;
[LinkedIn](https://www.linkedin.com/in/jasper-john-paitan-11641337b) &nbsp;|&nbsp;
[Credly Certifications](https://www.credly.com/users/jasper-john-paitan)

---

## ⚡ What I Build

- **AI Automation** — webhook in, decision in the middle, the right rows written and the right people notified, running on a schedule nobody has to remember
- **No-Code & Workflow Platforms** — n8n, Make, Airtable, Google Sheets and Slack, built so your team can open the canvas and read what it does rather than take my word for it
- **AI Development** — tool-calling agents, multi-provider LLM routing with failover, RAG over your own documents, and local models, written in Python
- **Multi-Agent Systems** — a planner that decomposes one directive into a dependency graph, workers that claim it under lease, and safety properties enforced as preconditions in code rather than requested in a prompt
- **Private & Local AI** — on-device assistants (Ollama, ChromaDB) that keep data on the client's own machine, with no subscription and no third party in the loop
- **Applied ML & Edge AI** — computer vision and real-time inference on-device (TensorFlow, Edge Impulse, Raspberry Pi)

## 💼 How I Can Help

I help teams find the highest-ROI workflow to automate, then **design, build, and hand over the system
that does it**, documented, reliable, and yours to keep. Available for **remote** AI automation and AI
development roles, and for consulting engagements.

- Automate a manual, repetitive workflow (lead intake, outreach, data entry, reporting) end to end
- Connect the tools you already pay for, so a form submission reaches your CRM, your sheet and your team without anyone retyping it
- Add an AI layer (chat, RAG, classification, routing) to an existing product or ops stack
- Stand up a private, local LLM setup so sensitive data never leaves your infrastructure
- Build your small business a **premium website wired for lead response** — form to instant reply to follow-up, so no inquiry goes cold

---

## 🚀 Featured Projects

### [💬 AI DM Setter](https://github.com/jasper-0918/ai-dm-setter) — Multi-Tenant Lead Qualification & Booking
> *Qualifies inbound leads in a chat window and books the call inside the conversation, no calendar
> link. One workflow serves any number of businesses.*

- **Multi-tenant by design** — each client's persona, offer, and pricing is a database row, so onboarding the next business is an insert, not a copied workflow
- **The model returns state, not prose** — every reply satisfies a `{ reply, booked, slot }` contract, so booking detection is a code path rather than an interpretation
- **A deterministic fallback covers model failure** — if the provider errors or garbles its output, a rules-based reply still goes out; a lead is never left on read
- **Tenant isolation is enforced, not assumed** — history is read on `client_id` AND `user_id`, and I proved it by reusing one lead id across two client accounts and confirming the second returned zero history rows

**Tech:** n8n (self-hosted), Postgres, LLM APIs, webhooks, REST API-driven workflow deployment

---

### ⚙️ Workflow Automation Stack — Self-Hosted n8n + Make
> *I run my own n8n rather than renting one, and I deploy to it through its REST API, so a workflow
> is a reviewable file instead of something someone clicked together and can't reproduce.*

- **Self-hosted n8n in Docker** — community edition, data persisting in a named volume, no per-task pricing and no vendor holding the automations
- **Workflows deployed over the REST API** — authored as JSON, then created, patched, activated and audited programmatically, which makes them diffable and repeatable
- **Credentials attached at push time** from a node-to-credential map, because n8n's export omits credentials entirely and a naive push silently strips them off every node
- **An error workflow on everything** — any failure emails the workflow, the failed node, and a link to that exact execution; silent failure is the thing I design against
- **Make scenario for lead routing** — a webhook receives an enquiry, branches on the answers, and fans out to Google Sheets, Slack, and an Airtable base whose formula field scores the lead on arrival

**Tech:** n8n (self-hosted), Docker, Make, REST API deployment, webhooks, Airtable, Google Sheets, Slack

---

### [⭐ agent-os](https://github.com/jasper-0918/agent-os) — Local Multi-Agent Team with Enforced Guardrails
> *You give one directive. A manager agent modelled on you turns it into a dependency graph of tasks
> and hands them to ten specialist workers. Runs fully offline, at zero cost, on your own machine.*

- **Plans, then executes** — one directive becomes a validated task graph with cycle detection and a closed set of ten worker roles; an illegal plan is rejected by code, not talked out of it by a prompt
- **Survives a crash** — the SQLite queue hands out work under lease, so a killed worker's task returns to the queue instead of vanishing
- **Fails closed on private data** — anything marked personal is pinned to a local model, and an egress tripwire inspects the outgoing bytes before any request leaves the machine
- **One live truth per subject**, enforced by a partial unique index, so the model of you never holds two contradictory beliefs at once
- **55 offline tests**, each written against a bug reproduced first, including a queue deadlock that reported itself as idle

**Tech:** Python, SQLite, FastAPI, Ollama, multi-provider LLM routing, capability policy + egress guardrails

---

### [🤖 Autonomous Job-Hunting Agent](https://github.com/jasper-0918/job-bot) — cut search from 2–4 hrs to under 10 min
> *An end-to-end agent that scrapes, screens, applies, and monitors replies, with a human kept in control.*

- **Result: reduced daily job-search time from 2–4 hours to under 10 minutes**
- Scrapes listings (Playwright), then scores each with an LLM for fit and **scam detection** (keyword filter + deep analysis)
- **Tiered decision engine** (auto-apply / human review / reject) based on AI fit scoring
- Generates a tailored cover letter per role, applies, and classifies inbox replies via IMAP; FastAPI dashboard for live monitoring

**Tech:** Python, Playwright, FastAPI, SQLite, Claude AI, Gmail SMTP/IMAP

> Also rebuilt as a [free, zero-cost version](https://github.com/jasper-0918/job-ai-agent-free) using only open-source tools, same pipeline, no paid APIs, to prove cost-efficient automation on any budget.

---

### [🧠 Personal AI Virtual Assistant](https://github.com/jasper-0918/personal-ai-assistant) — Fully Local Agent
> *A private AI agent that runs entirely on-device, no cloud, no data leaving the machine.*

- Runs **fully local via Ollama** — no subscriptions, no cloud APIs, no data leaving your machine
- RAG pipeline (ChromaDB + sentence-transformers) trained on personal notes to answer and draft in your own voice
- Reads and summarizes Gmail, drafts replies in your tone, scans for interview responses
- Autonomously searches and applies to jobs, and scaffolds complete working projects (plus a demo video) from a one-line prompt

**Tech:** Python, Ollama, ChromaDB, Streamlit, Gmail IMAP/SMTP, GitHub REST API, RAG

---

### [🎮 RoScript AI Pro](https://github.com/jasper-0918/RoScript-Pro) — Multi-Provider AI Coding Agent
> *A single-file, zero-backend AI coding assistant for game developers, engineered for reliability
> across multiple LLM providers.*

- **Multi-provider routing with automatic failover and API-key rotation** across Groq, OpenRouter, and Cerebras, so a rate-limited or down provider never stops the session
- Multi-round tool-calling: the agent calls tools, reads results, and keeps reasoning across steps in one turn
- Two-layer validation pipeline (static analysis + independent AI self-review) that catches and corrects logic errors before code is shown
- Integrated Tavily web search and AI image generation, hardened against XSS, all in one portable HTML file

**Tech:** HTML/CSS/JavaScript, Groq API, OpenRouter, Cerebras, Tavily Search API

---

### [📁 AI Document Organizer](https://github.com/jasper-0918/ai-document-organizer) — hands-free file classification
> *Auto-classifies and files documents using zero-shot NLP and computer vision, no training data,
> no manual rules.*

- Classifies documents by content using zero-shot NLP (`facebook/bart-large-mnli`)
- Recognizes image types with OpenCV scene recognition; perceptual-hash duplicate detection
- Runs hands-free on a schedule with dry-run and watch modes; SQLite history prevents re-processing

**Tech:** Python, HuggingFace Transformers, OpenCV, SQLite, schedule

---

### [🏪 Lead-Gen Website Demos](https://jasper-0918.github.io/demos/clinic/) — small-business sites built to convert
> *Three vertical demo sites — dental clinic, real estate, home services — each with its own complete
> design system and a lead-qualifying form. Work samples for my web design + lead-response service.*

- Three distinct design systems, hand-built in a single file each: no frameworks, no stock photos, all SVG illustration
- Lead-machine patterns throughout: reply-time promises, qualifying forms (service, budget, urgency), call CTAs
- Live: [Dental Clinic](https://jasper-0918.github.io/demos/clinic/) · [Real Estate](https://jasper-0918.github.io/demos/realestate/) · [Home Services](https://jasper-0918.github.io/demos/homeservices/)

**Tech:** HTML/CSS/JS, design systems, SVG illustration, conversion copywriting *(source private)*

---

### ♻️ Automatic Plastic Bottle Segregation System — Edge AI *(Thesis, Best Design Project)*
> *A real-time computer-vision system that classifies and physically sorts plastics, running entirely
> on-device with no cloud dependency.*

- MobileNet CNN (TensorFlow + Edge Impulse) classifying 5 plastic resin types at **greater than 90% accuracy**
- **Real-time inference fully on-device on a Raspberry Pi 5** — no cloud round-trip
- Servo actuators driven by model output automate the physical sorting end-to-end

**Tech:** Python, TensorFlow, TensorFlow Lite, Edge Impulse, OpenCV, Raspberry Pi 5

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| **AI Automation** | n8n (self-hosted), Make, webhooks, REST API deployment, error workflows and retries, scheduling, Playwright, web scraping, email automation (SMTP/IMAP) |
| **No-Code & Workflow Platforms** | n8n, Make, Airtable, Google Sheets, Slack, visual workflow design meant to be read by the team that inherits it |
| **AI Development** | Multi-agent orchestration (framework-free), tool-calling agents, multi-provider routing (Groq, Claude, OpenRouter, Cerebras), failover and key rotation, RAG (ChromaDB), prompt engineering, local LLM deployment (Ollama) |
| **ML & Edge AI** | TensorFlow, TensorFlow Lite, Edge Impulse, HuggingFace Transformers, OpenCV, on-device inference |
| **Backend & Data** | Python, FastAPI, REST APIs, SQLite, MySQL, pandas, numpy |
| **Languages & Tooling** | Python, C, C++, C#, JavaScript, Assembly, SQL, Git & GitHub, Docker, Linux, Raspberry Pi |

---

## 🎓 Background

Computer Engineering graduate with a software development internship at **Benpos Systems** (system
maintenance, defect resolution, client deployments), and a growing portfolio of AI automation and
agent systems. Certified in cybersecurity through **Google Cloud** and **Cisco**, a
security-conscious foundation for the private, local-first AI I build. I build things that run in
production, not demos.

---

## 📬 Let's Work Together

Available for **remote** AI automation and AI development roles, and consulting engagements, worldwide.

[![Portfolio](https://img.shields.io/badge/-Portfolio-000000?style=flat&logo=github&logoColor=white)](https://jasper-0918.github.io/)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jasper-john-paitan-11641337b)
[![Email](https://img.shields.io/badge/-Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:jasper.paitan0918@gmail.com)
[![Credly](https://img.shields.io/badge/-Certifications-FF6B00?style=flat&logo=credly&logoColor=white)](https://www.credly.com/users/jasper-john-paitan)
