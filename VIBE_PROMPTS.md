# VIBE PROMPTS

This section details the operational prompts available to the AI Agent, outlining their purpose and guidance for effective use in various software development tasks.

This section details the operational prompts available to the AI Agent, outlining their purpose and guidance for effective use in various software development tasks.

### Prompts List

1.  `PLAN_NEW_PROJECT`
2.  `REFACTOR`
3.  `UPDATE_TODO`
4.  `UPDATE_DOC`
5.  `REVIEW_README`
6.  `REVIEW_TEST`
7.  `ADD_LOGS`
8.  `APPLY_CHECKPOINT`
9.  `COMMIT_CHANGES`

---

### `PLAN_NEW_PROJECT`

*(Guidance: Primarily use **ARCHITECT** mode. Refer explicitly to the "New Application/System Planning Guidance" section and General Conventions.)*

**Task:** Initiate the planning process for a new application or system based on the user's initial idea, brief, or quickstart. If no initial description is provided, ask the user for one. Follow the steps outlined in the "New Application/System Planning Guidance" section. Start by asking clarifying questions to fully understand the project's vision and goals. Collaborate closely with the user throughout all planning steps.

---

### `REFACTOR`

*(Guidance: Primarily use **CODE** mode. Refer to General Conventions, especially SOLID, documentation, types, dependencies, and testing.)*

**Task:** Refactor the referenced module/script, breaking it into submodules/scripts and ensuring the main script still works as previously stated. Group similar functions/classes into submodules or use one module per function/class, whichever is more efficient.

**Also:**

1.  **Docstrings:** Add/Review existing docstrings in functions and classes to ensure they align with the defined guidelines (in **ENGLISH**) and accurately describe the corresponding code. Add any missing or incomplete docstrings.
2.  **Type Hints:** Verify type hints to ensure they correctly represent the function/method code. Add any missing or incorrect type hints.
3.  **Dependencies:** Identify necessary dependencies and packages for the script and add them to the project using the appropriate dependency management tool (see General Conventions).
4.  **Cleanup:** Remove unused imports and unnecessary comments.
5.  **Behavior:** **GUARANTEE THAT THE PREVIOUS BEHAVIOR OF THE ORIGINAL MODULE IS MAINTAINED.**

---

### `UPDATE_TODO`

*(Guidance: Use **ARCHITECT** or **CODE** mode. Refer to General Conventions.)*

**Task:** Create or update the `TODO.md` task list file by comparing what is defined in `@/SPEC.md` (if it exists) with what was implemented as described in `@/README.md` and `@/DOC.md`. For each feature, include the feature name from `TOOLS.md` (if applicable) and check: was it initialized? was it implemented? was it tested? How much? Check the `@coverage.xml` (read-only) for this information.

**Also:**

1.  **README:** Update the `README.md` file to include links to the `DOC.md` and `TODO.md` files with brief descriptions of them.

---

### `UPDATE_DOC`

*(Guidance: Use **ARCHITECT** or **CODE** mode. Refer to General Conventions.)*

**Task:** Analyze the referenced script (if a single one is provided) or each script file in the referenced folder and perform the following tasks one by one:

1.  **Documentations:** Create or update the `DOC.md` with a full documentation for this script/project in order to be used to guide AI Agents to understand the code and its behavior and use its functionality. 

**Also:**

1.  **README:** Update the `README.md` file to include link to the `DOC.md`.

---

### `REVIEW_README`

*(Guidance: Use **ASK** or **ARCHITECT** mode. **DO NOT MODIFY ANY CODE**.)*

**Task:** Analyze the referenced script (if a single one is provided) or each script file in the referenced folder and perform the following tasks one by one:

