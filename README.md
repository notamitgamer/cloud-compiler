# Cloud Code Compiler ☁️

> **A real-time, low-latency code execution platform.** > Built with raw WebSockets, Python `aiohttp`, and a custom C/C++ runner.

## 🚀 Live Demo

[**Try the Compiler**](https://compiler.amit.is-a.dev/)

## ⚡ Key Features

* **Real-time I/O**: Uses WebSockets to stream output character-by-character, allowing for interactive programs (e.g., `input()` in Python or `std::cin` in C++).

* **Multi-Language Support**:

  * 🐍 **Python 3**: With **Auto-Pip** technology (detects imports and installs packages on the fly).

  * ⚙️ **C / C++**: Full GCC/G++ compilation with standard stream handling.

* **Cyberpunk UI**: A retro-futuristic, responsive interface built with Tailwind CSS and Xterm.js.

* **Low Latency**: Persistent connections avoid the overhead of repeated HTTP requests.

## 🛠 Tech Stack

| Component | Technology | 
 | ----- | ----- | 
| **Frontend** | HTML5, Tailwind CSS, Xterm.js (WebSockets) | 
| **Backend** | Python 3.10, `aiohttp`, `asyncio` | 
| **Compilers** | GCC 11, G++, CPython | 
| **Deployment** | Docker (Planned), Linux Host | 

## 🏗 Architecture

### **The Backend (`backend.py`)**

The core is an asynchronous Python server using `aiohttp`. It upgrades HTTP requests to WebSocket connections.

* **Session Handling**: Each tab gets a unique session.

* **Execution**: Spawns `subprocess` threads to run user code safely on the host.

* **Stream Redirection**: Captures `stdout` and `stderr` pipes and pushes them to the frontend in real-time.

### **The Frontend**

* **Editor**: A custom `textarea` overlay for code input.

* **Terminal**: `xterm.js` renders ANSI escape codes (colors) and handles user input during execution.

## 📦 Installation & Setup

### Prerequisites

* Python 3.10+

* GCC / G++ Compiler

* Linux/MacOS (Recommended) or Windows (WSL)

### 1. Clone the Repository

```bash
git clone [https://github.com/notamitgamer/cloud-compiler.git](https://github.com/notamitgamer/cloud-compiler.git)
cd cloud-compiler
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the Backend Server

```bash
python backend.py
```

*The server will start on port 8080 (or the port defined in `backend.py`).*

## 🛡 Disclaimer & Liability

This compiler is a **demonstration project** created by a Computer Science undergraduate.

* **Security**: Code is currently executed on the host machine without sandboxing. Do not run malicious code.

* **Liability**: **Amit Dutta** assumes no responsibility for any data loss, security breaches, or damages resulting from the use of this code. Use at your own risk.

* **Rights**: The author reserves the right to modify or take down the service at any time.

## 👨‍💻 Author

**Amit Dutta**

* 🎓 CS Undergraduate (19 y/o)

* 🌐 [amit.is-a.dev](https://amit.is-a.dev)

* 🐙 [GitHub](https://github.com/notamitgamer)

* 📧 [amitdutta4255@gmail.com](mailto:amitdutta4255@gmail.com)

*Built with ❤️ and ☕ in Kolkata, India.*
