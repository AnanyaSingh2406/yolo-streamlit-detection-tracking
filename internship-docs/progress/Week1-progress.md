# Internship Progress Log
**Name:** Ananya Singh
**Company:** AparSoft

---

## 07-05-2026 — Day 1

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

## 09-05-2026 — Day 3

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

## 10-05-2026 — Day 4

### 1. Workstation Migration & Environment Setup
*   Successfully moved my entire development workspace over to a new MacBook Air.
*   Configured the terminal and installed the core tools required for the internship: Python 3.x, Git, and VS Code.
*   Verified that the Python virtual environment (`venv`) is working correctly to keep project libraries isolated from system files.

### 2. Git Workflow & Version Control
*   Learned the professional "save" process: staging files with `git add`, saving them with a `commit` message, and sending them to GitHub with `git push`.
*   Practiced managing the connection between my local machine, my personal GitHub fork (`AnanyaSingh2406`), and the company’s main repository.
*   Organized the project's folder structure to ensure it remains clean as the internship progresses.

---

## 11-05-2026 — Day 5

### 1. Technical Deep Dive: YOLO & Streamlit
*   **YOLO (You Only Look Once):** Gained a detailed understanding of how this real-time object detection system works, specifically how it processes entire images in a single pass for high speed and accuracy.
*   **Streamlit Framework:** Learnt the logic of turning Python scripts into interactive web apps, focusing on how it manages state and UI components without needing HTML/CSS.

### 2. Computer Vision Concepts & Dataset Overview
*   Looked over the **COCO Dataset** (Common Objects in Context) to understand the standard library of images used to train models like YOLO.
*   Mapped out the core differences between the four main types of Vision AI tasks:
    *   **Image Classification:** Identifying the main subject of a photo.
    *   **Object Detection:** Finding multiple objects and drawing "bounding boxes" around them.
    *   **Object Tracking:** Following a specific object's movement across a video.
    *   **Identification vs. Recognition:** Telling the difference between a general category (like "a car") and a specific unique item.

### 3. QA & Product Testing Preparation
*   Researched professional software testing methods to prepare for upcoming audits of AparSoft’s products.
*   Identified what to check for when testing the **Apar Chatbot**, **FireIQ**, and the **WhatsApp Chatbot**.

---

## 12-05-2026 — Day 6

### 1. Repository Organization & Documentation
*   Created a dedicated `internship-docs/` folder to keep progress reports and research separate from the actual code.
*   Divided this folder into `learnings/` and `progress/` sub-folders for better organization.
*   Moved earlier research files (like `AparSoft_Report.md`) into these new folders using the Mac terminal.

### 2. Technical Audit of the YOLO-Streamlit App
*   Performed a deep dive into the `app.py` and `README.md` files to understand how the Streamlit web interface communicates with the YOLO AI model.
*   Analyzed how the current app handles object tracking to identify potential areas for speed or accuracy improvements.
*   Developed a list of ideas for making the website more user-friendly and adding more detailed tracking metrics.

---

*Progress log maintained as part of internship documentation requirement.*
