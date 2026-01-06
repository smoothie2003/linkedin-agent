# LinkedIn Agent (CrewAI)

An agentic workflow for generating LinkedIn posts using multiple AI agents and a human-in-the-loop approval cycle.

Built with:
- Python
- CrewAI
- OpenAI API
- Jupyter Notebooks
- GitHub Codespaces

---


## Requirements

Python 3.9+ is recommended.

Dependencies are defined in `requirements.txt`:

- crewai
- openai
- python-dotenv

Install dependencies with:

```bash
pip install -r requirements.txt
```
## 🔐 OpenAI API Key Setup (Required)

This project uses the OpenAI API since thats the model the agents are using You can switch up your own model and supply your own keys.

**You must provide your own API key** — it is **not included** in this repository.

### ✅ Recommended: GitHub Codespaces (Secure)

If you are using **GitHub Codespaces**, add your API key as a Codespaces secret:

1. Go to your repository on GitHub
2. Navigate to:
   **Settings → Secrets and variables → Codespaces**
3. Click **New repository secret**
4. Add:
   - **Name:** `OPENAI_API_KEY`
   - **Value:** your OpenAI API key
5. Save and **restart or rebuild** your Codespace

Secrets are injected as environment variables and are:
- ❌ Not stored in the repo
- ❌ Not shared with forks or clones
- ❌ Not visible in code or commits

---

### 🧪 Verify the key is loaded (Terminal)

Inside your Codespace terminal, run:

```bash
printenv OPENAI_API_KEY
```
# Agent Workflow Design

```
┌──────────────────────────┐
│        Human (You)       │
│  • Topic                 │
│  • Max lines             │
│  • Emojis (yes / no)     │
└─────────────┬────────────┘
              │
              ▼
┌──────────────────────────┐
│  Agent 1: Content Writer │◀──────────────┐
│  • Generates full draft  │               │
│  • Focus on ideas & flow │               │
│  • Incorporates feedback │               │
└─────────────┬────────────┘               │
              │                            │
              ▼                            │
┌──────────────────────────┐               │
│  Agent 2: Editor / Ctrl  │               │
│  • Enforces constraints  │               │
│    – Max lines           │               │
│    – Emojis yes / no     │               │
│  • Tightens & compresses │               │
└─────────────┬────────────┘               │
              │                            │
              ▼                            │
┌──────────────────────────┐               │
│  Human-in-the-Loop       │               │
│  • Approve               │               │
│  • Reject + feedback     │───────────────┘
└─────────────┬────────────┘
              │
              ▼
        ✅ Final Post

```
# Agent Workflow Deep Dive

Agentic workflow for generating LinkedIn posts using CrewAI and the OpenAI API, with an optional human-in-the-loop review step.

Features
- Compose and iterate LinkedIn post drafts using modular agents.
- Store preferences and outputs in `memory/`.
- Interactive exploration via Jupyter notebooks in `notebooks/`.

Requirements
- Python 3.9+ recommended
- See `requirements.txt` for Python dependencies

Quick start
1. Create a Python virtual environment (recommended):

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

2. Provide your OpenAI API key (example using environment variable):

```bash
export OPENAI_API_KEY="sk-..."
# or create a .env file and load it from your environment
```

3. Open the notebooks to run the agent workflows:

```bash
jupyter lab notebooks/
```

Project layout
- `notebooks/` — Jupyter notebooks (main interface for experiments)
- `agents/` — agent definitions and orchestration code
- `memory/` — saved outputs, caches, and preferences
- `requirements.txt` — Python package dependencies

Notes
- This repository is designed as a starting point. Some agent modules may be placeholders or prototypes.
- If you use GitHub Codespaces, add `OPENAI_API_KEY` as a repository secret (`Settings → Secrets and variables → Codespaces`) to inject the key into the environment for convenience.

Contributing
- Please open issues or pull requests with improvements or bug fixes.

License
- See repository license (if any) or contact the maintainer.
