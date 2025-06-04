# VIBE ESPECIFICS - Python

Este documento contém diretrizes, exemplos de código e referências a ferramentas/bibliotecas específicas para a linguagem Python, extraídas do `VIBE_GUIDE.md`.

## 5. Environment and Dependency Management (Python)
*   **ALWAYS** check if a virtual environment exists and activate it before running commands (`source .venv/bin/activate` or similar).
*   **ALWAYS** use the `uv` tool to manage packages and run Python code.
*   Use `uv add [package_name]` for regular dependencies.
*   Use `uv add --group dev [package_name]` for development dependencies (e.g., `pytest`, `pytest-cov`).
*   **ALWAYS** read the `@pyproject.toml` file before determining what should be installed to avoid duplication or conflicts.

## 9. Testing (Python Specifics)
*   Use `pytest` for tests and `pytest-cov` for code coverage in Python.
*   Execute full tests with: `uv run pytest -s -vv --cov=<module_name> --cov-report=xml:coverage.xml --cov-report=html:coverage_html --cov-fail-under=90 tests/`
*   Execute specific script tests with: `uv run pytest -s -vv --cov=<module_name> --cov-report=xml:coverage.xml --cov-report=html:coverage_html --cov-fail-under=90 tests/<test_script>`
*   When encountering test errors, tackle them one by one until they pass: `uv run pytest -s -vv -k <scenario> tests/<test_script>`

## Prompts Specifics

### `REFACTOR` (Python Specifics)
*   **Dependencies:** Identify necessary dependencies and packages for the script and add them to the project using the `uv` tool (see General Conventions).

### `REVIEW_README` (Python Specifics)
*   **Dependencies:** Identify and install necessary/missing packages using `uv` (see General Conventions, remember to check `pyproject.toml` first).

### `REVIEW_TEST` (Python Specifics)
*   Use the `pytest` framework.
*   Execute full tests with: `uv run pytest -s -vv --cov=<module_name> --cov-report=xml:coverage.xml --cov-report=html:coverage_html --cov-fail-under=90 tests/`
*   Execute specific script tests with: `uv run pytest -s -vv --cov=<module_name> --cov-report=xml:coverage.xml --cov-report=html:coverage_html --cov-fail-under=90 tests/<test_script>`
*   When encountering test errors, tackle them one by one until they pass: `uv run pytest -s -vv -k <scenario> tests/<test_script>`
