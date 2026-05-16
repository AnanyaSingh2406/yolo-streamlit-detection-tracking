# FireIQ
*Project Evaluation and Prototype Case Study*

---

Detecting a fire isn't the main challenge—the real value lies in what the system does after it sees the fire.

* **The Problem:** Anyone can train an AI model to detect a flame. The hard part is avoiding false alarms (like mistaking a red light for a fire) and handling the chaos once a fire is found.
* **The Solution:** FireIQ is a complete "incident workflow." It doesn't just circle a fire in red; it cleans up mistakes (suppression), explains the situation in detail using language models (VLM reasoning), instantly alerts the right people via text or email (alert fan-out), and saves a video history for insurance or safety reviews (evidence trail).
___
* A simple **"bounding box"** (drawing a square around a fire) is not enough to help a facility manager during a real emergency. If an AI just puts a box around a fire on a screen, a human still has to figure out if it's a false alarm, how bad it is, and who to call.

* FireIQ is a Complete Workflow: It handles the entire crisis automatically in one connected loop: it captures the video (Ingest), identifies the fire (Detect), filters out false alarms (Smooth), describes the danger in plain English (Reason with a VLM), sends instant alerts to the team (Fan out), and saves the video for proof (Log evidence).
> 
> `[Ingest] ➔ [Detect] ➔ [Smooth] ➔ [Reason (VLM)] ➔ [Fan Out Alerts] ➔ [Log Evidence]`

---

## Why Current Fire Detection Systems Fail

### 1. Fire detection without an incident workflow is still a gap
* **The Problem:** Just knowing there is a fire isn't enough; an operator needs an automated system that handles routing the alert, saving evidence, and guiding the team's response.
* **The Bottom Line:** Detection is useless if you don't have a plan for what happens next.

### 2. Visual context is missing from most alarms
* **The Problem:** Traditional alarms tell you that something is wrong, but they don't show you what or how bad it is, leaving teams guessing during critical moments.
* **The Bottom Line:** Teams need instant visual proof to make fast, life-saving decisions.

### 3. Raw per-frame detection is too unstable to trust
* **The Problem:** AI models can "flicker," detecting a fire in one video frame and missing it in the next, which creates chaotic, blinking alerts that operators eventually learn to ignore.
* **The Bottom Line:** Alert smoothing (stabilizing the alarm) is required so humans can actually trust the system.

### 4. Detection accuracy is not the only false-positive problem
* **The Problem:** Things like dust, steam, or light glare easily confuse standard AI models into triggering false fire alarms.
* **The Bottom Line:** Using a second layer of AI judgment (like a VLM) to double-check the scene prevents false alarms from destroying operator trust.

### 5. Incidents without evidence trails are hard to learn from
* **The Problem:** If a system doesn't automatically log snapshots, video clips, and summaries of an incident, companies have no accurate data to review or learn from later.
* **The Bottom Line:** A safety system must create a permanent paper trail for accountability and future improvement.

---

## What Each Group Cares About

| Stakeholder Persona | Core Focus & Responsibilities | Key Priorities & Requirements (The Bottom Line) |
| :--- | :--- | :--- |
| **1. Operational Buyer** *(Managers & Executives)* | Business continuity, risk mitigation, liability. | Want to see the "big picture" of safety, specifically how the system handles the entire crisis from detection to saving the final evidence log. **Care about liability, liability protection, and reducing overall business risk.** |
| **2. Daily Operator** *(Control-Room & Security Teams)* | Active monitoring, rapid live response execution. | Need a clean, stable dashboard with clear severity scores and plain-language summaries, without annoying, flickering false alarms. **Care about a tool that makes their actual shifts easier and doesn't waste their time.** |
| **3. Integration Partner** *(Engineers & Technical Installers)* | System compatibility, installation pipelines, hardware IO. | Need to know that the software easily connects to real hardware (like live security cameras via RTSP) and existing physical alarm systems (via webhooks or hardware ports). **Care about how difficult or easy it is to physically install and wire up the software.** |

---

## 7 Engineering Features

### 1. Real monitoring loop across multiple input sources
The app doesn't just scan a single video file and stop. It works like a real security system that stays open, runs continuously, and can watch live camera feeds, YouTube streams, or uploads.

