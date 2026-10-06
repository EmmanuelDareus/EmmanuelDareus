### Hey, I'm Emmanuel Dareus!! 👋

I'm a software and AI engineer based in Florida who loves bringing ideas to life by writing clean code and teaming up with advanced AI models. I focus on building smart applications that automate workflows and solve real-world problems.

---

### 💡 4 Key Things About Me
1. **AI-Driven Builder:** I don't just write code the old-school way—I use modern AI models and agentic workflows as co-pilots to architect and ship software fast.
2. **Currently Building Omnilogiq:** I am actively developing a custom, AI-powered "school OS" app designed to streamline and organize academic workflows.
3. **The 9-Month Mission:** I'm following a strict, high-intensity roadmap to master full-stack software engineering, automation, and system design.
4. **Driven & Disciplined:** Whether I'm tracking financial markets or training on the soccer field, I treat high-performance habits the same way I treat code.

---

### 🧰 Tech & Tools I Use
* **Programming & Version Control:** Python, Git, GitHub, VS Code
* **AI & Automation:** Claude, ChatGPT, Gemini, Ollama, n8n
* **Workflow & Productivity:** Obsidian

---

### 📬 Let's Connect
Feel free to check out my repositories or reach out right here on GitHub!



# dd-recovery-os 🚀

[![CI Testing](https://github.com/emanthesoftwareengineer0403-art/dd-recovery-os/actions/workflows/pytest.yml/badge.svg)](https://github.com/emanthesoftwareengineer0403-art/dd-recovery-os/actions/workflows/pytest.yml)
[![Python Version](https://img.shields.io/badge/python-3.11%20%7C%203.14-blue.svg)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100%2B-009688.svg?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A modular, scalable Python backend application featuring a robust core engine, live-development middleware logging, and automated CI/CD-integrated testing.

---

## 🛠️ Project Architecture

```text
dd-recovery-os/
├── .github/
│   └── workflows/
│       └── pytest.yml      # Automated GitHub Actions CI pipeline
├── logs/
│   └── app.log             # Persistent runtime event & request logs
├── src/
│   ├── core/
│   │   └── engine.py       # Core application engine lifecycle
│   ├── integrations/       # External service and file system integrations
│   └── utils/
│       └── logger.py       # Standardized multi-stream logging utility
├── tests/
│   └── test_app.py         # Pytest suite for unit & API endpoint validation
├── main.py                 # FastAPI application entry point
├── config.py               # Global project configuration paths
└── requirements.txt        # Project dependencies
