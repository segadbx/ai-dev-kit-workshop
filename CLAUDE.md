# Claude Code Instructions

## Project Overview

This is an AI-DevKit Vibe Coding Workshop repository for building Databricks solutions using AI coding assistants.

## Code Organization

**All generated code must be placed in the `src/` folder.**

When creating new files (within the `usecases/<usecase>/bundle` directory):
- Python modules: `src/*.py` or `src/<module_name>/*.py`
- Notebooks: `src/notebooks/*.py` or `src/notebooks/*.ipynb`
- SQL files: `src/sql/*.sql`
- Configuration files: `src/config/`

## Project Structure

```
src/
├── notebooks/       # Databricks notebooks
├── sql/            # SQL queries and scripts
├── config/         # Configuration files
└── *.py            # Python modules and scripts
```

## Guidelines

1. **Use case context**: Read `usecases/<name>/context.md` for business and data context before implementing.
2. **Follow skills**: Reference `usecases/<name>/skills.md` for implementation guidance.
3. **Comprehensive Implementation Plan**: Each use case or User story must be presented as a `usecases/<name>/tasks.md` that includes full breakdown of the use case by tasks; then the implementation (code building) can be started.
3. **Databricks patterns**: use Databricks skills to build Databricks components; each use case implementation must include as much as possible the presentation (Dashboard, Application).
4. **Deployable Artifacts**: the `src/` output must be a configurable (without hardcoded variables and values) Databricks Asset Bundle.
5. **Modular code**: Create reusable functions and modules within the `src/` directory structure.
6. **Context Lineage**: Every `tasks.md` file must contain references to the `context.md` and `skills.md` files within the folder where the `tasks.md` is created.
7. **Serverless Compute**: Every Databricks resource must use the Serverless compute type.
