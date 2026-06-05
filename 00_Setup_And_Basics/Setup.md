# 🐍 Python Programming — Complete Professional Setup Guide

> **The most comprehensive Python environment setup guide for students, engineers, researchers, and open-source contributors.**
>
> From a brand-new computer → to a fully professional AI/ML-ready Python development environment.

---

<div align="center">

![Python](https://img.shields.io/badge/Python-3.12+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-informational?style=for-the-badge)
![Level](https://img.shields.io/badge/Level-Beginner%20to%20Expert-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

</div>

---

## 📋 Table of Contents

| # | Section | Description |
|---|---------|-------------|
| 01 | [Introduction to Python](#section-1--introduction-to-python) | History, ecosystem, use cases, career paths |
| 02 | [System Requirements](#section-2--system-requirements) | Hardware specs across all platforms |
| 03 | [Python Installation](#section-3--python-installation) | Windows, macOS, Linux installation |
| 04 | [Environment Management](#section-4--python-environment-management) | venv, virtualenv, poetry, pyenv |
| 05 | [VS Code Setup](#section-5--visual-studio-code-setup) | Extensions, settings, themes |
| 06 | [PyCharm Setup](#section-6--pycharm-setup) | Community & Professional |
| 07 | [Git Installation](#section-7--git-installation) | Version control fundamentals |
| 08 | [Git Configuration](#section-8--git-configuration) | Username, email, SSH, credential storage |
| 09 | [GitHub Setup](#section-9--github-setup) | Account, repos, PRs, Actions |
| 10 | [SSH Configuration](#section-10--ssh-configuration) | Keys, authentication, security |
| 11 | [Professional Git Workflow](#section-11--professional-git-workflow) | All essential Git commands |
| 12 | [Project Structure](#section-12--professional-python-project-structure) | Repository layout explained |
| 13 | [Jupyter Notebook Setup](#section-13--jupyter-notebook-setup) | Kernels, extensions, workflows |
| 14 | [Terminal Mastery](#section-14--terminal-mastery) | CMD, PowerShell, Bash, Zsh |
| 15 | [Common Errors & Solutions](#section-15--common-errors--solutions) | Extensive troubleshooting guide |
| 16 | [Security Best Practices](#section-16--security-best-practices) | API keys, .env, secrets |
| 17 | [Productivity Tools](#section-17--productivity-tools) | Essential developer tools |
| 18 | [Developer Best Practices](#section-18--developer-best-practices) | PEP8, testing, clean code |
| 19 | [Quick Setup Checklist](#section-19--quick-setup-checklist) | Verification checklist |
| 20 | [AI/LLM Engineering Roadmap](#section-20--aillm-engineering-roadmap) | Full learning roadmap |
| 21 | [FAQ](#section-21--faq) | 50+ beginner questions answered |
| 22 | [Resources](#section-22--resources) | Books, courses, communities |

---

## Section 1 — Introduction to Python

### 🐍 What is Python?

Python is a **high-level, interpreted, general-purpose programming language** created by **Guido van Rossum** and first released in **1991**. It was designed with a philosophy centered on code readability, simplicity, and expressiveness — captured in the famous document called **"The Zen of Python"** (type `import this` in any Python shell to read it).

Python's syntax uses **indentation** (spaces or tabs) to define code blocks, unlike C, Java, or JavaScript which use curly braces `{}`. This forces a clean, readable style that makes Python code look almost like plain English.

```python
# Python reads like natural language
name = "Baghel"
age = 20

if age >= 18:
    print(f"Hello {name}, you are an adult.")
else:
    print(f"Hello {name}, you are a minor.")
```

---

### 📜 History of Python

| Year | Milestone |
|------|-----------|
| 1989 | Guido van Rossum begins Python during Christmas holidays |
| 1991 | **Python 0.9.0** released — first public version |
| 1994 | **Python 1.0** released — lambda, map, filter added |
| 2000 | **Python 2.0** released — list comprehensions, garbage collection |
| 2008 | **Python 3.0** released — broke backward compatibility, major redesign |
| 2020 | **Python 2 officially retired** — Python 3 becomes the only standard |
| 2021 | **Python 3.10** — structural pattern matching (`match/case`) |
| 2022 | **Python 3.11** — 25% faster performance |
| 2023 | **Python 3.12** — better error messages, type system improvements |
| 2024 | **Python 3.13** — free-threaded mode (no GIL), JIT compiler preview |

> **💡 Note:** Always use **Python 3.10+** for new projects. Python 2 is end-of-life and should never be used.

---

### 🌟 Why Python is Popular

Python consistently ranks **#1 or #2** in every major programming language index (TIOBE, PYPL, Stack Overflow Developer Survey) because:

1. **Beginner Friendly** — The simplest syntax of any mainstream language
2. **Versatile** — Works for web, AI, data, automation, security, embedded systems
3. **Massive Ecosystem** — Over **500,000 packages** on PyPI (Python Package Index)
4. **Industry Adoption** — Used by Google, NASA, Netflix, Instagram, Spotify, OpenAI
5. **Community** — One of the largest, most welcoming developer communities in the world
6. **Free & Open Source** — No cost, no license restrictions
7. **Cross-Platform** — Runs identically on Windows, macOS, and Linux
8. **AI/ML Standard** — PyTorch, TensorFlow, scikit-learn, Hugging Face — all Python-first

---

### ✅ Advantages of Python

| Advantage | Details |
|-----------|---------|
| **Readable Syntax** | Code reads like English; minimal boilerplate |
| **Large Standard Library** | "Batteries included" — hundreds of built-in modules |
| **Rapid Development** | Prototype ideas 5–10x faster than Java or C++ |
| **Interpreted** | No compilation step; immediate feedback |
| **Dynamic Typing** | Variables don't need type declarations |
| **Multi-Paradigm** | Supports OOP, functional, procedural styles |
| **Glue Language** | Integrates with C, C++, Java, Rust, Fortran |
| **Strong AI/ML Ecosystem** | Industry standard for all AI research and production |
| **Active Development** | New releases yearly with major improvements |

---

### ❌ Disadvantages of Python

| Disadvantage | Details |
|-------------|---------|
| **Speed** | Slower than C, C++, Go, Rust for CPU-intensive tasks |
| **GIL (Global Interpreter Lock)** | CPython allows only one thread to run at a time |
| **Mobile Development** | Not ideal for iOS/Android apps (though Kivy exists) |
| **Memory Usage** | Higher memory consumption than low-level languages |
| **Runtime Errors** | Dynamic typing means bugs may appear only at runtime |
| **Not for Embedded Systems** | Limited use in firmware/microcontrollers (MicroPython helps) |

> **⚠️ Important:** Python's "slowness" is largely irrelevant for AI/ML work because the heavy computation (neural networks, matrix operations) runs in C/CUDA under the hood via NumPy, PyTorch, etc.

---

### 🌐 Python Ecosystem

```
Python Ecosystem
├── Web Development        → Django, Flask, FastAPI
├── Data Science           → NumPy, Pandas, Matplotlib, Seaborn
├── Machine Learning       → scikit-learn, XGBoost, LightGBM
├── Deep Learning          → PyTorch, TensorFlow, Keras, JAX
├── NLP                    → spaCy, NLTK, Transformers (Hugging Face)
├── LLM Engineering        → LangChain, LlamaIndex, OpenAI SDK
├── AI Agents              → AutoGen, CrewAI, LangGraph
├── Computer Vision        → OpenCV, Pillow, YOLO
├── Data Engineering       → Apache Spark (PySpark), Airflow, dbt
├── DevOps/Cloud           → Boto3, Fabric, Ansible
├── Security/Pentesting    → Scapy, Impacket, PyCrypto
├── Automation             → Selenium, Playwright, PyAutoGUI
├── Testing                → pytest, unittest, Hypothesis
├── API Development        → FastAPI, Flask-RESTful, aiohttp
├── Database               → SQLAlchemy, Peewee, Tortoise-ORM
└── Robotics               → ROS 2 (rclpy), PyRobot
```

---

### 💼 Use Cases

#### 🌐 Web Development
```python
# FastAPI — modern, fast, async-ready web framework
from fastapi import FastAPI

app = FastAPI()

@app.get("/hello/{name}")
async def greet(name: str):
    return {"message": f"Hello, {name}!"}
```

#### 🤖 Machine Learning
```python
# scikit-learn — train a classifier in 5 lines
from sklearn.ensemble import RandomForestClassifier
from sklearn.datasets import load_iris

X, y = load_iris(return_X_y=True)
model = RandomForestClassifier()
model.fit(X, y)
print(f"Accuracy: {model.score(X, y):.2%}")
```

#### 🧠 LLM Engineering
```python
# OpenAI SDK — call GPT-4 in 10 lines
from openai import OpenAI

client = OpenAI()
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Explain transformers."}]
)
print(response.choices[0].message.content)
```

#### 🔐 Cybersecurity
```python
# Network scanning with Scapy
from scapy.all import ARP, Ether, srp

def scan(ip_range):
    arp = ARP(pdst=ip_range)
    ether = Ether(dst="ff:ff:ff:ff:ff:ff")
    packet = ether / arp
    result = srp(packet, timeout=3, verbose=False)[0]
    return [received.psrc for sent, received in result]
```

---

### 🎯 Career Paths with Python

| Career Path | Key Skills | Avg Salary (India) | Avg Salary (USA) |
|-------------|-----------|-------------------|-----------------|
| Software Engineer | Python, OOP, DSA, Git | ₹6–15 LPA | $80–120K |
| Backend Engineer | FastAPI/Django, SQL, Docker | ₹8–20 LPA | $90–140K |
| Data Scientist | Pandas, ML, Statistics | ₹8–18 LPA | $95–150K |
| ML Engineer | PyTorch, MLOps, Cloud | ₹12–30 LPA | $120–180K |
| AI Engineer | LLMs, RAG, Agents | ₹15–40 LPA | $130–200K |
| LLM Engineer | LangChain, Fine-tuning | ₹18–50 LPA | $140–220K |
| Research Engineer | JAX, Papers, CUDA | ₹20–60 LPA | $150–250K |
| DevOps Engineer | Ansible, Boto3, CI/CD | ₹8–20 LPA | $100–160K |
| Security Engineer | Scapy, Pentesting, CTF | ₹8–20 LPA | $100–160K |

---

### 🗺️ Learning Roadmap Overview

```mermaid
flowchart TD
    A[🖥️ Computer Setup] --> B[🐍 Python Basics]
    B --> C[🔧 OOP & Modules]
    C --> D[📁 File Handling & APIs]
    D --> E[🌿 Git & GitHub]
    E --> F[🧮 DSA & Algorithms]
    F --> G[🗃️ SQL & Databases]
    G --> H[🐧 Linux & Terminal]
    H --> I[🐳 Docker & DevOps]
    I --> J[📊 Data Science]
    J --> K[🤖 Machine Learning]
    K --> L[🧠 Deep Learning]
    L --> M[💬 NLP & Transformers]
    M --> N[🔮 LLM Engineering]
    N --> O[🔗 RAG Systems]
    O --> P[🤖 AI Agents]
    P --> Q[⚛️ Quantum AI]

    style A fill:#4CAF50,color:#fff
    style Q fill:#9C27B0,color:#fff
    style N fill:#2196F3,color:#fff
```

---

## Section 2 — System Requirements

### 💻 Hardware Requirements by Level

#### Windows

| Component | Minimum | Recommended | Professional | AI/ML Ready |
|-----------|---------|-------------|--------------|-------------|
| **CPU** | Intel Core i3 / AMD Ryzen 3 | Intel Core i5 / Ryzen 5 | Intel Core i7 / Ryzen 7 | Intel Core i9 / Ryzen 9 / Threadripper |
| **RAM** | 4 GB | 8 GB | 16 GB | 32–64 GB |
| **Storage** | 128 GB HDD | 256 GB SSD | 512 GB NVMe SSD | 1 TB+ NVMe SSD |
| **GPU** | Integrated Graphics | Dedicated (GTX 1060) | RTX 3060 / 4060 | RTX 4090 / A100 |
| **Internet** | 5 Mbps | 25 Mbps | 100 Mbps | 1 Gbps |
| **Display** | 1280×720 | 1920×1080 | 2560×1440 | 4K (3840×2160) |
| **OS Version** | Windows 10 | Windows 10 22H2 | Windows 11 | Windows 11 + WSL2 |

#### macOS

| Component | Minimum | Recommended | Professional | AI/ML Ready |
|-----------|---------|-------------|--------------|-------------|
| **Chip** | Intel Core i5 | Intel Core i7 / M1 | M2 / M2 Pro | M3 Max / M4 Max |
| **RAM** | 8 GB | 16 GB | 32 GB | 64–128 GB Unified |
| **Storage** | 256 GB | 512 GB SSD | 1 TB SSD | 2 TB SSD |
| **OS Version** | macOS 12 Monterey | macOS 13 Ventura | macOS 14 Sonoma | macOS 15 Sequoia |

> **💡 Apple Silicon (M1/M2/M3/M4) Note:** Apple Silicon Macs are exceptional for local AI/ML work because the unified memory architecture shares CPU and GPU RAM, allowing models like LLaMA 3 to run efficiently. Always install the `arm64` version of tools.

#### Linux

| Component | Minimum | Recommended | Professional | AI/ML Ready |
|-----------|---------|-------------|--------------|-------------|
| **CPU** | Dual-core 64-bit | Quad-core | 8-core | 16–32 core |
| **RAM** | 2 GB | 8 GB | 16 GB | 64 GB+ |
| **Storage** | 20 GB | 100 GB SSD | 500 GB NVMe | 2 TB NVMe RAID |
| **GPU** | None | NVIDIA GTX 1060 | NVIDIA RTX 3080 | NVIDIA A100 / H100 |

---

### 🖥️ Supported Operating Systems

| OS | Version | Status | Notes |
|----|---------|--------|-------|
| Windows 10 | 21H2, 22H2 | ✅ Supported | Use WSL2 for Linux tools |
| Windows 11 | 22H2, 23H2, 24H2 | ✅ Recommended | Best Windows experience |
| macOS Intel | 12, 13, 14 | ✅ Supported | x86_64 builds |
| macOS Apple Silicon | 12, 13, 14, 15 | ✅ Recommended | arm64 builds |
| Ubuntu | 20.04, 22.04, 24.04 LTS | ✅ Best for Linux | Most packages available |
| Debian | 11 Bullseye, 12 Bookworm | ✅ Supported | Stable, minimal |
| Fedora | 39, 40, 41 | ✅ Supported | Cutting-edge packages |
| Arch Linux | Rolling release | ✅ For power users | Maximum control |
| Pop!_OS | 22.04 | ✅ Recommended for GPU | Best NVIDIA support |

---

## Section 3 — Python Installation

### Understanding Python Versions

Before installing, understand the version numbering:

```
Python 3 . 12 . 3
        │    │    └── Patch (bug fixes)
        │    └─────── Minor (new features, backward compatible)
        └──────────── Major (breaking changes)
```

**Which version should you install?**
- Use the **latest stable release** (Python 3.12.x as of 2025)
- Never use Python 2.x — it is end-of-life
- For AI/ML projects, Python 3.10+ is required for many libraries

---

### 🪟 Windows Installation

#### Method 1: Official Installer (Recommended for Beginners)

**Step 1: Download Python**

1. Open your web browser
2. Navigate to: `https://www.python.org/downloads/`
3. Click the large yellow **"Download Python 3.12.x"** button
4. This downloads a file named something like `python-3.12.3-amd64.exe`

> 📸 *[Screenshot: python.org download page with yellow download button highlighted]*

**Step 2: Run the Installer**

1. Locate the downloaded `.exe` file (usually in your `Downloads` folder)
2. **Right-click → Run as Administrator** (important!)
3. On the first screen, you will see two checkboxes at the bottom:

```
☑ Install launcher for all users (recommended)
☑ Add Python 3.12 to PATH    ← CRITICAL: CHECK THIS BOX
```

> ⚠️ **WARNING:** If you forget to check **"Add Python 3.12 to PATH"**, Python will install but you won't be able to run it from the command line. You would need to uninstall and reinstall.

4. Click **"Install Now"** for default installation
   — OR —
   Click **"Customize installation"** for advanced options (recommended if you want to choose install location)

**Step 3: Customized Installation (Recommended)**

If you clicked "Customize installation":

- **Optional Features** screen: Check ALL boxes
  - `☑ pip` — Python's package installer
  - `☑ tcl/tk and IDLE` — built-in IDE
  - `☑ Python test suite`
  - `☑ py launcher`
  - `☑ for all users`

- **Advanced Options** screen:
  - `☑ Install for all users`
  - `☑ Add Python to environment variables`
  - `☑ Create shortcuts for installed applications`
  - `☑ Add Python to PATH`
  - Change install path to: `C:\Python312` (simpler path = fewer issues)

**Step 4: Verify Installation**

Open **Command Prompt** (`Win + R` → type `cmd` → press Enter):

```cmd
python --version
```

Expected output:
```
Python 3.12.3
```

Also verify pip (Python's package installer):
```cmd
pip --version
```

Expected output:
```
pip 24.0 from C:\Python312\Lib\site-packages\pip (python 3.12)
```

---

#### Method 2: Microsoft Store

1. Open **Microsoft Store** (search in Start Menu)
2. Search for **"Python 3.12"**
3. Click **Get** / **Install**
4. Python installs automatically and is added to PATH

> **Note:** The Microsoft Store version has some limitations with certain packages and PATH configurations. The official installer is preferred for development work.

---

#### Method 3: Winget (Windows Package Manager)

Winget is Windows' built-in package manager (similar to `apt` on Linux).

Open **PowerShell as Administrator**:

```powershell
# Check if winget is available
winget --version

# Search for Python
winget search Python.Python

# Install Python 3.12
winget install Python.Python.3.12

# Verify
python --version
```

---

#### Windows PATH Troubleshooting

If `python` is not recognized after installation:

**Method A: Automatic PATH Fix**

```cmd
# Open Python installer again, click "Modify"
# Check "Add Python to environment variables"
```

**Method B: Manual PATH Configuration**

1. Press `Win + S`, search **"Environment Variables"**
2. Click **"Edit the system environment variables"**
3. Click **"Environment Variables"** button
4. Under **System variables**, find and select **"Path"**
5. Click **"Edit"**
6. Click **"New"** and add:
   ```
   C:\Python312
   C:\Python312\Scripts
   ```
7. Click **OK** on all windows
8. **Restart your terminal** (important!)

**Method C: Using PowerShell**

```powershell
# Add Python to PATH permanently via PowerShell
[Environment]::SetEnvironmentVariable(
    "Path",
    $env:Path + ";C:\Python312;C:\Python312\Scripts",
    "Machine"
)
```

---

### 🍎 macOS Installation

#### Method 1: Official Installer

1. Go to `https://www.python.org/downloads/`
2. Download the macOS installer (`.pkg` file)
   - For **Apple Silicon (M1/M2/M3/M4)**: Download `python-3.12.x-macos11.pkg`
   - For **Intel Mac**: Same file works
3. Double-click the `.pkg` file
4. Follow the installation wizard
5. Open **Terminal** (`Cmd + Space` → type `terminal`)

```bash
# Verify installation
python3 --version
pip3 --version
```

> **💡 macOS Note:** macOS ships with a system Python 2.7 (on older versions) or Python 3. Never delete or modify the system Python. Always use a separately installed Python 3 for your work.

---

#### Method 2: Homebrew (Recommended for macOS)

**Homebrew** is the most popular package manager for macOS. Think of it like an App Store for command-line tools.

**Step 1: Install Homebrew**

```bash
# This command downloads and installs Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

This script will:
- Install Xcode Command Line Tools (if not present)
- Download Homebrew
- Add Homebrew to your PATH

**Step 2: For Apple Silicon — Add Homebrew to PATH**

```bash
# Apple Silicon Macs install Homebrew to /opt/homebrew
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

**Step 3: Verify Homebrew**

```bash
brew --version
brew doctor  # Should say "Your system is ready to brew."
```

**Step 4: Install Python**

```bash
# Install latest Python
brew install python@3.12

# Install multiple versions (optional)
brew install python@3.11

# Verify
python3 --version
pip3 --version
```

**Step 5: Set Python 3 as Default**

```bash
# Add to ~/.zshrc (macOS default shell since Catalina)
echo 'export PATH="/opt/homebrew/opt/python@3.12/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc

# Verify
python3 --version
```

---

#### Method 3: pyenv (Best for Managing Multiple Python Versions)

`pyenv` allows you to install and switch between multiple Python versions effortlessly.

```bash
# Install pyenv via Homebrew
brew install pyenv

# Add pyenv to shell configuration
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc

# Reload shell
source ~/.zshrc

# See all available Python versions
pyenv install --list

# Install a specific version
pyenv install 3.12.3
pyenv install 3.11.9

# Set global (default) Python version
pyenv global 3.12.3

# Set local version (for a specific project folder)
cd my-project
pyenv local 3.11.9

# Verify
python --version
pyenv versions  # Shows all installed versions
```

---

### 🐧 Linux Installation

#### Ubuntu / Debian

**Ubuntu 22.04+ comes with Python 3.10. Here's how to get Python 3.12:**

```bash
# Update package list
sudo apt update

# Upgrade existing packages
sudo apt upgrade -y

# Install prerequisites
sudo apt install -y software-properties-common

# Add deadsnakes PPA (Personal Package Archive) — has latest Python versions
sudo add-apt-repository ppa:deadsnakes/ppa

# Update again after adding PPA
sudo apt update

# Install Python 3.12
sudo apt install -y python3.12 python3.12-venv python3.12-dev

# Install pip
sudo apt install -y python3-pip

# Verify
python3.12 --version
pip3 --version

# (Optional) Make python3.12 the default python3
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.12 1
sudo update-alternatives --config python3  # Choose your preferred version

# Alias python to python3 (add to ~/.bashrc)
echo "alias python=python3" >> ~/.bashrc
echo "alias pip=pip3" >> ~/.bashrc
source ~/.bashrc
```

---

#### Fedora

```bash
# Fedora's package manager is DNF
# Update system
sudo dnf update -y

# Install Python 3.12
sudo dnf install -y python3.12 python3.12-devel python3-pip

# Verify
python3.12 --version
pip3 --version

# Install development tools (compilers, headers — needed for some Python packages)
sudo dnf groupinstall -y "Development Tools"
sudo dnf install -y python3-devel
```

---

#### Arch Linux

```bash
# Arch uses pacman — Python is available in core repos
# Update everything
sudo pacman -Syu

# Install Python
sudo pacman -S python python-pip

# Verify
python --version  # Arch links python to python3 by default
pip --version

# Install build dependencies (for compiling packages)
sudo pacman -S base-devel
```

---

#### Building Python from Source (All Linux Distros)

For maximum control or when your distro doesn't have the latest version:

```bash
# Install build dependencies (Ubuntu)
sudo apt install -y build-essential libssl-dev libffi-dev python3-dev \
    zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev libncurses5-dev \
    libgdbm-dev liblzma-dev uuid-dev

# Download Python source
wget https://www.python.org/ftp/python/3.12.3/Python-3.12.3.tgz

# Extract
tar -xzf Python-3.12.3.tgz
cd Python-3.12.3

# Configure (--enable-optimizations makes Python ~10% faster)
./configure --enable-optimizations --with-lto

# Compile using all CPU cores
make -j$(nproc)

# Install (altinstall prevents overwriting system python3)
sudo make altinstall

# Verify
python3.12 --version
```

---

## Section 4 — Python Environment Management

### 🌍 Understanding the Problem

Imagine you're working on two projects:
- **Project A** needs `Django 4.2`
- **Project B** needs `Django 3.2`

If you install both globally, they'll conflict. **Virtual environments** solve this by creating isolated Python environments per project — each with its own packages.

```mermaid
graph LR
    subgraph "Global Python"
        G[Python 3.12]
    end
    subgraph "Project A (venv)"
        A1[Python 3.12 copy]
        A2[Django 4.2]
        A3[requests 2.31]
    end
    subgraph "Project B (venv)"
        B1[Python 3.12 copy]
        B2[Django 3.2]
        B3[requests 2.28]
    end
    G --> A1
    G --> B1
```

---

### 📦 Virtual Environment Tools Comparison

| Feature | venv | virtualenv | pipenv | poetry | conda |
|---------|------|------------|--------|--------|-------|
| **Built-in** | ✅ Yes | ❌ No | ❌ No | ❌ No | ❌ No |
| **Python version mgmt** | ❌ No | ❌ No | ⚠️ Limited | ⚠️ Limited | ✅ Yes |
| **Dependency resolution** | ❌ Basic | ❌ Basic | ✅ Yes | ✅ Yes | ✅ Yes |
| **Lock file** | ❌ No | ❌ No | ✅ Pipfile.lock | ✅ poetry.lock | ✅ environment.yml |
| **Package publishing** | ❌ No | ❌ No | ❌ No | ✅ Yes | ❌ No |
| **Learning curve** | 🟢 Easy | 🟢 Easy | 🟡 Medium | 🟡 Medium | 🔴 High |
| **Industry usage** | 🔥 Universal | 🔥 High | 🔵 Medium | 🔥 Growing | 🔥 Data Science |
| **Speed** | ⚡ Fast | ⚡ Fast | 🐢 Slow | ⚡ Fast | 🐢 Slow |

---

### 🔵 venv — Built-in Virtual Environments

`venv` is built into Python 3.3+ and is the simplest way to create virtual environments.

```bash
# --- WINDOWS ---

# Create virtual environment (creates a folder called 'venv')
python -m venv venv

# Activate it
venv\Scripts\activate

# Your prompt will change:
# (venv) C:\Users\YourName\project>

# Install packages (only into this venv)
pip install requests numpy pandas

# See what's installed
pip list

# Save dependencies to a file
pip freeze > requirements.txt

# Deactivate when done
deactivate
```

```bash
# --- macOS / Linux ---

# Create virtual environment
python3 -m venv venv

# Activate it
source venv/bin/activate

# Your prompt changes:
# (venv) user@computer:~/project$

# Install packages
pip install requests numpy pandas

# Save dependencies
pip freeze > requirements.txt

# Deactivate
deactivate
```

**The `requirements.txt` file looks like:**

```txt
numpy==1.26.4
pandas==2.2.0
requests==2.31.0
scikit-learn==1.4.0
```

**To recreate an environment from `requirements.txt`:**

```bash
# Create new venv
python -m venv venv

# Activate it
source venv/bin/activate  # or venv\Scripts\activate on Windows

# Install all packages from file
pip install -r requirements.txt
```

---

### 🟡 Poetry — Modern Dependency Management

Poetry is the modern standard for Python projects that need professional dependency management and package publishing.

```bash
# Install Poetry
# macOS / Linux
curl -sSL https://install.python-poetry.org | python3 -

# Windows (PowerShell)
(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -

# Verify
poetry --version

# Create a new project with Poetry
poetry new my-project
cd my-project

# The structure Poetry creates:
# my-project/
# ├── pyproject.toml    ← configuration & dependencies
# ├── README.md
# ├── my_project/
# │   └── __init__.py
# └── tests/
#     └── __init__.py

# Add a dependency
poetry add requests
poetry add numpy pandas

# Add a dev-only dependency (only for testing/development)
poetry add --group dev pytest black ruff

# Install all dependencies
poetry install

# Activate the virtual environment Poetry manages
poetry shell

# Run a script inside the Poetry environment without activating
poetry run python main.py

# Show installed packages
poetry show

# Update all packages
poetry update

# Export to requirements.txt (for compatibility)
poetry export -f requirements.txt --output requirements.txt
```

**`pyproject.toml` (Poetry's configuration file):**

```toml
[tool.poetry]
name = "my-project"
version = "0.1.0"
description = "A sample Python project"
authors = ["Baghel <baghel@example.com>"]
readme = "README.md"

[tool.poetry.dependencies]
python = "^3.12"
requests = "^2.31.0"
numpy = "^1.26.4"
pandas = "^2.2.0"

[tool.poetry.group.dev.dependencies]
pytest = "^8.0.0"
black = "^24.0.0"
ruff = "^0.4.0"

[build-system]
requires = ["poetry-core"]
build-backend = "poetry.core.masonry.api"
```

---

### 🔮 pyenv — Python Version Management

`pyenv` lets you install and switch between Python versions without conflicting with the system Python.

```bash
# Install pyenv (macOS/Linux)
# Already covered in Section 3 — Method 3

# For Windows, use pyenv-win:
# PowerShell
Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"

# List all Python versions available
pyenv install --list | grep "3\."

# Install Python 3.12.3
pyenv install 3.12.3

# Install Python 3.11.9
pyenv install 3.11.9

# See all installed versions
pyenv versions

# Set global default
pyenv global 3.12.3

# Set local version (only for current directory)
pyenv local 3.11.9

# Check active version
python --version
pyenv version

# Combine pyenv + venv (recommended workflow)
pyenv global 3.12.3
python -m venv .venv
source .venv/bin/activate
```

---

### ✅ Recommended Workflow

```bash
# 1. For a new project (start here)
mkdir my-project && cd my-project

# 2. Create virtual environment
python3 -m venv .venv

# 3. Activate it
source .venv/bin/activate  # macOS/Linux
# .venv\Scripts\activate   # Windows

# 4. Upgrade pip (always do this first)
pip install --upgrade pip

# 5. Install your packages
pip install numpy pandas requests fastapi

# 6. Save your dependencies
pip freeze > requirements.txt

# 7. When done
deactivate
```

> **💡 Pro Tip:** Name your virtual environment `.venv` (with a dot) so it's hidden by default in file explorers and auto-detected by VS Code.

---

## Section 5 — Visual Studio Code Setup

### What is VS Code?

**Visual Studio Code** (VS Code) is a free, open-source code editor made by Microsoft. It has become the world's most popular code editor (70%+ of developers use it according to Stack Overflow surveys) because:

- Lightning fast startup
- Massive extension marketplace
- Built-in Git integration
- IntelliSense (intelligent code completion)
- Integrated terminal
- Remote development (SSH, containers, WSL)
- Free forever

---

### 📥 Installation

**Windows:**
1. Go to `https://code.visualstudio.com/`
2. Click **"Download for Windows"**
3. Run the installer
4. **Important checkboxes during install:**
   - `☑ Add "Open with Code" action to Windows Explorer file context menu`
   - `☑ Add "Open with Code" action to Windows Explorer directory context menu`
   - `☑ Add to PATH`

**macOS:**
```bash
# Via Homebrew (recommended)
brew install --cask visual-studio-code

# Or download from https://code.visualstudio.com/
# Drag VS Code.app to Applications folder
# Then add to PATH:
# In VS Code: Cmd+Shift+P → type "Shell Command: Install 'code' command in PATH"
```

**Linux:**
```bash
# Ubuntu/Debian
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
sudo apt update
sudo apt install code

# Fedora
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
sudo dnf install code

# Arch
yay -S visual-studio-code-bin  # Using AUR
```

---

### ⚙️ Essential Settings (`settings.json`)

Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on macOS) → type **"Open User Settings JSON"**

```json
{
  // Python Settings
  "python.defaultInterpreterPath": "${workspaceFolder}/.venv/bin/python",
  "python.terminal.activateEnvironment": true,
  "python.languageServer": "Pylance",

  // Editor Settings
  "editor.fontSize": 14,
  "editor.fontFamily": "'JetBrains Mono', 'Fira Code', Consolas, monospace",
  "editor.fontLigatures": true,
  "editor.tabSize": 4,
  "editor.insertSpaces": true,
  "editor.rulers": [79, 120],
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.organizeImports": "explicit",
    "source.fixAll.ruff": "explicit"
  },

  // File Settings
  "files.trimTrailingWhitespace": true,
  "files.insertFinalNewline": true,
  "files.exclude": {
    "**/__pycache__": true,
    "**/.pytest_cache": true,
    "**/.mypy_cache": true,
    "**/.ruff_cache": true
  },

  // Terminal Settings
  "terminal.integrated.fontSize": 13,
  "terminal.integrated.defaultProfile.linux": "bash",
  "terminal.integrated.defaultProfile.osx": "zsh",
  "terminal.integrated.defaultProfile.windows": "PowerShell",

  // Git Settings
  "git.autofetch": true,
  "git.confirmSync": false,

  // Theme (adjust to your preference)
  "workbench.colorTheme": "One Dark Pro",
  "workbench.iconTheme": "material-icon-theme",

  // Formatting
  "[python]": {
    "editor.defaultFormatter": "charliermarsh.ruff"
  }
}
```

---

### 🔌 Essential Extensions

Open VS Code → Press `Ctrl+Shift+X` to open Extensions panel

#### Core Python Extensions

| Extension | Publisher | Purpose | Install Command |
|-----------|-----------|---------|----------------|
| **Python** | Microsoft | Core Python support | `ext install ms-python.python` |
| **Pylance** | Microsoft | Fast IntelliSense, type checking | `ext install ms-python.vscode-pylance` |
| **Ruff** | Astral Software | Fast Python linter & formatter | `ext install charliermarsh.ruff` |
| **Jupyter** | Microsoft | Run Jupyter notebooks in VS Code | `ext install ms-toolsai.jupyter` |
| **Python Debugger** | Microsoft | Advanced debugging | `ext install ms-python.debugpy` |

#### AI & Productivity Extensions

| Extension | Publisher | Purpose |
|-----------|-----------|---------|
| **GitHub Copilot** | GitHub | AI code completion |
| **GitLens** | GitKraken | Advanced Git visualization |
| **Error Lens** | Alexander | Inline error messages |
| **Better Comments** | Aaron Bond | Color-coded comments |
| **Todo Tree** | Gruntfuggly | Track TODO/FIXME in code |
| **Path Intellisense** | Christian Kohler | Autocomplete file paths |
| **IntelliCode** | Microsoft | AI-assisted IntelliSense |

#### Code Quality & Documentation

| Extension | Publisher | Purpose |
|-----------|-----------|---------|
| **Code Spell Checker** | Street Side Software | Catches typos in code and comments |
| **Markdown All in One** | Yu Zhang | Markdown preview & shortcuts |
| **autoDocstring** | Nils Werner | Auto-generate Python docstrings |
| **indent-rainbow** | oderwat | Color-codes indentation levels |
| **Bracket Pair Colorization** | Built-in VS Code | Colors matching brackets |

#### Infrastructure & DevOps

| Extension | Publisher | Purpose |
|-----------|-----------|---------|
| **Docker** | Microsoft | Docker container management |
| **Remote - SSH** | Microsoft | Develop on remote servers |
| **Remote - WSL** | Microsoft | Develop in WSL on Windows |
| **YAML** | Red Hat | YAML validation & completion |
| **Prettier** | Prettier | Format JSON, YAML, JS files |
| **DotENV** | mikestead | Syntax highlighting for .env files |

#### Install All at Once (Terminal)

```bash
# Install all essential Python extensions at once
code --install-extension ms-python.python
code --install-extension ms-python.vscode-pylance
code --install-extension charliermarsh.ruff
code --install-extension ms-toolsai.jupyter
code --install-extension ms-python.debugpy
code --install-extension eamodio.gitlens
code --install-extension usernamehw.errorlens
code --install-extension aaron-bond.better-comments
code --install-extension streetsidesoftware.code-spell-checker
code --install-extension ms-azuretools.vscode-docker
code --install-extension PKief.material-icon-theme
code --install-extension zhuangtongfa.material-theme
```

---

### 🎨 Recommended Themes

| Theme | Description | Install |
|-------|-------------|---------|
| **One Dark Pro** | Most popular dark theme | `ext install zhuangtongfa.material-theme` |
| **Dracula** | High-contrast dark theme | `ext install dracula-theme.theme-dracula` |
| **Tokyo Night** | Elegant blue/purple dark theme | `ext install enkia.tokyo-night` |
| **GitHub Theme** | Official GitHub light/dark | `ext install GitHub.github-vscode-theme` |
| **Catppuccin** | Warm pastel theme | `ext install Catppuccin.catppuccin-vsc` |

---

### 🐛 Debugging Python in VS Code

Create a `.vscode/launch.json` file in your project:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Python: Current File",
      "type": "debugpy",
      "request": "launch",
      "program": "${file}",
      "console": "integratedTerminal",
      "justMyCode": true
    },
    {
      "name": "Python: FastAPI",
      "type": "debugpy",
      "request": "launch",
      "module": "uvicorn",
      "args": ["main:app", "--reload"],
      "jinja": true
    },
    {
      "name": "Python: pytest",
      "type": "debugpy",
      "request": "launch",
      "module": "pytest",
      "args": ["tests/", "-v"]
    }
  ]
}
```

**Debugging keyboard shortcuts:**

| Action | Windows/Linux | macOS |
|--------|--------------|-------|
| Start debugging | `F5` | `F5` |
| Stop debugging | `Shift+F5` | `Shift+F5` |
| Step over (next line) | `F10` | `F10` |
| Step into function | `F11` | `F11` |
| Step out of function | `Shift+F11` | `Shift+F11` |
| Toggle breakpoint | `F9` | `F9` |

---

## Section 6 — PyCharm Setup

### PyCharm vs VS Code

| Feature | PyCharm Community | PyCharm Professional | VS Code + Extensions |
|---------|------------------|---------------------|----------------------|
| **Cost** | Free | ~$249/year | Free |
| **Python support** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| **Jupyter support** | ❌ | ✅ | ✅ |
| **Remote dev** | ❌ | ✅ | ✅ |
| **Database tools** | ❌ | ✅ | Via extensions |
| **Web frameworks** | ❌ | ✅ (Django, Flask, FastAPI) | Via extensions |
| **Profiling** | ❌ | ✅ | Limited |
| **Refactoring** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |
| **Startup speed** | 🐢 Slow | 🐢 Slow | ⚡ Fast |

> **Recommendation:** Use **VS Code** for daily work (lighter, faster, more versatile). Use **PyCharm Community** when you need advanced Python refactoring, or **PyCharm Professional** for enterprise web development.

---

### 📥 PyCharm Installation

```bash
# macOS via Homebrew
brew install --cask pycharm-ce      # Community (free)
brew install --cask pycharm         # Professional (paid)

# Linux via Snap
sudo snap install pycharm-community --classic
sudo snap install pycharm-professional --classic

# Or download from https://www.jetbrains.com/pycharm/download/
```

---

### ⚙️ Initial PyCharm Configuration

**Setting up the Python Interpreter:**

1. Open PyCharm → Create or Open a project
2. Go to `File → Settings` (Windows/Linux) or `PyCharm → Settings` (macOS)
3. Navigate to `Project → Python Interpreter`
4. Click the gear icon ⚙️ → `Add Interpreter`
5. Choose `Virtualenv Environment` → `New environment`
6. Select base Python: `/usr/bin/python3.12` or `C:\Python312\python.exe`
7. Click **OK**

**Essential PyCharm Plugins:**

Go to `Settings → Plugins → Marketplace`:

- `.ignore` — .gitignore support
- `Rainbow Brackets` — Color matching brackets
- `Key Promoter X` — Teaches keyboard shortcuts
- `GitHub Copilot` — AI assistance
- `String Manipulation` — Transform strings
- `Makefile Language` — Makefile support

---

## Section 7 — Git Installation

### 🌿 What is Git?

**Git** is a **distributed version control system** created by **Linus Torvalds** (the same person who created Linux) in 2005. He built it in just 10 days because he was dissatisfied with existing version control tools.

**Why does Git exist?**
- To track every change ever made to code
- To allow multiple people to work on the same project simultaneously
- To allow "time travel" — go back to any previous version
- To create separate branches for experiments without affecting working code
- To back up code remotely

**Without Git, software development would look like:**
```
project_final.py
project_final_v2.py
project_FINAL_ACTUALLY_FINAL.py
project_backup_monday.py
project_for_presentation.py
```

**With Git:**
```bash
git log --oneline
a3f7d9e feat: add user authentication
b2c1a8f fix: resolve login bug
c9d4e3a feat: add database connection
...
```

---

### 🏗️ Git Architecture

```mermaid
flowchart LR
    subgraph "Your Computer"
        WD[📁 Working Directory\nYour actual files]
        SA[📋 Staging Area\ngit add]
        LR[🗄️ Local Repository\n.git folder]
    end
    subgraph "Remote"
        RR[☁️ Remote Repository\nGitHub / GitLab]
    end

    WD -->|git add| SA
    SA -->|git commit| LR
    LR -->|git push| RR
    RR -->|git pull / clone| WD
    LR -->|git fetch| LR

    style WD fill:#4CAF50,color:#fff
    style SA fill:#FF9800,color:#fff
    style LR fill:#2196F3,color:#fff
    style RR fill:#9C27B0,color:#fff
```

**Understanding the four areas:**

| Area | Location | Description |
|------|----------|-------------|
| **Working Directory** | Your project folder | Files you're actively editing |
| **Staging Area** | `.git/index` | Changes prepared for the next commit |
| **Local Repository** | `.git/` folder | Complete history of all commits |
| **Remote Repository** | GitHub/GitLab server | Shared backup accessible to collaborators |

---

### 📥 Install Git

**Windows:**

```powershell
# Method 1: Official installer
# Download from https://git-scm.com/download/win
# Run the installer with these settings:
# - Default editor: Visual Studio Code
# - Initial branch name: main
# - PATH: "Git from the command line and also from 3rd-party software"
# - Line ending: "Checkout Windows-style, commit Unix-style line endings"

# Method 2: Winget
winget install --id Git.Git -e --source winget

# Method 3: Chocolatey
choco install git

# Verify
git --version
```

**macOS:**

```bash
# macOS may already have Git installed (via Xcode)
git --version  # If not found, it prompts to install Xcode CLT

# Install via Homebrew (recommended — gives you latest version)
brew install git

# Verify
git --version
which git  # Should show /opt/homebrew/bin/git, not /usr/bin/git
```

**Linux:**

```bash
# Ubuntu/Debian
sudo apt update
sudo apt install -y git git-lfs

# Fedora
sudo dnf install -y git git-lfs

# Arch
sudo pacman -S git git-lfs

# Verify
git --version
```

---

## Section 8 — Git Configuration

After installing Git, you MUST configure it before using it. These settings are stored in `~/.gitconfig`.

### 🔧 Essential Configuration

```bash
# Set your name (shows in every commit you make — use your real name)
git config --global user.name "Your Full Name"

# Set your email (MUST match your GitHub email for contributions to be attributed)
git config --global user.email "you@example.com"

# Set default branch name to 'main' (industry standard since 2020)
git config --global init.defaultBranch main

# Set VS Code as default editor for Git messages
git config --global core.editor "code --wait"

# Or use nano (easier for beginners in terminal)
git config --global core.editor "nano"

# Configure line ending handling
# Windows
git config --global core.autocrlf true

# macOS / Linux
git config --global core.autocrlf input

# Enable colorized output (makes git output much more readable)
git config --global color.ui auto

# Set pull strategy (rebase keeps history cleaner)
git config --global pull.rebase false

# Store credentials in memory temporarily (avoid re-entering password)
git config --global credential.helper cache

# Windows: Store credentials in Windows Credential Manager
git config --global credential.helper manager

# macOS: Store in macOS Keychain
git config --global credential.helper osxkeychain

# View all your configuration
git config --list

# View global config file directly
cat ~/.gitconfig
```

**Your `~/.gitconfig` should look like:**

```ini
[user]
    name = Baghel
    email = baghel@example.com

[core]
    editor = code --wait
    autocrlf = input

[init]
    defaultBranch = main

[color]
    ui = auto

[pull]
    rebase = false

[credential]
    helper = osxkeychain
```

---

### 🎨 Useful Git Aliases

Aliases are shortcuts for long Git commands:

```bash
# Short status
git config --global alias.st status

# Short log with graph
git config --global alias.lg "log --oneline --graph --all --decorate"

# Undo last commit but keep changes
git config --global alias.undo "reset HEAD~1 --mixed"

# List all branches
git config --global alias.br "branch -a"

# Quick commit
git config --global alias.cm "commit -m"

# Usage examples:
git st          # same as: git status
git lg          # beautiful log graph
git cm "fix bug" # same as: git commit -m "fix bug"
```

---

## Section 9 — GitHub Setup

### What is GitHub?

**GitHub** is a cloud-based platform built on top of Git. It provides:
- Remote storage for your Git repositories
- Collaboration tools (pull requests, code reviews)
- Issue tracking
- Project management boards
- CI/CD automation (GitHub Actions)
- Free hosting for static websites (GitHub Pages)
- Portfolio showcase for developers

> **Git** is the tool. **GitHub** is the platform. They are separate things. Other platforms: **GitLab**, **Bitbucket**, **Gitea** (self-hosted).

---

### 👤 Create a GitHub Account

1. Go to `https://github.com/`
2. Click **"Sign up"**
3. Enter your email, create a password, choose a username
4. Solve the CAPTCHA puzzle
5. Verify your email address
6. Choose the **Free** plan

**Username Tips:**
- Use your real name if possible: `firstname-lastname` or `firstnamelastname`
- Avoid numbers, underscores, or silly names
- This is your professional identity — recruiters will see it

---

### 🌟 Profile Optimization

A great GitHub profile gets you noticed by recruiters and collaborators.

**Update your profile:**
1. Click your avatar → **Settings**
2. Fill in:
   - **Name**: Your real name
   - **Bio**: One line about you ("AI/ML Student | Python Developer | NIELIT Gorakhpur")
   - **Location**: Your city/country
   - **Website**: Your portfolio or LinkedIn URL
   - **Twitter/X**: Optional

**Create a Profile README:**
1. Create a new repository with the **same name as your GitHub username**
   (e.g., if your username is `baghel-dev`, create repo `baghel-dev`)
2. Check "Add a README file"
3. Edit the README.md — it will appear on your GitHub profile page!

Example profile README starter:
```markdown
# Hi, I'm Baghel 👋

🎓 CS Student @ NIELIT Gorakhpur  
🐍 Python Developer | AI/ML Enthusiast  
🔭 Currently learning: LLM Engineering & RAG Systems  
📫 Reach me: baghel@example.com

## 🛠️ Tech Stack
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/-PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![Git](https://img.shields.io/badge/-Git-F05032?style=flat&logo=git&logoColor=white)
```

---

### 📁 Creating a Repository

```bash
# Method 1: Create on GitHub, then clone locally

# 1. Go to github.com → click "+" → "New repository"
# 2. Fill in:
#    - Repository name: python-programming
#    - Description: "My Python learning journey"
#    - Visibility: Public (for portfolio) or Private
#    - Initialize: ✅ Add README, ✅ Add .gitignore (Python), ✅ Choose license (MIT)
# 3. Click "Create repository"
# 4. Click "Code" → Copy HTTPS or SSH URL
# 5. Clone to your computer:

git clone https://github.com/yourusername/python-programming.git
cd python-programming
```

```bash
# Method 2: Create locally, then push to GitHub

mkdir python-programming
cd python-programming
git init
echo "# Python Programming" > README.md
git add README.md
git commit -m "Initial commit"

# On GitHub: create a new EMPTY repository (no README)
# Then connect your local repo to it:
git remote add origin https://github.com/yourusername/python-programming.git
git branch -M main
git push -u origin main
```

---

## Section 10 — SSH Configuration

### 🔑 Why SSH?

When connecting to GitHub, you have two options:

| Protocol | Authentication | URL format | Security |
|----------|---------------|------------|---------|
| **HTTPS** | Username + Password/Token | `https://github.com/user/repo.git` | Good |
| **SSH** | Cryptographic key pair | `git@github.com:user/repo.git` | Excellent |

**SSH is preferred because:**
- No password typing — authenticate automatically
- More secure (private key never leaves your machine)
- Required for many CI/CD systems
- Industry standard for professional development

---

### 🗝️ How SSH Keys Work

```mermaid
sequenceDiagram
    participant L as Your Computer
    participant G as GitHub Server
    
    Note over L: You have: Private Key (secret) + Public Key
    Note over G: GitHub has: Your Public Key stored
    
    L->>G: "I want to connect as baghel"
    G->>L: "Prove it — decrypt this challenge"
    L->>G: (decrypts with private key)
    G->>L: "Identity verified — access granted!"
```

---

### 🔐 Generate SSH Keys

#### Option A: ED25519 (Recommended — Modern & Secure)

```bash
# Generate ED25519 key (more secure and faster than RSA)
ssh-keygen -t ed25519 -C "your-email@example.com"

# You'll be asked:
# Enter file in which to save the key: [press Enter for default]
# Enter passphrase (empty for no passphrase): [type a strong passphrase]
# Enter same passphrase again: [repeat passphrase]

# Keys are saved to:
# Private key: ~/.ssh/id_ed25519       ← NEVER share this!
# Public key:  ~/.ssh/id_ed25519.pub   ← Add this to GitHub
```

#### Option B: RSA 4096 (Compatible with older systems)

```bash
# Generate RSA 4096-bit key
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"

# Keys saved to:
# ~/.ssh/id_rsa      ← Private
# ~/.ssh/id_rsa.pub  ← Public (add to GitHub)
```

---

### ➕ Add SSH Key to GitHub

```bash
# 1. Copy your PUBLIC key content

# macOS
cat ~/.ssh/id_ed25519.pub | pbcopy    # Copies to clipboard

# Linux
cat ~/.ssh/id_ed25519.pub | xclip -selection clipboard  # or xsel

# Windows (PowerShell)
Get-Content ~/.ssh/id_ed25519.pub | Set-Clipboard

# Or just print it and manually copy
cat ~/.ssh/id_ed25519.pub
```

2. Go to GitHub → Click avatar → **Settings**
3. Left sidebar → **SSH and GPG keys**
4. Click **"New SSH key"**
5. Title: `Work Laptop` or `Home PC` (describe the computer)
6. Key type: `Authentication Key`
7. Paste your public key
8. Click **"Add SSH key"**

---

### ✅ Verify SSH Connection

```bash
# Test connection to GitHub
ssh -T git@github.com

# Expected output:
# Hi yourusername! You've successfully authenticated, but GitHub does not provide shell access.

# If it shows "Permission denied (publickey)", see troubleshooting below
```

---

### 🔧 SSH Config File

Create `~/.ssh/config` to manage multiple SSH keys:

```bash
# Create/edit SSH config
nano ~/.ssh/config
```

```
# GitHub (Personal)
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519
    AddKeysToAgent yes

# GitHub (Work account — if you have multiple)
Host github-work
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_work
    AddKeysToAgent yes
```

```bash
# Set correct permissions on SSH files
chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_ed25519
chmod 644 ~/.ssh/id_ed25519.pub
chmod 600 ~/.ssh/config
```

---

### 🔑 SSH Agent (Avoid re-entering passphrase)

```bash
# Start SSH agent
eval "$(ssh-agent -s)"

# Add your key to the agent
ssh-add ~/.ssh/id_ed25519

# macOS: Add to keychain permanently
ssh-add --apple-use-keychain ~/.ssh/id_ed25519

# Windows (PowerShell as Admin): Enable SSH agent service
Set-Service -Name ssh-agent -StartupType Automatic
Start-Service ssh-agent
ssh-add ~/.ssh/id_ed25519
```

---

## Section 11 — Professional Git Workflow

### Core Git Commands — Deep Dive

#### `git init`
Initializes a brand new, empty Git repository in the current folder.

```bash
mkdir my-project
cd my-project
git init

# Output:
# Initialized empty Git repository in /home/user/my-project/.git/

# What this does:
# Creates a hidden .git/ folder that stores ALL Git data
# You never need to touch .git/ manually

ls -la  # See the hidden .git folder
# drwxr-xr-x .git
```

---

#### `git clone`
Copies an existing remote repository to your computer.

```bash
# Clone via HTTPS
git clone https://github.com/user/repository.git

# Clone via SSH (after SSH setup)
git clone git@github.com:user/repository.git

# Clone into a specific folder name
git clone https://github.com/user/repository.git my-folder-name

# Clone only the latest commit (faster, saves disk space)
git clone --depth 1 https://github.com/user/repository.git

# Clone a specific branch
git clone -b develop https://github.com/user/repository.git
```

---

#### `git status`
Shows the current state of your working directory and staging area.

```bash
git status

# Possible outputs:
# On branch main
# Your branch is up to date with 'origin/main'.
#
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   modified:   README.md
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#   new_script.py

# Short version
git status -s
# M  README.md       (M = modified)
# ?? new_script.py   (?? = untracked)
```

---

#### `git add`
Moves changes from working directory to the staging area.

```bash
# Stage a specific file
git add README.md

# Stage multiple files
git add file1.py file2.py

# Stage all changes in current directory
git add .

# Stage all modified and new files (not deletions)
git add --all

# Interactively choose which changes to stage (advanced)
git add -p

# After staging, check status
git status
```

---

#### `git commit`
Takes a snapshot of everything in the staging area and saves it to the local repository.

```bash
# Commit with a message
git commit -m "feat: add user authentication system"

# Commit all tracked modified files (skips untracked files)
git commit -am "fix: correct login validation bug"

# Open editor for a longer commit message
git commit

# Amend the last commit (if you made a typo or forgot a file)
# WARNING: Never amend commits that have been pushed to a shared repository
git commit --amend -m "corrected commit message"
```

**✍️ Writing Good Commit Messages**

Follow the **Conventional Commits** standard:

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

| Type | Use When |
|------|----------|
| `feat` | Adding a new feature |
| `fix` | Fixing a bug |
| `docs` | Documentation changes only |
| `style` | Formatting changes (no code logic change) |
| `refactor` | Code restructuring (no feature/bug change) |
| `test` | Adding or fixing tests |
| `chore` | Build process, dependencies, tooling |
| `perf` | Performance improvements |

```bash
# Good commit messages:
git commit -m "feat: add JWT authentication to API endpoints"
git commit -m "fix: resolve NullPointerError in user signup"
git commit -m "docs: update README with installation instructions"
git commit -m "refactor: extract validation logic to utils module"

# Bad commit messages (avoid):
git commit -m "fix"
git commit -m "changes"
git commit -m "asdfgh"
git commit -m "WIP"
```

---

#### `git push`
Uploads your local commits to the remote repository.

```bash
# Push to the 'main' branch on 'origin' (GitHub)
git push origin main

# Push and set upstream tracking (so future pushes are simpler)
git push -u origin main  # Do this once per branch

# After tracking is set, you can just:
git push

# Push all local branches
git push --all origin

# Push tags
git push origin --tags

# Force push (DANGEROUS — only on your own branches, never on shared branches)
git push --force-with-lease origin feature/my-branch
```

---

#### `git pull`
Downloads remote changes and merges them into your current branch.

```bash
# Pull latest changes
git pull

# Pull from a specific remote and branch
git pull origin main

# Pull with rebase instead of merge (cleaner history)
git pull --rebase origin main

# Show what changed before pulling
git fetch
git diff HEAD origin/main
git pull
```

---

#### `git fetch`
Downloads remote changes but does NOT merge them. Safer than `git pull`.

```bash
# Fetch all changes from all remotes
git fetch --all

# Fetch from a specific remote
git fetch origin

# Fetch a specific branch
git fetch origin main

# After fetching, compare:
git log HEAD..origin/main --oneline  # See new commits from remote
git diff HEAD origin/main            # See actual changes
```

---

#### `git branch`
Create, list, rename, and delete branches.

```bash
# List all local branches (* marks current branch)
git branch

# List all branches (local + remote)
git branch -a

# Create a new branch
git branch feature/user-auth

# Create and switch to it in one command
git checkout -b feature/user-auth
# OR modern way (Git 2.23+):
git switch -c feature/user-auth

# Switch to an existing branch
git checkout main
git switch main  # modern way

# Rename current branch
git branch -m new-name

# Delete a branch (after merging)
git branch -d feature/user-auth

# Force delete (not yet merged)
git branch -D feature/user-auth

# Delete remote branch
git push origin --delete feature/user-auth
```

---

#### `git merge`
Combines another branch's history into the current branch.

```bash
# Be on the branch you want to merge INTO
git switch main

# Merge a feature branch
git merge feature/user-auth

# Merge with a commit message (no fast-forward — creates merge commit)
git merge --no-ff feature/user-auth -m "Merge feature/user-auth into main"

# Abort a merge if conflicts are too complex
git merge --abort
```

---

#### `git rebase`
Replays your commits on top of another branch. Keeps history linear and clean.

```bash
# You're on feature/my-feature
# You want to incorporate latest main changes
git switch feature/my-feature
git rebase main

# Interactive rebase — rewrite, squash, or reorder commits (powerful!)
git rebase -i HEAD~3   # Interactively edit last 3 commits

# Abort a rebase
git rebase --abort

# Continue after resolving conflicts
git rebase --continue
```

> **🚫 Warning:** Never rebase commits that have been pushed to a shared branch. Only rebase local unpushed commits.

---

#### `git stash`
Temporarily saves uncommitted changes so you can switch branches.

```bash
# Save uncommitted changes (working directory + staging area)
git stash

# Save with a descriptive message
git stash push -m "WIP: working on user dashboard"

# List all stashes
git stash list
# stash@{0}: WIP: working on user dashboard
# stash@{1}: WIP: bug fix attempt

# Apply the most recent stash (keeps it in stash list)
git stash apply

# Apply and remove from stash list
git stash pop

# Apply a specific stash
git stash apply stash@{1}

# Delete a stash
git stash drop stash@{0}

# Delete all stashes
git stash clear
```

---

#### `git log`
View commit history.

```bash
# Full log
git log

# One line per commit
git log --oneline

# Visual branch graph
git log --oneline --graph --all --decorate

# Last 10 commits
git log -10

# Commits by a specific author
git log --author="Baghel"

# Commits since a date
git log --since="2024-01-01"

# Commits that changed a specific file
git log --follow README.md

# Show changes in each commit
git log -p

# Search commit messages
git log --grep="authentication"
```

---

#### `git diff`
Show differences between versions of files.

```bash
# Difference between working directory and last commit
git diff

# Difference between staging area and last commit
git diff --staged

# Difference between two branches
git diff main feature/user-auth

# Difference in a specific file
git diff README.md

# Difference between two commits
git diff abc123 def456
```

---

#### `git reset`
Undo commits or unstage changes.

```bash
# Unstage a file (undo git add)
git reset README.md

# Undo last commit but keep changes staged
git reset --soft HEAD~1

# Undo last commit, unstage changes, but keep files
git reset --mixed HEAD~1  # This is the default

# Undo last commit AND delete changes (DESTRUCTIVE — cannot recover)
git reset --hard HEAD~1

# Reset to specific commit (DESTRUCTIVE)
git reset --hard abc123

# Safe version: create a new commit that reverses changes
git revert abc123
```

---

#### Real-World Git Workflow

```bash
# Daily professional workflow:

# 1. Start the day — get latest changes
git switch main
git pull

# 2. Create a feature branch
git switch -c feature/add-llm-chatbot

# 3. Work on your feature...
# edit files...

# 4. Check what changed
git status
git diff

# 5. Stage and commit incrementally
git add src/chatbot.py
git commit -m "feat: add basic chatbot skeleton"

# Edit more...
git add src/chatbot.py tests/test_chatbot.py
git commit -m "feat: implement chatbot response logic"

# 6. Before pushing, update from main
git fetch origin
git rebase origin/main  # incorporate any changes from teammates

# 7. Push your feature branch
git push -u origin feature/add-llm-chatbot

# 8. Create a Pull Request on GitHub
# (done in browser)

# 9. After PR is merged, clean up
git switch main
git pull
git branch -d feature/add-llm-chatbot
```

---

## Section 12 — Professional Python Project Structure

### 📁 Complete Repository Layout

```
Python-Programming/
│
├── 📄 README.md                 ← Project overview (shown on GitHub)
├── 📄 Setup.md                  ← This file — environment setup guide
├── 📄 LICENSE                   ← Open source license (MIT, Apache 2.0, etc.)
├── 📄 CONTRIBUTING.md           ← How others can contribute
├── 📄 CODE_OF_CONDUCT.md        ← Community behavior guidelines
├── 📄 CHANGELOG.md              ← History of changes per version
│
├── ⚙️ pyproject.toml             ← Modern Python project config (PEP 518)
├── 📦 requirements.txt          ← Production dependencies
├── 🔧 requirements-dev.txt      ← Development-only dependencies
├── 🔒 requirements-lock.txt     ← Exact pinned versions (reproducible builds)
│
├── 🚫 .gitignore                ← Files Git should ignore
├── 🔐 .env.example              ← Template for environment variables
├── ⚙️ .editorconfig             ← Editor formatting standards
├── 🔍 .pre-commit-config.yaml   ← Pre-commit hooks
│
├── 📁 src/                      ← Source code (src-layout pattern)
│   └── my_package/
│       ├── __init__.py
│       ├── main.py
│       └── utils.py
│
├── 📁 tests/                    ← All test files
│   ├── __init__.py
│   ├── conftest.py              ← Pytest configuration & fixtures
│   ├── test_main.py
│   └── test_utils.py
│
├── 📁 docs/                     ← Documentation
│   ├── index.md
│   ├── installation.md
│   └── api.md
│
├── 📁 notebooks/                ← Jupyter notebooks
│   ├── 01_exploration.ipynb
│   └── 02_experiments.ipynb
│
├── 📁 scripts/                  ← Utility / automation scripts
│   ├── setup.sh
│   └── run_tests.sh
│
├── 📁 data/                     ← Data files (add to .gitignore if large)
│   ├── raw/
│   └── processed/
│
├── 📁 models/                   ← Trained ML models (use Git LFS for large files)
│
├── 📁 exercises/                ← Practice problems with solutions
│   ├── 01_basics/
│   ├── 02_oop/
│   └── 03_algorithms/
│
├── 📁 projects/                 ← Complete mini-projects
│   ├── web_scraper/
│   ├── chat_bot/
│   └── data_dashboard/
│
├── 📁 notes/                    ← Study notes in Markdown
│   ├── python_basics.md
│   ├── oop_notes.md
│   └── ml_concepts.md
│
├── 📁 resources/                ← Reference materials, PDFs, cheatsheets
│
└── 📁 assets/                   ← Images, diagrams for documentation
```

---

### File Explanations

#### `.gitignore`

Tells Git which files NOT to track. Get a starter from `gitignore.io`.

```gitignore
# === Python ===
__pycache__/
*.py[cod]
*$py.class
*.pyo
*.pyd
*.so

# Virtual environments
.venv/
venv/
env/
ENV/

# Distribution / packaging
build/
dist/
*.egg-info/
*.egg

# Testing
.pytest_cache/
.coverage
htmlcov/
.tox/

# Type checkers
.mypy_cache/
.ruff_cache/
.pytype/

# Jupyter
.ipynb_checkpoints/
*.ipynb_checkpoints

# IDEs
.vscode/
.idea/
*.swp
*.swo

# macOS
.DS_Store
.AppleDouble
.LSOverride

# Windows
Thumbs.db
ehthumbs.db
Desktop.ini

# Environment variables — NEVER commit these!
.env
.env.local
.env.*.local

# Data / Models (often too large for Git)
data/raw/
models/
*.h5
*.pkl
*.pt
*.pth

# Logs
logs/
*.log
```

---

#### `.env.example`

Template for environment variables. Commit this file but NOT `.env`.

```env
# Application Settings
APP_NAME=MyPythonApp
APP_ENV=development
DEBUG=True
SECRET_KEY=your-secret-key-here

# Database
DATABASE_URL=postgresql://user:password@localhost:5432/mydb

# API Keys (NEVER put real keys here — this is just a template)
OPENAI_API_KEY=sk-your-openai-key-here
ANTHROPIC_API_KEY=your-anthropic-key-here
HUGGINGFACE_API_KEY=hf-your-key-here

# Redis
REDIS_URL=redis://localhost:6379

# AWS (if using cloud)
AWS_ACCESS_KEY_ID=your-access-key
AWS_SECRET_ACCESS_KEY=your-secret-key
AWS_REGION=us-east-1
```

---

#### `pyproject.toml`

Modern standard for Python project configuration (replaces `setup.py`, `setup.cfg`).

```toml
[build-system]
requires = ["setuptools>=68", "wheel"]
build-backend = "setuptools.backends.legacy:build"

[project]
name = "python-programming"
version = "0.1.0"
description = "Python learning repository"
readme = "README.md"
requires-python = ">=3.10"
license = {text = "MIT"}
authors = [
    {name = "Baghel", email = "baghel@example.com"}
]

dependencies = [
    "numpy>=1.26.0",
    "pandas>=2.0.0",
    "requests>=2.31.0",
]

[project.optional-dependencies]
dev = [
    "pytest>=8.0.0",
    "pytest-cov>=5.0.0",
    "ruff>=0.4.0",
    "mypy>=1.10.0",
]

ml = [
    "torch>=2.3.0",
    "transformers>=4.40.0",
    "scikit-learn>=1.4.0",
]

[tool.ruff]
line-length = 88
target-version = "py312"

[tool.ruff.lint]
select = ["E", "F", "W", "I", "N", "UP"]
ignore = ["E501"]

[tool.pytest.ini_options]
testpaths = ["tests"]
addopts = "-v --tb=short"

[tool.mypy]
python_version = "3.12"
strict = true
```

---

## Section 13 — Jupyter Notebook Setup

### What is Jupyter?

**Jupyter Notebook** (and **JupyterLab**) is an interactive computing environment where you can mix code, output, visualizations, and text in a single document (`.ipynb` file). It's the standard tool for data science, ML research, and teaching Python.

```
Jupyter Notebook = Code + Output + Markdown + Visualizations
```

---

### 📥 Installation

```bash
# Activate your virtual environment first!
source .venv/bin/activate  # macOS/Linux
.venv\Scripts\activate     # Windows

# Install JupyterLab (modern successor to classic Notebook)
pip install jupyterlab

# Install classic Jupyter Notebook (lighter)
pip install notebook

# Install essential data science extensions
pip install jupyterlab-git          # Git integration
pip install jupyterlab-code-formatter  # Auto-format code

# Start JupyterLab
jupyter lab

# Start classic Notebook
jupyter notebook
```

This opens your browser at `http://localhost:8888`

---

### 🧠 Jupyter Kernels

A **kernel** is the computing engine behind a notebook. Each notebook connects to a kernel.

```bash
# List available kernels
jupyter kernelspec list

# Install IPython kernel for your virtual environment
pip install ipykernel
python -m ipykernel install --user --name=my-project --display-name "Python (my-project)"

# Now your .venv will appear as a kernel option in Jupyter

# Remove a kernel
jupyter kernelspec uninstall my-project
```

---

### ⌨️ Essential Jupyter Keyboard Shortcuts

| Mode | Shortcut | Action |
|------|----------|--------|
| **Command** | `Enter` | Enter edit mode |
| **Command** | `Shift+Enter` | Run cell, move to next |
| **Command** | `Ctrl+Enter` | Run cell, stay |
| **Command** | `A` | Insert cell above |
| **Command** | `B` | Insert cell below |
| **Command** | `D D` | Delete cell |
| **Command** | `M` | Convert to Markdown |
| **Command** | `Y` | Convert to Code |
| **Command** | `Z` | Undo last action |
| **Edit** | `Esc` | Enter command mode |
| **Edit** | `Tab` | Code completion |
| **Edit** | `Shift+Tab` | Show docstring |
| **Edit** | `Ctrl+/` | Toggle comment |

---

### 📊 Jupyter Best Practices

```python
# Cell 1: Imports (always at the top)
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

%matplotlib inline  # Show plots inside notebook
%config InlineBackend.figure_format = 'retina'  # High-res plots on Mac

# Cell 2: Configuration
pd.set_option('display.max_columns', 50)
pd.set_option('display.max_rows', 100)
plt.style.use('seaborn-v0_8-darkgrid')

# Cell 3: Load data
df = pd.read_csv('data/dataset.csv')
df.head()
```

---

## Section 14 — Terminal Mastery

### 🖥️ Why Learn the Terminal?

The terminal (command line) is the most powerful tool in a developer's toolkit. Many development tasks are faster, more precise, and only possible via the terminal.

---

### Windows CMD / PowerShell

```powershell
# --- NAVIGATION ---
cd Documents              # Change to Documents folder
cd ..                     # Go up one level
cd \                      # Go to root of drive
dir                       # List files and folders (CMD)
Get-ChildItem             # List files (PowerShell)
ls                        # Also works in PowerShell

# --- FILES & FOLDERS ---
mkdir new-folder          # Create directory
rm file.txt               # Delete file (PowerShell)
del file.txt              # Delete file (CMD)
copy source.txt dest.txt  # Copy file
move source.txt dest/     # Move file
type file.txt             # Print file contents (CMD)
Get-Content file.txt      # Print file contents (PowerShell)

# --- ENVIRONMENT ---
$env:PATH                 # View PATH (PowerShell)
echo %PATH%               # View PATH (CMD)
$env:PYTHON_PATH          # Read environment variable
[Environment]::GetEnvironmentVariable("PATH", "Machine")  # System PATH

# --- PROCESS MANAGEMENT ---
Get-Process               # List running processes
Stop-Process -Name python # Kill a process
python script.py          # Run Python script

# --- NETWORK ---
ipconfig                  # Show IP configuration
ping google.com           # Test network connection
curl https://api.example.com  # HTTP requests (PowerShell 7+)
```

---

### macOS / Linux Bash

```bash
# === NAVIGATION ===
pwd             # Print working directory (where am I?)
ls              # List files
ls -la          # List ALL files with details (including hidden)
cd Documents    # Change directory
cd ..           # Go up one level
cd ~            # Go to home directory
cd -            # Go back to previous directory

# === FILE OPERATIONS ===
touch file.py          # Create empty file
mkdir project          # Create directory
mkdir -p a/b/c         # Create nested directories
cp source.py dest.py   # Copy file
cp -r dir1/ dir2/      # Copy directory recursively
mv old.py new.py       # Rename/move file
rm file.py             # Delete file
rm -rf directory/      # Delete directory (CAREFUL — no recycle bin!)
cat file.py            # Print file contents
less file.py           # View file with scrolling (q to quit)
head -20 file.py       # First 20 lines
tail -20 file.py       # Last 20 lines
tail -f log.txt        # Follow file in real-time (great for logs)
nano file.py           # Edit file in terminal (beginner-friendly)
vim file.py            # Edit with Vim (powerful but steep learning curve)

# === SEARCH & FIND ===
find . -name "*.py"           # Find all Python files
find . -name "*.py" -type f   # Only files (not directories)
grep "def " main.py           # Search inside file
grep -r "import pandas" .     # Search recursively in all files
grep -n "TODO" *.py           # Show line numbers

# === PERMISSIONS ===
ls -la                      # See file permissions
chmod +x script.sh          # Make script executable
chmod 644 file.txt          # Set specific permissions (owner: rw, others: r)
chown user:group file.txt   # Change file owner

# === ENVIRONMENT VARIABLES ===
export MY_VAR="hello"       # Set variable for current session
echo $MY_VAR                # Read variable
env                         # List all environment variables
unset MY_VAR                # Remove variable

# Permanent (add to ~/.bashrc or ~/.zshrc):
echo 'export MY_VAR="hello"' >> ~/.bashrc
source ~/.bashrc             # Reload shell configuration

# === PROCESSES ===
ps aux           # List all running processes
kill PID         # Kill process by ID
kill -9 PID      # Force kill (use as last resort)
htop             # Interactive process viewer (install: sudo apt install htop)
top              # Built-in process viewer
bg               # Send process to background
fg               # Bring background process to foreground
Ctrl+C           # Interrupt/stop current process
Ctrl+Z           # Suspend current process

# === PYTHON SPECIFIC ===
python3 --version
which python3               # Show which Python is being used
python3 -c "print('hello')" # Run Python one-liner
python3 script.py           # Run a script
python3 -m pytest tests/    # Run tests as module
python3 -m pip list         # List installed packages

# === SHELL SHORTCUTS (PRODUCTIVITY) ===
Ctrl+A          # Move cursor to beginning of line
Ctrl+E          # Move cursor to end of line
Ctrl+U          # Delete from cursor to beginning
Ctrl+K          # Delete from cursor to end
Ctrl+W          # Delete previous word
Ctrl+R          # Search command history
Ctrl+L          # Clear screen (same as: clear)
!!              # Repeat last command
!python         # Repeat last command starting with 'python'
history         # Show command history
```

---

### 🌊 Shell Configuration

**Customize your terminal by editing your shell config:**

```bash
# macOS default: ~/.zshrc
# Linux default: ~/.bashrc

nano ~/.zshrc

# Add these useful customizations:

# === ALIASES ===
alias ll='ls -la'
alias py='python3'
alias venv='python3 -m venv .venv && source .venv/bin/activate'
alias activate='source .venv/bin/activate'
alias gs='git status'
alias gl='git log --oneline --graph --all'
alias gc='git commit -m'
alias gp='git push'

# === PATH ===
export PATH="$HOME/.local/bin:$PATH"

# === PYTHON ===
export PYTHONDONTWRITEBYTECODE=1   # Don't create .pyc files
export PYTHONUNBUFFERED=1          # Unbuffered output (important for Docker)

# Reload
source ~/.zshrc
```

---

## Section 15 — Common Errors & Solutions

### 🔴 Python Not Recognized

```
'python' is not recognized as an internal or external command
```

**Cause:** Python is not in PATH.

**Solution:**
```powershell
# Windows: Add Python to PATH manually
# Win+S → "Environment Variables" → System Variables → Path → Edit → New
# Add: C:\Python312 and C:\Python312\Scripts

# Or try:
py --version  # Windows Python Launcher (usually works)
python3 --version  # Some systems use python3

# Reinstall Python with "Add to PATH" checkbox checked
```

---

### 🔴 pip Not Recognized

```
'pip' is not recognized as an internal or external command
```

**Solution:**
```bash
# Use Python module instead
python -m pip install package-name
python3 -m pip install package-name

# Reinstall pip
python -m ensurepip --upgrade

# Update pip
python -m pip install --upgrade pip
```

---

### 🔴 ModuleNotFoundError

```
ModuleNotFoundError: No module named 'numpy'
```

**Cause:** Package not installed, or wrong virtual environment active.

**Solution:**
```bash
# Check which Python is active
which python  # macOS/Linux
where python  # Windows

# Check if you're in the right venv
pip list | grep numpy

# Install the missing package
pip install numpy

# If in a project — install from requirements.txt
pip install -r requirements.txt

# VS Code: Make sure the correct interpreter is selected
# Ctrl+Shift+P → "Python: Select Interpreter" → choose .venv
```

---

### 🔴 Virtual Environment Won't Activate (Windows)

```
.venv\Scripts\activate : File cannot be loaded because running scripts is disabled
```

**Cause:** PowerShell execution policy blocks scripts.

**Solution:**
```powershell
# Fix execution policy
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# Then try again
.venv\Scripts\activate
```

---

### 🔴 Git Not Recognized

```
'git' is not recognized as an internal or external command
```

**Solution:**
```powershell
# Windows — reinstall Git and check "Add to PATH"
winget install Git.Git

# Verify PATH contains Git
$env:PATH -split ';' | Select-String git

# Manual: Add to PATH
# C:\Program Files\Git\cmd
```

---

### 🔴 Git Push Authentication Failure

```
remote: Support for password authentication was removed on August 13, 2021.
fatal: Authentication failed
```

**Cause:** GitHub removed password authentication. You must use SSH or Personal Access Token.

**Solution:**
```bash
# Option 1: Set up SSH (recommended — see Section 10)
# Change remote to SSH
git remote set-url origin git@github.com:username/repository.git

# Option 2: Use Personal Access Token
# GitHub → Settings → Developer Settings → Personal Access Tokens → Generate new token
# Use the token as your password when prompted
```

---

### 🔴 Merge Conflict

```
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
```

**Understanding the conflict markers:**
```python
<<<<<<< HEAD
# Your version of the code
def my_function():
    return "version from your branch"
=======
# Incoming version (from the branch being merged)
def my_function():
    return "version from other branch"
>>>>>>> feature/other-branch
```

**Solution:**
```bash
# Option 1: Use VS Code (recommended for beginners)
# Open VS Code — it shows conflict markers with buttons:
# "Accept Current Change" | "Accept Incoming Change" | "Accept Both Changes"

# Option 2: Manual resolution
# Edit the file, remove the conflict markers, keep the code you want
nano README.md

# After resolving all conflicts:
git add README.md
git commit -m "resolve merge conflict in README.md"

# Option 3: Abort the merge
git merge --abort
```

---

### 🔴 SSH Permission Denied

```
Permission denied (publickey).
fatal: Could not read from remote repository.
```

**Solution:**
```bash
# Check if SSH agent has your key
ssh-add -l

# Add key if missing
ssh-add ~/.ssh/id_ed25519

# Test connection with verbose output
ssh -vT git@github.com

# Check your public key matches what's on GitHub
cat ~/.ssh/id_ed25519.pub
# Paste this on GitHub → Settings → SSH Keys and compare

# Check file permissions
chmod 600 ~/.ssh/id_ed25519
chmod 644 ~/.ssh/id_ed25519.pub
```

---

### 🔴 VS Code "Python Interpreter Not Found"

**Solution:**
```bash
# 1. Make sure virtual environment exists
ls .venv  # Should show bin/, lib/, etc.

# 2. If not, create it
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# 3. In VS Code:
# Ctrl+Shift+P → "Python: Select Interpreter"
# → "Enter interpreter path"
# → ./.venv/bin/python (macOS/Linux) or .\.venv\Scripts\python.exe (Windows)
```

---

### 🔴 `pip install` Fails with SSL Error

```
SSL: CERTIFICATE_VERIFY_FAILED
```

**Solution:**
```bash
# Upgrade pip and certificates
python -m pip install --upgrade pip
pip install --upgrade certifi

# macOS: Run the certificate installer
/Applications/Python\ 3.12/Install\ Certificates.command

# Temporary workaround (not recommended for production)
pip install --trusted-host pypi.org --trusted-host files.pythonhosted.org package-name
```

---

## Section 16 — Security Best Practices

### 🔐 Never Commit Secrets to Git

This is the **#1 security rule** in software development.

```bash
# These should NEVER be in your code or commits:
# - API keys (OpenAI, AWS, Google, etc.)
# - Passwords and database credentials
# - JWT secret keys
# - OAuth tokens
# - SSH private keys
# - Credit card numbers
# - Personal data

# BAD — API key hardcoded in code:
import openai
openai.api_key = "sk-abc123yourrealkeyhere"  # ❌ NEVER DO THIS

# GOOD — Load from environment variable:
import os
from dotenv import load_dotenv

load_dotenv()  # Loads .env file
api_key = os.getenv("OPENAI_API_KEY")  # ✅ Safe

client = openai.OpenAI(api_key=api_key)
```

---

### 📁 .env File Workflow

```bash
# 1. Install python-dotenv
pip install python-dotenv

# 2. Create .env file (NOT in Git)
cat .env
# OPENAI_API_KEY=sk-real-key-here
# DATABASE_URL=postgresql://user:pass@localhost/db

# 3. Create .env.example (IN Git — template without real values)
cat .env.example
# OPENAI_API_KEY=your-key-here
# DATABASE_URL=your-database-url-here

# 4. Add .env to .gitignore (ALWAYS)
echo ".env" >> .gitignore
echo ".env.local" >> .gitignore

# 5. Use in code
from dotenv import load_dotenv
import os

load_dotenv()
key = os.getenv("OPENAI_API_KEY")
```

---

### 🚨 What To Do If You Accidentally Commit a Secret

```bash
# 1. IMMEDIATELY revoke the secret on the service (GitHub token, OpenAI key, etc.)
# This is the most important step — assume it's already compromised

# 2. Remove from Git history (this is complex — won't cover all edge cases)
# Option A: BFG Repo Cleaner (easier)
brew install bfg
bfg --delete-files .env
git reflog expire --expire=now --all && git gc --prune=now --aggressive
git push --force

# Option B: git filter-repo (built-in)
pip install git-filter-repo
git filter-repo --path .env --invert-paths

# 3. Force push (coordinate with your team)
git push --force

# 4. Rotate ALL secrets that were in the commit
# Never assume the old credentials are safe again
```

---

### 🔒 Dependency Security

```bash
# Audit packages for known vulnerabilities
pip install pip-audit
pip-audit

# Or using Safety
pip install safety
safety check

# Keep packages updated (balance security vs stability)
pip list --outdated
pip install --upgrade package-name

# Pin exact versions in production (reproducible, predictable)
pip freeze > requirements-lock.txt

# Use dependabot on GitHub (automated security PRs)
# Add .github/dependabot.yml to your repo
```

---

### 🛡️ GitHub Security Settings

1. **Enable 2FA (Two-Factor Authentication):**
   - GitHub → Settings → Password and authentication → Enable 2FA
   - Use an authenticator app (Google Authenticator, Authy)

2. **Secret Scanning:**
   - GitHub automatically scans public repos for known secret patterns
   - For private repos: Settings → Security → Secret scanning → Enable

3. **Signed Commits (Advanced):**
```bash
# Generate GPG key
gpg --full-generate-key

# Get key ID
gpg --list-secret-keys --keyid-format=long

# Configure Git to sign commits
git config --global user.signingkey YOUR_KEY_ID
git config --global commit.gpgsign true

# Add public GPG key to GitHub
gpg --armor --export YOUR_KEY_ID
# Copy and add to GitHub → Settings → SSH and GPG keys
```

---

## Section 17 — Productivity Tools

### 🛠️ Essential Developer Toolkit

| Tool | Type | Free? | Use Case |
|------|------|-------|----------|
| **VS Code** | Code Editor | ✅ | Primary coding environment |
| **PyCharm** | IDE | Community ✅ | Heavy Python development |
| **GitHub Desktop** | Git GUI | ✅ | Visual Git operations |
| **Docker** | Containerization | ✅ | Reproducible environments |
| **Postman** | API Testing | ✅ | Test REST APIs |
| **DBeaver** | Database GUI | ✅ | Explore SQL databases |
| **Jupyter** | Notebooks | ✅ | Data science, exploration |
| **Notion** | Notes | ✅ | Documentation, notes |
| **Obsidian** | Notes | ✅ | Personal knowledge base |
| **Warp** | Terminal | ✅ | AI-powered terminal |
| **TablePlus** | Database GUI | Limited ✅ | macOS DB browser |
| **Insomnia** | API Testing | ✅ | REST/GraphQL client |
| **Draw.io** | Diagrams | ✅ | Architecture diagrams |

---

### 🐳 Docker — Why Developers Love It

Docker solves the famous "works on my machine" problem by packaging your application with all its dependencies into a container.

```bash
# Install Docker Desktop from https://www.docker.com/products/docker-desktop/

# Verify installation
docker --version
docker compose version

# Run Python in a container (no local Python needed!)
docker run --rm -it python:3.12 python3

# Basic Dockerfile for a Python project
cat Dockerfile
```

```dockerfile
# Dockerfile
FROM python:3.12-slim

WORKDIR /app

# Copy requirements first (caches dependencies layer)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy source code
COPY . .

# Run the application
CMD ["python", "main.py"]
```

```bash
# Build and run your container
docker build -t my-python-app .
docker run my-python-app
```

---

## Section 18 — Developer Best Practices

### 📏 PEP 8 — Python Style Guide

PEP 8 is the official style guide for Python code. Following it makes your code readable and professional.

```python
# ✅ GOOD Python Code

# Imports: one per line, organized (stdlib, third-party, local)
import os
import sys
from pathlib import Path

import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split

from my_package.utils import helper_function

# Constants: ALL_CAPS
MAX_RETRIES = 3
DEFAULT_TIMEOUT = 30

# Functions: snake_case, with docstring
def calculate_average(numbers: list[float]) -> float:
    """Calculate the arithmetic mean of a list of numbers.
    
    Args:
        numbers: A list of numeric values.
        
    Returns:
        The arithmetic mean as a float.
        
    Raises:
        ValueError: If the list is empty.
        
    Example:
        >>> calculate_average([1.0, 2.0, 3.0])
        2.0
    """
    if not numbers:
        raise ValueError("Cannot calculate average of empty list")
    return sum(numbers) / len(numbers)


# Classes: PascalCase
class DataProcessor:
    """Process and transform datasets.
    
    Attributes:
        name: Human-readable name for the processor.
        batch_size: Number of samples to process at once.
    """
    
    def __init__(self, name: str, batch_size: int = 32) -> None:
        self.name = name
        self.batch_size = batch_size
        self._internal_state = {}  # Private: prefix with underscore
    
    def process(self, data: list) -> list:
        """Process a batch of data."""
        return [self._transform(item) for item in data]
    
    def _transform(self, item):
        """Internal transformation logic (private method)."""
        return item
```

---

### 🧪 Testing with pytest

Testing is not optional in professional development.

```bash
# Install pytest
pip install pytest pytest-cov

# Write tests (file name must start with test_)
cat tests/test_calculator.py
```

```python
# tests/test_calculator.py
import pytest
from src.calculator import Calculator


class TestCalculator:
    """Test cases for Calculator class."""
    
    def setup_method(self):
        """Set up fresh calculator before each test."""
        self.calc = Calculator()
    
    def test_add_positive_numbers(self):
        assert self.calc.add(2, 3) == 5
    
    def test_add_negative_numbers(self):
        assert self.calc.add(-1, -1) == -2
    
    def test_divide_by_zero_raises(self):
        with pytest.raises(ZeroDivisionError):
            self.calc.divide(10, 0)
    
    @pytest.mark.parametrize("a,b,expected", [
        (1, 2, 3),
        (0, 0, 0),
        (-1, 1, 0),
        (100, 200, 300),
    ])
    def test_add_multiple_inputs(self, a, b, expected):
        assert self.calc.add(a, b) == expected
```

```bash
# Run all tests
pytest

# Run with verbose output
pytest -v

# Run with coverage report
pytest --cov=src --cov-report=html

# Run only tests matching a pattern
pytest -k "test_add"

# Run a specific file
pytest tests/test_calculator.py
```

---

### 🔄 Pre-commit Hooks

Automatically check code quality before every commit.

```bash
# Install pre-commit
pip install pre-commit

# Create .pre-commit-config.yaml
```

```yaml
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.6.0
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
      - id: check-yaml
      - id: check-added-large-files
      - id: check-merge-conflict
      - id: detect-private-key          # Catches accidentally staged keys!
  
  - repo: https://github.com/astral-sh/ruff-pre-commit
    rev: v0.4.4
    hooks:
      - id: ruff
        args: [--fix]
      - id: ruff-format
  
  - repo: https://github.com/pre-commit/mirrors-mypy
    rev: v1.10.0
    hooks:
      - id: mypy
```

```bash
# Install the hooks
pre-commit install

# Now every git commit will automatically run these checks
git commit -m "my commit"

# Run manually on all files
pre-commit run --all-files
```

---

## Section 19 — Quick Setup Checklist

Use this checklist to verify your environment is fully configured.

### ✅ Foundation

- [ ] Python 3.10+ installed and accessible from terminal
- [ ] `python --version` (or `python3 --version`) returns correct version
- [ ] `pip --version` works and shows correct version
- [ ] pip is up to date: `pip install --upgrade pip`

### ✅ Virtual Environments

- [ ] Can create virtual environment: `python -m venv .venv`
- [ ] Can activate it: `source .venv/bin/activate` (Linux/macOS) or `.venv\Scripts\activate` (Windows)
- [ ] Can install packages into it: `pip install requests`
- [ ] Can deactivate: `deactivate`

### ✅ VS Code

- [ ] VS Code installed and opens with `code .` command
- [ ] Python extension installed
- [ ] Pylance extension installed
- [ ] Ruff extension installed
- [ ] Python interpreter set to `.venv`
- [ ] Format on save works (create a messy file, save it)
- [ ] Integrated terminal opens (`Ctrl+\``)

### ✅ Git

- [ ] `git --version` returns version 2.30+
- [ ] `git config user.name` shows your name
- [ ] `git config user.email` shows your email (matches GitHub)
- [ ] `git config init.defaultBranch` shows `main`

### ✅ GitHub & SSH

- [ ] GitHub account created
- [ ] Profile filled with name, bio, location
- [ ] SSH key generated (`ls ~/.ssh/`)
- [ ] Public key added to GitHub (Settings → SSH Keys)
- [ ] SSH connection verified: `ssh -T git@github.com` → "Hi username!"
- [ ] Can clone a repo via SSH: `git clone git@github.com:...`
- [ ] Can push to a repo

### ✅ First Repository

- [ ] Repository created on GitHub
- [ ] Repository cloned locally
- [ ] `README.md` created and committed
- [ ] Change pushed to GitHub and visible online
- [ ] `.gitignore` added (Python template)
- [ ] Virtual environment NOT in Git (`.venv` in `.gitignore`)

### ✅ Jupyter (Optional but recommended)

- [ ] JupyterLab installed: `pip install jupyterlab`
- [ ] Can start: `jupyter lab`
- [ ] Kernel for your project installed
- [ ] Can run Python cells successfully

### ✅ Security

- [ ] `.env` file exists and is in `.gitignore`
- [ ] `.env.example` exists and is in Git (without real values)
- [ ] GitHub 2FA enabled
- [ ] No real API keys in any committed files

---

## Section 20 — AI/LLM Engineering Roadmap

### 🗺️ Complete Learning Roadmap

```mermaid
flowchart TD
    START([🚀 Start Here]) --> P1

    subgraph FOUNDATION["📘 Foundation (Months 1-3)"]
        P1[Python Basics\nVariables, Loops, Functions]
        P2[Data Structures\nLists, Dicts, Sets, Tuples]
        P3[OOP\nClasses, Inheritance, Polymorphism]
        P4[File I/O & Exceptions]
        P5[Git & GitHub]
        P1 --> P2 --> P3 --> P4 --> P5
    end

    subgraph INTERMEDIATE["⚙️ Intermediate (Months 4-6)"]
        I1[Algorithms & DSA]
        I2[SQL & Databases]
        I3[REST APIs & HTTP]
        I4[Linux & Terminal]
        I5[Testing & pytest]
        I6[Virtual Envs & Packaging]
        P5 --> I1 --> I2 --> I3 --> I4 --> I5 --> I6
    end

    subgraph DATA["📊 Data Science (Months 6-9)"]
        D1[NumPy & Pandas]
        D2[Matplotlib & Seaborn]
        D3[Statistics & Probability]
        D4[Data Cleaning & EDA]
        I6 --> D1 --> D2 --> D3 --> D4
    end

    subgraph ML["🤖 Machine Learning (Months 9-12)"]
        M1[scikit-learn]
        M2[Supervised Learning]
        M3[Unsupervised Learning]
        M4[Model Evaluation & Tuning]
        M5[Feature Engineering]
        D4 --> M1 --> M2 --> M3 --> M4 --> M5
    end

    subgraph DL["🧠 Deep Learning (Months 12-18)"]
        DL1[Neural Networks Basics]
        DL2[PyTorch Fundamentals]
        DL3[CNNs & Computer Vision]
        DL4[RNNs & Sequence Models]
        DL5[Attention Mechanism]
        M5 --> DL1 --> DL2 --> DL3 --> DL4 --> DL5
    end

    subgraph NLP["💬 NLP & Transformers (Months 18-24)"]
        N1[NLP Fundamentals]
        N2[Tokenization & Embeddings]
        N3[Transformer Architecture]
        N4[BERT & GPT Variants]
        N5[Hugging Face Ecosystem]
        DL5 --> N1 --> N2 --> N3 --> N4 --> N5
    end

    subgraph LLM["🔮 LLM Engineering (Months 24-36)"]
        L1[OpenAI API & Prompting]
        L2[LangChain & LlamaIndex]
        L3[RAG Systems]
        L4[Vector Databases]
        L5[Fine-tuning LLMs]
        L6[AI Agents & Tool Use]
        L7[LLMOps & Deployment]
        N5 --> L1 --> L2 --> L3 --> L4 --> L5 --> L6 --> L7
    end

    subgraph ADVANCED["⚡ Advanced (Months 36-60)"]
        A1[MLOps & CI/CD for AI]
        A2[Distributed Training]
        A3[CUDA & GPU Programming]
        A4[AI Research & Papers]
        A5[Quantum Computing Basics]
        A6[Quantum ML & Qiskit]
        L7 --> A1 --> A2 --> A3 --> A4 --> A5 --> A6
    end

    A6 --> END([🏆 AI Research Engineer])

    style START fill:#4CAF50,color:#fff
    style END fill:#9C27B0,color:#fff
    style FOUNDATION fill:#E3F2FD
    style LLM fill:#FFF3E0
    style ADVANCED fill:#F3E5F5
```

---

### 📚 Learning Timeline

| Phase | Duration | Focus | Key Libraries |
|-------|----------|-------|---------------|
| **Foundation** | 0–3 months | Python, Git, OOP | standard library |
| **Intermediate** | 3–6 months | DSA, SQL, APIs, Linux | FastAPI, SQLAlchemy |
| **Data Science** | 6–9 months | Data analysis | NumPy, Pandas, Matplotlib |
| **Machine Learning** | 9–12 months | Classical ML | scikit-learn, XGBoost |
| **Deep Learning** | 12–18 months | Neural networks | PyTorch, Lightning |
| **NLP/Transformers** | 18–24 months | Language models | Transformers, spaCy |
| **LLM Engineering** | 24–36 months | LLMs, RAG, Agents | LangChain, OpenAI |
| **Advanced AI** | 36–60 months | Research & production | CUDA, Triton, Qiskit |

---

### 🏆 Milestone Projects

| Level | Project | Skills Demonstrated |
|-------|---------|---------------------|
| Beginner | Calculator CLI | Python basics, OOP |
| Beginner | To-Do App | File I/O, JSON |
| Intermediate | Web Scraper | requests, BeautifulSoup |
| Intermediate | REST API | FastAPI, SQLite |
| Data Science | EDA Dashboard | Pandas, Plotly, Streamlit |
| ML | Price Predictor | scikit-learn, model deployment |
| Deep Learning | Image Classifier | PyTorch, CNN |
| NLP | Sentiment Analyzer | Transformers, BERT |
| LLM | RAG Chatbot | LangChain, vector DB, OpenAI |
| Advanced | AI Agent | LangGraph, tools, memory |

---

## Section 21 — FAQ

**Q1: Should I learn Python 2 or Python 3?**
> Always Python 3. Python 2 was officially retired on January 1, 2020. Any book, course, or resource still teaching Python 2 is outdated.

**Q2: How long does it take to learn Python?**
> Basic syntax: 2–4 weeks. Comfortable with OOP and standard library: 3–6 months. Professional-level: 1–2 years. But you can build real projects after just 1–2 months.

**Q3: Do I need to know math for Python?**
> For basic Python, automation, and web development — no. For data science and machine learning — basic statistics and linear algebra help. For deep learning research — calculus and probability are important.

**Q4: What's the difference between a library, package, framework, and module?**
> - **Module**: A single `.py` file (`math.py`)
> - **Package**: A folder of modules with an `__init__.py`
> - **Library**: A collection of related packages (`NumPy`)
> - **Framework**: An opinionated structure where you fill in the blanks (`Django`)

**Q5: Should I use Python 3.10, 3.11, or 3.12?**
> Use the latest stable release (3.12 as of 2025). Each version brings performance improvements. 3.11 was 25% faster than 3.10. 3.12 improved further. Check library compatibility if using niche packages.

**Q6: What is pip?**
> `pip` stands for "Pip Installs Packages." It's Python's package installer that downloads packages from PyPI (Python Package Index — `pypi.org`). Think of it like an app store for Python libraries.

**Q7: What's the difference between `pip install` and `conda install`?**
> `pip` installs Python packages from PyPI. `conda` (from Anaconda/Miniconda) installs packages from conda channels and can also manage non-Python dependencies like CUDA libraries. For AI/ML work, both are commonly used.

**Q8: Do I need to learn the terminal?**
> Yes. The terminal is essential for Python development, Git, server management, and virtually all professional development workflows. Start with basic commands from Section 14.

**Q9: What is `__init__.py`?**
> It's a special file that tells Python "this folder is a package." It can be empty. When you do `from mypackage import something`, Python looks for `__init__.py` in `mypackage/`.

**Q10: What is `if __name__ == "__main__"`?**
> It checks if the script is being run directly (not imported). Code inside this block only runs when you do `python script.py`, not when another file imports it.
```python
def main():
    print("Running directly")

if __name__ == "__main__":
    main()
```

**Q11: What's the difference between `==` and `is` in Python?**
> `==` checks **value equality** (are they the same value?). `is` checks **identity** (are they the same object in memory?). Use `==` for value comparisons. Use `is` only for `None` checks: `if x is None`.

**Q12: What is a virtual environment and why do I need one?**
> It's an isolated Python environment with its own packages. You need one because different projects need different package versions. Without it, packages from Project A would conflict with Project B.

**Q13: What's the difference between `requirements.txt` and `pyproject.toml`?**
> `requirements.txt` is the old-school way to list dependencies. `pyproject.toml` is the modern standard (PEP 518/621) that combines project metadata, dependencies, and tool configuration. New projects should use `pyproject.toml`.

**Q14: How do I update all my packages?**
> ```bash
> pip install --upgrade pip
> pip list --outdated  # See what's outdated
> pip install --upgrade package-name  # Update specific package
> # Warning: Mass upgrading can break things. Test carefully.
> ```

**Q15: What is `*args` and `**kwargs`?**
> They allow functions to accept any number of arguments.
> ```python
> def my_func(*args, **kwargs):
>     print(args)    # Tuple of positional args: (1, 2, 3)
>     print(kwargs)  # Dict of keyword args: {'a': 1, 'b': 2}
> 
> my_func(1, 2, 3, a=1, b=2)
> ```

**Q16: What is a decorator in Python?**
> A function that wraps another function to add behavior without modifying its code.
> ```python
> def timer(func):
>     import time
>     def wrapper(*args, **kwargs):
>         start = time.time()
>         result = func(*args, **kwargs)
>         print(f"Took {time.time()-start:.2f}s")
>         return result
>     return wrapper
> 
> @timer
> def slow_function():
>     time.sleep(1)
> ```

**Q17: What is a list comprehension?**
> A concise way to create lists:
> ```python
> # Traditional
> squares = []
> for x in range(10):
>     squares.append(x ** 2)
> 
> # List comprehension
> squares = [x ** 2 for x in range(10)]
> 
> # With filter
> even_squares = [x ** 2 for x in range(10) if x % 2 == 0]
> ```

**Q18: What is the GIL in Python?**
> The **Global Interpreter Lock** is a mutex in CPython (the standard Python) that allows only one thread to execute Python code at a time. This limits CPU parallelism in multi-threaded programs. Workarounds: use `multiprocessing` module, async programming, or switch to a GIL-free implementation (Python 3.13+ has a free-threaded mode).

**Q19: What is a generator in Python?**
> A function that yields values one at a time instead of returning all at once. Memory-efficient for large data:
> ```python
> def count_up(n):
>     for i in range(n):
>         yield i  # Pauses here, resumes next call
> 
> gen = count_up(1000000)  # No memory allocated yet
> print(next(gen))  # Get values one at a time
> ```

**Q20: What's the difference between `append()` and `extend()` for lists?**
> `append()` adds a single item. `extend()` adds all items from an iterable:
> ```python
> lst = [1, 2, 3]
> lst.append([4, 5])   # [1, 2, 3, [4, 5]]  ← nested list
> lst.extend([4, 5])   # [1, 2, 3, 4, 5]    ← merged
> ```

**Q21: What is duck typing?**
> Python doesn't require explicit type declarations. If an object has the methods/attributes needed, it works — like a duck test ("if it walks like a duck and quacks like a duck, it's a duck"). This enables flexible, reusable code.

**Q22: What is the difference between shallow copy and deep copy?**
> ```python
> import copy
> original = [[1, 2], [3, 4]]
> 
> shallow = original.copy()       # New list, but inner lists are shared
> deep = copy.deepcopy(original)  # Completely independent copy
> 
> original[0].append(99)
> print(shallow)  # [[1, 2, 99], [3, 4]] — affected!
> print(deep)     # [[1, 2], [3, 4]]     — not affected
> ```

**Q23: What is `self` in Python classes?**
> `self` refers to the current instance of the class. It's passed automatically to all instance methods and lets you access the object's attributes and other methods. The name `self` is a convention, not a keyword.

**Q24: What is `__str__` vs `__repr__`?**
> `__str__` is for human-readable output (used by `print()`). `__repr__` is for developer-readable output showing how to recreate the object (used in REPL):
> ```python
> class Point:
>     def __str__(self): return f"({self.x}, {self.y})"
>     def __repr__(self): return f"Point(x={self.x}, y={self.y})"
> ```

**Q25: What is an f-string?**
> F-strings (formatted string literals, Python 3.6+) are the modern way to embed variables in strings:
> ```python
> name = "Baghel"
> age = 20
> print(f"Hello, {name}! You are {age} years old.")
> print(f"3 + 4 = {3 + 4}")       # Expressions allowed
> print(f"Pi = {3.14159:.2f}")     # Formatting
> ```

**Q26: How do I read a file in Python?**
> ```python
> # Modern way — context manager handles closing automatically
> with open("file.txt", "r", encoding="utf-8") as f:
>     content = f.read()       # Entire file as string
>     lines = f.readlines()    # List of lines
>     
> # Write to a file
> with open("output.txt", "w", encoding="utf-8") as f:
>     f.write("Hello, file!\n")
> ```

**Q27: What is `pathlib` and why use it over `os.path`?**
> `pathlib` is the modern way to work with file paths (Python 3.4+). It's object-oriented and more readable:
> ```python
> from pathlib import Path
> 
> p = Path("my_folder") / "subfolder" / "file.txt"  # OS-agnostic path joining
> p.exists()
> p.mkdir(parents=True, exist_ok=True)
> p.write_text("content")
> text = p.read_text()
> ```

**Q28: What is `asyncio` in Python?**
> `asyncio` enables asynchronous programming — running concurrent operations without threads. Critical for I/O-bound tasks like web requests, databases:
> ```python
> import asyncio
> import aiohttp
> 
> async def fetch(url):
>     async with aiohttp.ClientSession() as session:
>         async with session.get(url) as response:
>             return await response.text()
> 
> asyncio.run(fetch("https://api.example.com"))
> ```

**Q29: What is type hinting?**
> Optional annotations that document expected types. Don't affect runtime but help IDEs and static checkers:
> ```python
> def greet(name: str, age: int) -> str:
>     return f"Hello {name}, age {age}"
> 
> def process(items: list[int]) -> dict[str, int]:
>     return {"sum": sum(items), "count": len(items)}
> ```

**Q30: What's the difference between `sort()` and `sorted()`?**
> `list.sort()` sorts in-place (modifies original). `sorted()` returns a new sorted list:
> ```python
> nums = [3, 1, 4, 1, 5]
> nums.sort()         # Modifies nums: [1, 1, 3, 4, 5]
> 
> nums = [3, 1, 4, 1, 5]
> new = sorted(nums)  # nums unchanged, new = [1, 1, 3, 4, 5]
> ```

**Q31: How does Python manage memory?**
> Python uses automatic memory management with **reference counting** and a cyclic **garbage collector**. When an object's reference count drops to 0, it's immediately freed. Circular references are handled by the garbage collector periodically.

**Q32: What is `None` in Python?**
> `None` is Python's null value — it represents the absence of a value. It's not the same as 0, False, or an empty string. Functions return `None` by default if they don't have an explicit `return` statement.

**Q33: What is the difference between `is` and `==` for None checks?**
> Always use `is` for None: `if value is None:`. Using `==` technically works but is considered bad practice because custom objects could override `__eq__` in unexpected ways.

**Q34: What are Python's built-in data types?**
> Numeric: `int`, `float`, `complex`. Sequence: `str`, `list`, `tuple`, `range`. Mapping: `dict`. Set: `set`, `frozenset`. Boolean: `bool`. Binary: `bytes`, `bytearray`. None: `NoneType`.

**Q35: What is a dictionary comprehension?**
> ```python
> # Create dict from two lists
> keys = ['a', 'b', 'c']
> vals = [1, 2, 3]
> d = {k: v for k, v in zip(keys, vals)}  # {'a': 1, 'b': 2, 'c': 3}
> 
> # Transform existing dict
> prices = {'apple': 1.0, 'banana': 0.5}
> discounted = {k: v * 0.9 for k, v in prices.items()}
> ```

**Q36: What is exception handling?**
> ```python
> try:
>     result = int(input("Enter a number: "))
> except ValueError as e:
>     print(f"Invalid input: {e}")
> except ZeroDivisionError:
>     print("Cannot divide by zero")
> else:
>     print(f"Success: {result}")  # Runs if no exception
> finally:
>     print("This always runs")    # Cleanup code
> ```

**Q37: What is `__init__` in a class?**
> The constructor method — called automatically when you create an instance with `MyClass()`. Use it to initialize attributes:
> ```python
> class Car:
>     def __init__(self, brand: str, year: int):
>         self.brand = brand
>         self.year = year
> 
> my_car = Car("Toyota", 2023)  # __init__ called here
> ```

**Q38: What is inheritance?**
> A class can inherit attributes and methods from a parent class:
> ```python
> class Animal:
>     def speak(self): return "..."
> 
> class Dog(Animal):          # Dog inherits from Animal
>     def speak(self): return "Woof!"  # Override parent method
> 
> class Cat(Animal):
>     def speak(self): return "Meow!"
> 
> dog = Dog()
> print(dog.speak())  # "Woof!"
> print(isinstance(dog, Animal))  # True
> ```

**Q39: What is `super()`?**
> Calls the parent class's methods:
> ```python
> class Animal:
>     def __init__(self, name):
>         self.name = name
> 
> class Dog(Animal):
>     def __init__(self, name, breed):
>         super().__init__(name)  # Call Animal.__init__
>         self.breed = breed
> ```

**Q40: What is a lambda function?**
> An anonymous one-line function:
> ```python
> # Regular function
> def square(x): return x ** 2
> 
> # Lambda equivalent
> square = lambda x: x ** 2
> 
> # Common use with sorted/map/filter
> data = [('Alice', 30), ('Bob', 25), ('Charlie', 35)]
> sorted_data = sorted(data, key=lambda x: x[1])  # Sort by age
> ```

**Q41: What is `map()` and `filter()`?**
> ```python
> nums = [1, 2, 3, 4, 5]
> 
> # map: apply function to each element
> squares = list(map(lambda x: x**2, nums))  # [1, 4, 9, 16, 25]
> 
> # filter: keep elements where function returns True
> evens = list(filter(lambda x: x % 2 == 0, nums))  # [2, 4]
> 
> # Modern Pythonic alternative — list comprehensions
> squares = [x**2 for x in nums]
> evens = [x for x in nums if x % 2 == 0]
> ```

**Q42: What is `zip()`?**
> Combines multiple iterables element by element:
> ```python
> names = ["Alice", "Bob", "Charlie"]
> scores = [95, 87, 92]
> 
> for name, score in zip(names, scores):
>     print(f"{name}: {score}")
> 
> # Create dict
> result = dict(zip(names, scores))  # {'Alice': 95, 'Bob': 87, 'Charlie': 92}
> ```

**Q43: What is a context manager (`with` statement)?**
> Ensures resources (files, DB connections) are properly opened and closed even if an error occurs:
> ```python
> # File automatically closes after the with block
> with open("file.txt") as f:
>     data = f.read()
> 
> # Create your own with @contextmanager
> from contextlib import contextmanager
> 
> @contextmanager
> def timer():
>     import time
>     start = time.time()
>     yield
>     print(f"Elapsed: {time.time() - start:.2f}s")
> 
> with timer():
>     do_something()
> ```

**Q44: What is the difference between `break`, `continue`, and `pass`?**
> ```python
> for i in range(10):
>     if i == 3: break     # Exit loop entirely
>     if i == 5: continue  # Skip to next iteration
>     if i == 7: pass      # Do nothing (placeholder)
>     print(i)
> ```

**Q45: What is unpacking in Python?**
> ```python
> # Tuple unpacking
> x, y, z = (1, 2, 3)
> 
> # Extended unpacking
> first, *rest = [1, 2, 3, 4, 5]
> # first = 1, rest = [2, 3, 4, 5]
> 
> # Swap variables (Python magic!)
> a, b = 10, 20
> a, b = b, a  # No temp variable needed
> 
> # Dict unpacking into function
> def func(x, y, z): ...
> params = {'x': 1, 'y': 2, 'z': 3}
> func(**params)
> ```

**Q46: How do I run a Python script as a module vs. as a script?**
> ```bash
> python script.py          # Run as script
> python -m script          # Run as module (uses sys.path, enables relative imports)
> python -m pytest tests/   # Run pytest as module
> python -m venv .venv      # Run venv module
> ```

**Q47: What is `__all__` in a module?**
> Controls what's exported when someone does `from module import *`:
> ```python
> # utils.py
> __all__ = ["public_func", "PublicClass"]  # Only these are exported
> 
> def public_func(): ...
> def _private_func(): ...   # Won't be exported
> class PublicClass: ...
> ```

**Q48: What is `dataclass`?**
> A decorator that auto-generates `__init__`, `__repr__`, `__eq__` for classes:
> ```python
> from dataclasses import dataclass, field
> 
> @dataclass
> class Point:
>     x: float
>     y: float
>     label: str = "point"  # Default value
>     tags: list = field(default_factory=list)
> 
> p = Point(1.0, 2.0)
> print(p)  # Point(x=1.0, y=2.0, label='point', tags=[])
> ```

**Q49: What is the `walrus operator` (`:=`)?**
> Assigns a value AND evaluates it in the same expression (Python 3.8+):
> ```python
> # Without walrus
> line = file.readline()
> while line:
>     process(line)
>     line = file.readline()
> 
> # With walrus
> while line := file.readline():
>     process(line)
> ```

**Q50: How do I make my Python code faster?**
> 1. Profile first: `python -m cProfile script.py` — find the bottleneck
> 2. Use built-in functions (they're in C): `sum()`, `max()`, `sorted()`
> 3. Use `numpy` for numerical operations (vectorized, C-speed)
> 4. Use `multiprocessing` for CPU-bound parallel work
> 5. Use `asyncio` for I/O-bound concurrent work
> 6. Consider `numba` for JIT-compiled numerics
> 7. For very performance-critical code, write C extensions or use Cython

---

## Section 22 — Resources

### 📚 Official Documentation

| Resource | URL | Description |
|----------|-----|-------------|
| **Python Docs** | docs.python.org | Official Python documentation |
| **PyPI** | pypi.org | Find and install Python packages |
| **PEP Index** | peps.python.org | Python Enhancement Proposals |
| **Python Tutorial** | docs.python.org/3/tutorial | Official beginner tutorial |
| **Real Python** | realpython.com | In-depth Python tutorials |
| **Python Cookbook** | github.com/dabeaz/python-cookbook | Advanced Python recipes |

---

### 📖 Recommended Books

| Level | Book | Author |
|-------|------|--------|
| Beginner | *Python Crash Course* | Eric Matthes |
| Beginner | *Automate the Boring Stuff with Python* | Al Sweigart (free online!) |
| Intermediate | *Fluent Python* | Luciano Ramalho |
| Intermediate | *Python Cookbook* | David Beazley |
| Advanced | *High Performance Python* | Micha Gorelick |
| Data Science | *Python for Data Analysis* | Wes McKinney |
| ML/DL | *Hands-On Machine Learning* | Aurélien Géron |
| LLM Eng | *Building LLMs for Production* | Towards AI team |
| Clean Code | *Clean Code in Python* | Mariano Anaya |

---

### 🎓 Online Courses

| Platform | Course | Level | Free? |
|----------|--------|-------|-------|
| **freeCodeCamp** | Scientific Computing with Python | Beginner | ✅ Free |
| **CS50P** (Harvard) | Introduction to Programming with Python | Beginner | ✅ Free |
| **Kaggle** | Python Course | Beginner | ✅ Free |
| **fast.ai** | Practical Deep Learning | Advanced | ✅ Free |
| **Hugging Face** | NLP Course | Intermediate | ✅ Free |
| **DeepLearning.AI** | Machine Learning Specialization | Intermediate | Audit free |
| **Coursera** | Python for Everybody | Beginner | Audit free |
| **Udemy** | Complete Python Bootcamp | Beginner–Intermediate | Paid |
| **DataCamp** | Python tracks | All levels | Limited free |

---

### 📺 YouTube Channels

| Channel | Focus | Recommended For |
|---------|-------|----------------|
| **Corey Schafer** | Python fundamentals to advanced | Best overall Python |
| **Tech With Tim** | Python projects, ML | Project-based learning |
| **Sentdex** | Python, ML, finance | Applied Python |
| **Patrick Loeber** | ML/DL/AI with Python | Machine learning |
| **Andrej Karpathy** | Deep learning, LLMs | Neural networks, GPT |
| **3Blue1Brown** | Math/ML visuals | Understanding concepts |
| **Yannic Kilcher** | ML papers explained | Research papers |
| **freeCodeCamp** | Full Python courses | Comprehensive courses |
| **Programming with Mosh** | Python fundamentals | Clean beginner content |
| **Tech With Tim** | Python, Game Dev | Fun projects |

---

### 🏋️ Practice Platforms

| Platform | Focus | Level |
|----------|-------|-------|
| **LeetCode** | Algorithms & DSA | All levels |
| **HackerRank** | Python challenges | Beginner–Advanced |
| **Codewars** | Kata challenges | All levels |
| **Project Euler** | Math + Python | Intermediate+ |
| **Advent of Code** | Annual puzzle challenges | Intermediate |
| **Kaggle Competitions** | Real ML datasets | Data Science |
| **HuggingFace Spaces** | Deploy ML apps | ML/DL |
| **exercism.io** | Python exercises + mentoring | Beginner–Intermediate |

---

### 🌐 GitHub Repositories to Follow & Star

```bash
# Python fundamentals
github.com/TheAlgorithms/Python          # All algorithms in Python
github.com/vinta/awesome-python          # Curated Python resources
github.com/satwikkansal/wtfpython        # Surprising Python behavior

# Data Science
github.com/donnemartin/data-science-ipython-notebooks

# Machine Learning
github.com/ageron/handson-ml3            # Hands-On ML book notebooks
github.com/rasbt/LLMs-from-scratch       # Build LLMs from scratch!

# LLM Engineering
github.com/langchain-ai/langchain
github.com/run-llama/llama_index
github.com/openai/openai-python

# Learning Resources
github.com/30-seconds/30-seconds-of-python  # Useful Python snippets
```

---

### 🤝 Communities

| Community | Platform | Description |
|-----------|----------|-------------|
| **r/learnpython** | Reddit | Beginner-friendly Q&A |
| **r/Python** | Reddit | General Python discussion |
| **Python Discord** | Discord | Active real-time help |
| **Hugging Face Discord** | Discord | AI/ML community |
| **PyData** | Slack | Data science community |
| **Stack Overflow** | Web | Technical Q&A |
| **Dev.to** | Web | Articles and tutorials |
| **Hashnode** | Web | Developer blogging |

---

> ### 🎯 Final Message
>
> You now have everything you need to build a world-class Python development environment. The most important step is simply to **start** — open your terminal, create a virtual environment, and write your first line of code today.
>
> **Remember:** Every expert was once a beginner. The only difference is they kept going.
>
> ```python
> # Your first Python program
> print("Hello, World! My Python journey starts now. 🚀")
> ```
>
> **— Good luck, Baghel. Build something amazing. 🐍**

---

<div align="center">

**⭐ If this guide helped you, star the repository and share it with others!**

Made with ❤️ for the Python community

</div>
