# TroubleShooter-AI 🛠️⚡

> **An AI-Assisted Cisco Network Diagnostic Engine & Infrastructure Troubleshooter**

TroubleShooter-AI is a full-stack automated network diagnostic tool that bridges network engineering and generative AI. It accepts raw diagnostic output from Cisco IOS devices (or Cisco Packet Tracer simulations), parses key protocol states, and leverages Large Language Models (LLMs) to identify root cause misconfigurations and generate exact CLI remediation commands.

---

## 🌟 Key Features

- **Automated Configuration Parsing**: Parses diagnostic outputs (`show running-config`, `show ip route`, `show ip interface brief`, etc.) from Cisco routers and switches.
- **LLM-Driven Root Cause Analysis**: Uses custom prompt templates (`diagnose_prompt.md`) and LLM orchestration to identify protocol failures (VLAN misconfigurations, DHCP scope issues, static/dynamic routing drops, and ACL rules).
- **Synthetic Test-Case Generator**: Includes a dedicated script (`generate_cases.py`) and dataset (`cases.csv`) to benchmark diagnostic accuracy across custom topology scenarios.
- **Interactive Web Dashboard**: Modern React + Vite frontend for real-time log ingestion, diagnostic breakdown, and side-by-side CLI command generation.
- **Human-in-the-Loop Safeguard**: Generates suggested CLI remediation scripts that engineers can review and verify before applying to production/simulated devices.

---

## 🏗️ System Architecture


```

┌───────────────────────────┐      ┌───────────────────────────┐
│   Cisco Packet Tracer /   │      │   React + Vite Frontend   │
│     IOS CLI Telemetry     │      │   (Interactive Web UI)    │
└─────────────┬─────────────┘      └─────────────┬─────────────┘
│                                  │
│ Raw Log Output                   │ REST API
▼                                  ▼
┌──────────────────────────────────────────────────────────────┐
│                   Python Backend Engine                      │
│      (FastAPI/Flask API Parser & Diagnostic Agent)           │
└─────────────────────────────┬────────────────────────────────┘
│
▼
┌──────────────────────────────────────────────────────────────┐
│              LLM Diagnostic Pipeline & Prompts               │
│         (LangChain / Groq / OpenAI Integration)              │
└──────────────────────────────────────────────────────────────┘

```

---

## 🛠️ Tech Stack

- **Frontend**: React, TypeScript, Vite, Tailwind CSS
- **Backend**: Python 3.10+, FastAPI/Flask
- **AI & Automation**: LangChain, LLM Prompts (`diagnose_prompt.md`), Custom Synthesizers
- **Networking Protocols**: Cisco IOS, TCP/IP, Subnetting, VLAN, OSPF/EIGRP, DHCP, NAT, ACLs
- **Simulation**: Cisco Packet Tracer

---

## 📁 Repository Structure


```

TroubleShooter-AI/
├── backend/
│   ├── checker.py            # Log validation & CLI parser engine
│   └── main.py               # API backend routes & model invocation
├── frontend/
│   ├── public/               # Static assets & icons
│   ├── src/                  # React dashboard components & UI
│   ├── package.json          # Frontend dependencies
│   └── vite.config.ts        # Vite configuration
├── cases.csv                 # Synthetic test case dataset
├── diagnose_prompt.md        # Core LLM prompt engineering template
├── generate_cases.py         # Test case generation engine
└── README.md                 # Project documentation

```

---

## 🚀 Getting Started

### Prerequisites

- **Python**: `3.10` or higher
- **Node.js**: `v18.0` or higher
- **Cisco Packet Tracer** (Optional, for generating live network logs)

### 1. Backend Setup

```bash
# Navigate to backend directory or project root
cd backend

# Install dependencies
pip install -r requirements.txt

# Start the Python server
python main.py

```

### 2. Frontend Setup

```bash
# Navigate to frontend directory
cd frontend

# Install packages
npm install

# Start development server
npm run dev

```

Open `http://localhost:5173` in your browser to access the dashboard.

---

## 🤝 Contributors

* **Rushan Dayma** ([@RushanDayma](https://www.google.com/search?q=https://github.com/RushanDayma&utm_source=gemini))
* **Aditya** ([@aditya-3027](https://www.google.com/search?q=https://github.com/aditya-3027&utm_source=gemini))