1.  **Docstrings:** Add/Review existing docstrings (in **ENGLISH**) to ensure they align with guidelines and accurately describe the code. Add missing/incomplete ones. Change ONLY that ones that are missing, incomplete, outdated or incorrect. **DO NOT MODIFY ANY OTHER CODE.**
2.  **Type Hints:** Verify type hints to ensure they correctly represent the code. Add missing/incorrect ones.
3.  **Dependencies:** Identify and install necessary/missing packages using the appropriate dependency management tool (see General Conventions, remember to consult the project's dependency manifest file first).
4.  **Cleanup:** Identify unused imports and unnecessary comments. **Remove them.**
5.  **README:** Create or update the `README.md` file with  BASIC information about the project's MAIN purpose and  functionalities, making it suitable for GitHub publication.
6.  **Restriction:** **DO NOT MODIFY ANY EXISTING CODE.**

---

### `REVIEW_TEST`

*(Guidance: Use **CODE** and **DEBUG** modes. Refer to General Conventions, especially testing rules (including TDD), documentation, types, and dependencies.)*

**Task:** Analyze the referenced module/script and perform the following tasks:

1.  **Docstrings:** Add/Review existing docstrings (in **ENGLISH**) to ensure they align with guidelines and accurately describe the code. Add missing/incomplete ones.
2.  **Type Hints:** Verify type hints to ensure they correctly represent the code. Add missing/incorrect ones.
3.  **Dependencies:** Identify and install necessary/missing packages using the appropriate dependency management tool (see General Conventions, remember to consult the project's dependency manifest file first).
4.  **Cleanup:** Remove unused imports.
5.  **Unit Tests:** Write unit tests for all functions, classes, and methods in the code, following these directives:
    *   Use the `pytest` framework.
    *   Follow the naming convention: `test_<module_name>_<function>_<scenario>.py`.
    *   Create `tests/<module_name>` folders if they don't already exist.
    *   If the `tests/<module_name>` folder exists, check for existing successful tests. Create only missing tests; do not overwrite existing ones.
    *   **CODE COVERAGE AFTER ALL TESTS MUST BE >= 90%.**
    *   Use **mocking** strategies for external dependencies.
    *   Design tests to achieve the **highest possible coverage** of existing scenarios. Apply TDD principles where applicable (ensure tests reflect requirements defined during planning or before coding).
    *   Ensure the virtual environment is activated before running tests.
    *   **ALWAYS USE THE SYSTEM TEMPORARY FOLDER** for test files/objects.
    *   Use functions for tests; avoid test classes if possible.
    *   Keep test files small (max 450 lines), breaking down scenarios if necessary.
    *   Execute full tests with: `uv run pytest -s -vv --cov=<module_name> --cov-report=xml:coverage.xml --cov-report=html:coverage_html --cov-fail-under=90 tests/`
    *   Execute specific script tests with: `uv run pytest -s -vv --cov=<module_name> --cov-report=xml:coverage.xml --cov-report=html:coverage_html --cov-fail-under=90 tests/<test_script>`
    *   When encountering test errors, tackle them one by one until they pass: `uv run pytest -s -vv -k <scenario> tests/<test_script>`

---

### `ADD_LOGS`

*(Guidance: Use **CODE** mode. Refer to General Conventions regarding logging.)*

**Task:** Analyze the referenced script and perform the following tasks:

1.  **Add Logs:** Add useful logging information to the script.
2.  **Use Existing Logger:** **Always use the available logging object.** If not available, ask to create one.
3.  **Log Levels:** Use the following log levels appropriately: `DEBUG`, `INFO`, `WARNING`, `ERROR`, `CRITICAL`.
4.  **Replace Prints:** Replace `print()` statements with logging statements where appropriate (for debugging or flow information).
5.  **Restriction:** **DO NOT MODIFY ANY EXISTING CODE, ONLY ADD THE LOGGING STATEMENTS.**

---

---

### `APPLY_CHECKPOINT`

*(Guidance: Use **CODE** mode, interacting with the version control system.)*

**Task:** Include the pattern `CKP_*.md` in the repository's `.gitignore` file. Verify all changes made in the repository using appropriate git commands to:
  - Check which files were created.
  - Check which files were deleted.
  - Check which files were modified.
  - Analyze changes by comparing differences between previous and new versions (diff).
  - Summarize changes in a suitable git commit message that synthesizes the detected changes.
  - Request the user to immediately apply the commit with the generated message or create a `.md` file with this message for a later commit. The file should follow the pattern `CKP_<timestamp>.md`.

---

### `COMMIT_CHANGES`

*(Guidance: Use **CODE** mode, interacting with the version control system.)*

**Task:** Analyze the referenced script/folder and perform the following tasks using the `git` command line:

1.  **Check Status:** Discover file changes with: `git status`.
2.  **Group Changes:** Group changes by nature: modifications, new files, deletions.
3.  **Add to Staging:** Use `git add <file>` to add changes and new files to the staging area.
4.  **Check Diffs:** Use `git diff` or `git diff --staged` to see the changes in each file and compose your commit message.
5.  **Commit:** Commit each group of changes with a meaningful but not too long message (less than 150 characters), in **BRAZILIAN PORTUGUESE** and in technical but simple language, using: `git commit -m "<message>"`.
