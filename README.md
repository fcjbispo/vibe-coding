# AI Software Development Agent - Configuration & Guidelines

This repository contains the configuration files, operational guidelines, and standard procedures for an AI agent specialized in software development tasks. These files define the agent's behavior, modes of operation, coding conventions, and task-specific prompts.

## Overview

The core components defining the agent's operation are:

*   **`VIBE.md`**: The central guide outlining general conventions, SOLID principles, testing strategies, dependency management (`uv`), logging practices, operational modes, and specific task prompts. This is the primary instruction set.
*   **`CONVENTIONS.md`**: Details specific coding standards, SOLID principles application, testing guidelines (including TDD), documentation rules, and general best practices the agent must follow.
*   **`MODES.md`**: Defines the different operational personas or modes the agent can adopt (`CODE`, `ARCHITECT`, `ASK`, `DEBUG`), each tailored for specific types of tasks.
*   **`REVISION_PROMPTS.md`**: Provides detailed templates and instructions for common software development tasks like refactoring, updating TODO lists, reviewing code, adding tests, adding logs, and committing changes.
*   **`VIBE_SUMMARY.md`**: Provides a summary of the Vibe prompts and a development flow diagram.

## Purpose

The goal of this configuration is to ensure the AI agent operates consistently, efficiently, and according to best practices in software engineering. It provides a framework for:

*   **Planning:** Architecting new applications based on user requirements.
*   **Coding:** Writing clean, documented, and type-hinted code.
*   **Refactoring:** Improving existing code structure and maintainability.
*   **Testing:** Implementing comprehensive unit tests using `pytest` with high coverage.
*   **Debugging:** Systematically diagnosing and resolving issues.
*   **Documentation:** Maintaining clear and accurate project documentation.
*   **Version Control:** Using `git` effectively for managing changes.

## Key Principles

*   **Language:** Code and documentation are written in English. User interaction is in Brazilian Portuguese.
*   **SOLID Principles:** Strictly followed in all code design.
*   **Testing:** Emphasis on high code coverage (>=90%) using `pytest`.
*   **Dependencies:** Managed using `uv`.
*   **Logging:** Integrated for debugging and monitoring.
*   **Clean Code:** Focus on readability, maintainability, and avoiding duplication.

Refer to the individual `.md` files for detailed specifications on each aspect.
