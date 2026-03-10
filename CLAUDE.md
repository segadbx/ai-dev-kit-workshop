# Claude Code Instructions

## Project Overview

This is an AI-DevKit Vibe Coding Workshop repository for building Databricks solutions using AI coding assistants.

## Code Organization

**All generated code must be placed in the `src/` folder.**

When creating new files:
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
3. **Databricks patterns**: Follow Databricks best practices for Unity Catalog, Delta Lake, and PySpark.
4. **Modular code**: Create reusable functions and modules within the `src/` directory structure.
