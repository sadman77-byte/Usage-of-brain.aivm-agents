# AIVM Brain Integration & Multi-Agent MCP Setup

This repository provides a comprehensive guide on integrating **AIVM Brain** (via [brain.aivm.io](https://brain.aivm.io)) with local developer IDEs and terminal agents (such as Cursor, Codex, and Claude Code) using the **Model Context Protocol (MCP)**. It also covers the Node.js environment requirements and the cybersecurity domain under which this architecture operates.

---

## 📌 Workflow Overview

AIVM Brain acts as a governed AI context and knowledge management layer. It allows AI agents running in your local editor or terminal to securely query workspace memories and share session states.

```
+------------------------+      Secure Session Key / MCP Bridge      +---------------------------+
|    AIVM Brain Cloud    | <=======================================> |  Local Machine (macOS)    |
| (https://brain.aivm.io)|                                           |  - Cursor / Codex / IDE   |
+------------------------+                                           |  - Local dir: ~/_brain    |
                                                                     +---------------------------+
```

---

## 🚀 Step-by-Step Setup Process

### Step 1: Prerequisites & Node.js Installation
The connection bridge requires Node.js to execute the runner script via terminal (`bash`/`zsh`).
1. Download the macOS installer (`.pkg` file) directly from official Node.js website: [https://nodejs.org/](https://nodejs.org/).
2. Run the `.pkg` file and follow the standard installation steps to set up `node` and `npm`/`npx`.
3. Verify installation in your terminal:
   ```bash
   node -v
   npm -v
   ```

### Step 2: Tool & Platform Selection (AIVM Dashboard)
1. Go to [https://brain.aivm.io](https://brain.aivm.io).
2. Under **Choose your tool**, select your target agent or IDE (e.g., `Claude Code`, `Claude Desktop`, `Cursor`, or `Codex`).
3. Under **Confirm your platform**, select your operating system (e.g., `macOS`).

### Step 3: Session Key Generation & Terminal Bridge
1. Enter a name for your connection (e.g., `Codex · macOS` or `Cursor · macOS`).
2. Click **Generate key**.
3. Copy and run the provided command in your local terminal:
   ```bash
   curl -fsSL https://app.brain.aivm.io/agent-keys/connect.cjs | node - --key <YOUR_SESSION_KEY>
   ```
   *(Note: A compatibility bridge option is also available if the default command fails).*

### Step 4: Workspace Registration & Model Configuration
1. The terminal command automatically creates a local workspace folder at `~/_brain` and registers auto-read `AGENTS.md` rules.
2. Open **Cursor IDE** or your preferred tool.
3. In Cursor Settings (`Settings -> Models`), enable and select your desired subagent models (e.g., `Claude Opus 5`, `GPT-5.6 Sol`, `Gemini 3.8 Flash`, `GLM 5.2`).
4. Interact with the chat interface to verify that session context is loaded directly from your brain.

---

## 🛡️ Cybersecurity Domain & Analysis

This entire process falls under the **Identity and Access Management (IAM)** and **AI Security Governance** branches of Cybersecurity.

### Key Security Principles Involved:
1. **Scoped API Key & Token Management (IAM):**
   - Access is restricted using scoped session tokens that act strictly on behalf of the authenticated user within a specific workspace.
2. **Principle of Least Privilege (PoLP):**
   - Connected tools only access what is explicitly authorized in the workspace. Revoking a key instantly terminates access.
3. **Audit Logging & Governance (GRC - Governance, Risk, and Compliance):**
   - Every agent request and execution is checked against user permissions and logged to a tamper-evident ledger for full traceability.

---

## 📝 Summary of Resources Used

* **AIVM Brain Dashboard:** [https://brain.aivm.io](https://brain.aivm.io)
* **Node.js Package (.pkg Download):** [https://nodejs.org/](https://nodejs.org/)
* **Protocol:** Model Context Protocol (MCP)

---

## 📄 License
This project is for educational and technical documentation purposes.