### 2. Runtime class resolution
The code doesn't have words like "fire" or "smoke" hardcoded. Instead, it asks the AI model what it is trained to see right when it starts up, meaning you can swap or upgrade your AI models instantly without breaking the code.

### 3. Alert smoothing
If the AI blinks and loses sight of the fire for one second, the app doesn't instantly turn off the alarm. It holds the box on the screen for a moment so the dashboard doesn't violently flicker and annoy the user.

### 4. Secondary classifier (False-positive suppression)
It uses a second, backup AI model to double-check the first one. If the primary model thinks steam or dust is "smoke," the backup model checks the room and cancels the false alarm.

### 5. VLM-based scene reasoning
Instead of just drawing a red square and saying "fire," it uses a smart language model to write a short paragraph explaining exactly what is happening (e.g., *"A small electrical fire has started near the computer desk"*).

### 6. Multi-channel alert fan-out (AlertBus)
It has a built-in routing system that sends the alarm to multiple places at the exact same time—ringing physical buzzers, flashing LED lights, and sending digital messages to other apps.

### 7. Evidence trail
Every single time an alarm goes off, the system automatically takes a picture, writes down the exact time, and saves a text report so managers have a permanent record for safety and insurance checks.

---

## Five Connected Steps
These steps happen automatically from the moment a camera spots a fire to when the final report is saved. It emphasizes that FireIQ is a complete "lifecycle" rather than just a collection of separate features.

### 1. Detect and Surface
* **What it does:** The AI monitors the live camera feed, draws boxes around any fire or smoke it sees, and displays a live scoreboard showing the danger level and trends.
* **In simple terms:** It changes the raw video feed into a live, smart dashboard that security guards can easily read.

### 2. Smooth and Hold the Alert State
* **What it does:** It keeps the alarm active and the boxes on screen for a few extra seconds even if the AI briefly loses sight of the flame, while a backup AI checks for false alarms.
* **In simple terms:** It stabilizes the screen so the alarm doesn't annoying-ly flicker on and off during a real crisis.

### 3. Reason with VLM
* **What it does:** It takes a snapshot of the fire and sends it to a Vision Language Model, which instantly writes out a plain English explanation of the cause, danger level, and next steps.
* **In simple terms:** It changes a basic "red alert" into an intelligent summary that tells the operator exactly what is happening and how to react.

### 4. Fan Out the Alert
* **What it does:** A central module (AlertBus) instantly sends the alarm to a web dashboard, flashes physical lights, and sounds local buzzers all at once.
* **In simple terms:** It ensures the warning immediately leaves the computer screen and reaches the actual people and hardware in the building.

### 5. Capture the Evidence Trail
* **What it does:** The system automatically saves a JPEG photo of the incident, the AI's written report, and a detailed spreadsheet log with exact timestamps.
* **In simple terms:** It builds a permanent, digital paper trail so management can review exactly what happened for insurance or safety audits.

---

## Five Implementation Layers
These layers make the FireIQ prototype look like a professional, believable system rather than a cheap school project.

### 1. Four+ Input Modes
The app monitors live security camera feeds (RTSP), YouTube live streams, uploaded clips, and local test footage all from the same interface instead of relying on a single test file.

### 2. Two-Stage Detection Pipeline
It uses two layers of AI security where the primary model catches the fire, and a secondary classifier checks the frame to ensure things like dust, steam, or light glare aren't causing a false alarm.

### 3. Five-Field VLM Incident Analysis
When an alarm triggers, a vision-language model writes a structured report covering five specific fields: scene description, probable cause, severity score (1–5), recommended actions, and evacuation guidance.

### 4. Three Training Paths
The system is built to experiment with and swap three different AI approaches over time, ensuring the platform isn't permanently locked into a single frozen model checkpoint.

### 5. Quality Gates
It includes smart safety features like alert smoothing to stop screen flicker, graceful text fallbacks if the vision AI fails, and fail-soft backends so missing physical hardware doesn't crash the software.

---

## Five Useful Things Established Before Production Engineering Begins
FireIQ is still a prototype. The value of this stage is clarity — collapsing the ambiguous into the inspectable. These are the proof points the prototype can honestly defend.

