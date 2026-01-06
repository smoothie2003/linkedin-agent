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
OpenAI API Key Setup (Required)
This project uses the OpenAI API through CrewAI.

The API key must be provided via an environment variable named:

nginx
Copy code
OPENAI_API_KEY
Recommended Setup: GitHub Codespaces
# LinkedIn Agent

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
