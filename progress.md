# Internship Progress Log
**Name:** Ananya Singh
**Company:** AparSoft

---

## 07-05-2026
### 1. Cloned the repository and ran the YOLO Vision Studio app
- Cloned the repository: `yolo-streamlit-detection-tracking`
- Set up Python virtual environment (`venv`)
- Installed all dependencies from `requirements.txt`
- Successfully ran the YOLO Vision Studio app on `localhost:8501`
- App is working — tested image segmentation and object detection

### 2. GitHub Setup
- Forked the repository to personal GitHub account: `AnanyaSingh2406`
- Updated git remote URL to point to personal fork
- Added upstream remote pointing to original `aparsoft` repository
- Pushed `progress.md` to personal GitHub fork successfully

---

## 09-05-2026 — Day 2

### 1. Company & Product Research
- Explored AparSoft's full product portfolio on their website
- Studied all 5 products: Apar AI LMS, Apar Academy, Apar Exam, Apar Chatbot, FireIQ
- Understood the two core verticals: Education Technology and Enterprise AI
- Wrote a detailed company perception report (`AparSoft_Report.md`)

### 2. Deep Dive — Apar Chatbot

**What it is:**
Apar Chatbot is a multi-tenant enterprise chatbot built using a RAG (Retrieval Augmented Generation) architecture with pgvector as the vector database.

**What it does:**
- Allows businesses to deploy their own intelligent chatbot trained on their own data/documents
- Uses pgvector to store and search through document embeddings
- When a user asks a question, the chatbot retrieves the most relevant chunks from the company's documents and generates an accurate, context-aware response
- Multi-tenant means multiple businesses can each have their own isolated chatbot instance on the same platform

**Why it matters:**
Traditional chatbots follow fixed scripts. Apar Chatbot uses AI to understand natural language and answer from a company's actual knowledge base — making it far more intelligent and useful for customer support, internal helpdesks, or product FAQs.

**Tech Stack (inferred):**
- LLM for response generation
- pgvector (PostgreSQL extension) for vector similarity search
- RAG pipeline for document retrieval
- SaaS architecture for multi-tenancy

---

### 3. Deep Dive — FireIQ (Fire Detection)

**What it is:**
FireIQ is a Vision AI product that detects fire and smoke in real-time using camera feeds, powered by VLM (Vision Language Model) reasoning.

**What it does:**
- Connects to live camera streams (CCTV, IP cameras etc.)
- Uses computer vision models to identify fire and smoke in video frames in real-time
- VLM reasoning means it doesn't just detect — it can also describe and reason about what it sees (e.g., "smoke detected near electrical panel on floor 2")
- Sends alerts when fire/smoke is detected
- Can be deployed in factories, warehouses, server rooms, buildings

**Why it matters:**
Traditional fire detection relies on heat/smoke sensors which only trigger when fire is already significant. FireIQ can detect visual signs of fire and smoke much earlier, potentially saving lives and preventing major damage.

**Connection to my internship project:**
The `yolo-streamlit-detection-tracking` repository I am working on uses YOLO — the same family of computer vision models that would power FireIQ. This means my work is directly relevant to understanding and potentially contributing to FireIQ's detection pipeline.

**Tech Stack (inferred):**
- YOLO or similar real-time object detection model
- Vision Language Model (VLM) for reasoning layer
- Streamlit or similar for dashboard/interface
- Real-time video stream processing with OpenCV

---

*Progress log maintained as part of internship documentation requirement.*