### 1. Live End-to-End Event Loop
Detection, alert smoothing, VLM reasoning, alert fan-out, and evidence logging all work together inside a single continuous monitoring session rather than functioning as separate, disconnected tools.

### 2. Four Alert Channels Proven
The system successfully communicates with console logs, network webhooks, RS232 serial connections, and physical hardware pins (GPIO), ensuring the framework is ready to talk to real-world facility equipment.

### 3. Saved Incident Evidence Trail
Every alert automatically saves image snapshots, JSON files containing the AI's logic, and a CSV spreadsheet log, giving management a permanent record for safety and insurance audits without needing live video replays.

### 4. 1–5 VLM Severity Scoring
Instead of giving a basic AI confidence percentage, a local language model reads the scene to provide an actionable, 5-part summary detailing the exact cause, a severity score, and clear evacuation instructions.

### 5. Three Model Training Paths Open
The codebase includes open scripts to update and train the primary detector, the backup false-alarm filter, and alternate AI architectures, ensuring the software isn't permanently locked to a single version.

### 6. Clear Production Path Defined
By building and testing every stage of the pipeline now, the engineering team has a clear, visible blueprint of how the system performs, removing guesswork when it comes time to build the heavy-duty production version.

---

## Why the User Experience Matters Most
Most AI fire demos do nothing more than draw a box around a flame on a video. FireIQ goes beyond that by focusing entirely on what the security guards (operators) and technical installers actually need during a real crisis.

* **A Complete Incident Process:** Instead of running as a simple testing script, the system connects video monitoring, false-alarm filtering, text explanations, and physical alarms into one single, smooth operation.
* **Ready to Connect to Hardware:** Right from the prototype stage, the software is built to talk to network servers, serial communication lines, and physical warning boards (GPIO). This means it can be tested with real building hardware immediately.
* **Conversations with Buyers:** When showcasing the tool to managers, the focus shifts away from raw mathematical accuracy. Instead, it shows how helpful the AI is under pressure by displaying a severity score, a likely cause of the fire, and an action plan.

---

## How FireIQ Proves AparSoft's Development Capabilities
FireIQ isn't just a fire safety demo; it is proof of how efficiently the company builds software by using smart, reusable engineering practices.

* **Using Existing Foundations (Apar Drishti):** The engineers didn't start coding from scratch. They took the pre-existing video ingestion and interface tools from their core software system (Apar Drishti) and simply added fire-detection features on top of it.
* **Practical Thinking First:** Essential features like smooth alarms, multi-channel alerting, and automated record-keeping were built right into the first draft instead of being delayed for a future product update.
* **Honesty and Progress:** The documentation is completely honest about the software being an early testing model (prototype) rather than a finished product. However, it leaves all training pathways open so engineers can easily swap out and improve the AI models later.

---

## The FireIQ Tech Stack Explained
This list shows the different software layers that work together to capture video, detect fire, analyze the crisis, and send out alerts.

* **SOTA Detector:** This stands for State-of-the-Art Detector (like the YOLO family models). It is the primary high-speed computer vision engine that actively scans the incoming video frames to spot fire and smoke instantly.
* **RF-DETR Training Path:** This is an alternative, advanced object detection model architecture (Real-Time DEtection TRansformer). Having this open path means the system isn't locked into just one type of AI; engineers can train and test different modern models to improve accuracy over time.
* **Locally GPU-Powered VLM:** This is the Vision Language Model that runs on local hardware graphic cards (GPUs) instead of relying on a slow internet connection. It is the "brain" that looks at a snapshot of the fire and writes out the 5-field plain English crisis description and safety recommendations.
* **Dashboard Monitoring App:** Built using a Python framework like Streamlit, this is the live user interface (HUD) that the operator looks at. It displays the live video stream, draws the bounding boxes, and shows the real-time fire and smoke trend charts.
* **AlertBus Fan-Out:** This is a custom-built routing module in the code. Once a fire is confirmed, this "bus" acts like a power strip, instantly sending the alert signal out to multiple places at once (computer console, network webhooks, or hardware pins to ring physical buzzers).
* **Alert Receiver:** A lightweight local web server (typically built using Flask) that runs on a separate dashboard or screen. It acts as the destination that catches the digital alert signal from the AlertBus and flashes a bright red warning banner for the control room team.
