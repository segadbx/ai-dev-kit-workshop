# AI‑DevKit Vibe Coding Workshop

Welcome to the **AI‑DevKit Vibe Coding Workshop** repo.  
You’ll use your preferred AI coding assistant (Cursor, Claude Code, Copilot, etc.) to build against **real Databricks use cases**, using this repository as your starting point.

The goal is **not** to hand‑code everything; it is to **describe → generate → test → refine** with an AI assistant and ship something useful by the end of the session.

---

## 1. Workshop goals

By the end of the workshop, participants will:

- Practice **vibe coding** with AI assistants on top of Databricks.
- Build thin‑slice implementations for **3–5 real use cases**.
- Build Databricks resources and deploy them to a Databtricks workspace using [AI-Dev-Kit](https://github.com/databricks-solutions/ai-dev-kit)
- Leave with:
  - Working notebooks / scripts / small apps.
  - A **prompt + code pattern** they can reuse on future work.

---

## 2. Who this is for

- **Primary:** Data engineers, ML engineers, analytics engineers, app developers.
- **Secondary:** Technical product owners / architects who want to see how vibe coding can accelerate delivery.

You should be comfortable reading Python/SQL and running notebooks, but you do **not** need to be an expert app developer.

---

## 3. Prerequisites

### 3.1. Access & environment

Before the workshop:

1. **Databricks workspace**
  - Access to the target workspace.
  - Unity Catalog enabled.
  - Permission to:
    - Read the datasets used by the use cases (**note:** mock data can be generated during the workshop).
    - Create notebooks, jobs, and tables in a sandbox catalog/schema.
2. **Git & GitHub**
  - `git` installed on your laptop.
  - Ability to clone this repository (no firewall/proxy blocks).
3. **Python / runtime**
  - A recent Python (3.9+) installed **or**
  - A Databricks Runtime you can use for notebooks (recommended).
4. **Code editor**
  - VS Code, Cursor, IntelliJ, or any editor you’re comfortable with.

### 3.2. AI coding assistant

You must have **at least one** of the following set up:

- Cursor
- Claude Code (CLI or IDE integration)
- GitHub Copilot (with chat)
- Another agentic coding tool that can:
  - Read this repo.
  - Edit files.
  - Run or suggest shell/terminal commands.

**Model quality matters.** Use the best reasoning‑capable model you can (e.g., Claude Sonnet 4.5+ or equivalent) for a better experience.

---

## 4. Repository structure

At a high level:

```text
.
├── README.md               # You are here
├── common/
│   ├── PROMPTING_GUIDE.md  # Vibe coding tips & examples
│   └── TROUBLESHOOTING.md  # Common issues & fixes
├── env/
│   ├── requirements.txt    # Optional Python deps (if running locally)
│   └── bootstrap.sh        # Optional setup helper (if provided)
└── usecases/
    ├── <usecase-1>/
    │   ├── context.md      # Business + data context for this use case
    │   ├── skill.md        # Instructions for your coding agent (prompts by stage)
    │   └── tasks.md        # Concrete tasks to complete during the workshop
    ├── <usecase-2>/
    │   └── ...
    └── <usecase-n>/
        └── ...
```

Each **use case folder** is self‑contained: you can work on one without needing the others.

---

## 5. Getting started

### 5.1. Clone the repo

```bash
git clone <REPO_URL>
cd <REPO_DIR>
```

If you’re using an IDE like Cursor or VS Code, open this folder as your project.

### 5.2. (Optional) Set up a local Python env

If you plan to run code locally instead of (or in addition to) Databricks:

```bash
python -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate
pip install -r env/requirements.txt
```

If you prefer to run everything in Databricks notebooks, you can skip this and just treat the repo as source files that your assistant edits.

### 5.3. Configure your AI coding assistant

Typical steps (details vary by tool):

1. Point the assistant at the **root of this repo** so it can see:
  - `usecases/**/context.md`
  - `usecases/**/skill.md`
  - `usecases/**/tasks.md`
2. Configure any Databricks integrations (if supported by your tool):
  - Workspace URL, PAT/SSO, cluster/warehouse to use.
3. Test with a simple question, e.g.:

> “Read `usecases/<usecase-1>/context.md` and summarize the business problem in 3 bullets.”

---

## 6. How to work with a use case

For each use case, you’ll follow the same pattern:

1. **Pick a use case**
  Choose a folder under `usecases/` (your facilitator may assign one).
2. **Read the context**
  Open `context.md` in that folder and read it (or ask your AI assistant to summarize it).
3. **Load the skill**
  Open `skill.md` in the same folder. This file contains the **instructions for the vibe‑coding agent**, organized by stage:
  - `1-Validating` – prove the data is accessible and the idea is feasible.
  - `2-Scoping` – shape the MVP and key components.
  - `3-Evaluating` – add basic evaluation/metrics/backtests.
  - `4-Confirming` – package it for repeatable use (jobs, services, docs).
   You can:
  - Paste sections of `skill.md` into your assistant, or
  - Ask your assistant to **“adopt”** the skill file as context and follow its steps.
4. **Follow the tasks**
  Open `tasks.md` for a list of concrete exercises. For each task:
  - Start by telling your assistant *what you want*, referencing the task.
  - Let it propose code/changes.
  - Run/validate, then iterate.
   Example prompt pattern:
    > “Using the instructions in `usecases/4cp-forecasting/skill.md` for the `1-Validating` stage and Task 1 in `tasks.md`, generate a Databricks notebook that:
    >
    > - reads the 4CP-related tables from Unity Catalog, and  
    > - computes a simple daily max load per site into a new Delta table.”

---

## 7. Recommended workflow (Vibe Coding loop)

Throughout the workshop, we want you to **lean on the AI agent**:

1. **Describe**
  - Explain the goal in natural language.
  - Point to `context.md`, `skill.md`, and `tasks.md` so it can use them.
2. **Generate**
  - Let the assistant propose code, notebooks, or file edits.
  - Ask it to explain what it changed.
3. **Test**
  - Run the code (locally or on Databricks).
  - Capture any errors or unexpected behavior.
4. **Refine**
  - Paste errors back to the assistant.
  - Ask for targeted fixes (not a full rewrite unless necessary).
5. **Repeat** until you hit the task’s **Definition of Done**.

If you find yourself manually writing long functions from scratch, that’s a signal to **hand more work to the agent**.

---

