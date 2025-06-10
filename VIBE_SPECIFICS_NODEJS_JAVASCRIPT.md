# VIBE SPECIFICS - Node.js/JavaScript

This document contains guidelines, code examples, and references to specific tools/libraries for the Node.js/JavaScript ecosystem, aligned with the `VIBE_GUIDE.md`.

## General Guidelines
*   Use npm or yarn for package management.
*   Follow JavaScript/TypeScript coding conventions (e.g., camelCase for variables and functions, PascalCase for classes).
*   Prioritize modularity and functional programming paradigms.

## Testing
*   Use Jest, Mocha, or Vitest for unit tests and Sinon.js for mocking.
*   Example of test execution: `npm test` or `yarn test`.

## Dependency Management
*   `package.json` for project dependencies.

## 1. Environment and Dependency Management
*   **Package Managers:** Use npm or yarn for managing project dependencies.
*   **Node.js Versioning:** Use tools like `nvm` or `fnm` to manage Node.js versions for consistency across environments.
*   **Type Safety:** Utilize TypeScript for type safety in larger projects. For JavaScript, use JSDoc for type annotations and IDE support.

## 2. Testing
*   **Frameworks:** Use Jest, Mocha, or Vitest for unit tests.
*   **Mocking:** Use mocking libraries like Sinon.js or built-in Jest mocking for isolating dependencies.
*   **Test Execution:** Run tests using `npm test` or `yarn test`.
*   **Code Coverage:** Integrate code coverage tools like Istanbul/nyc. Configure scripts in `package.json` for coverage reports.

## 3. Prompts Specifics

### 3.1. REFACTOR
*   **Guidance:** Primarily use **CODE** mode. Refer to General Conventions, especially SOLID, documentation, types, dependencies, and testing.
*   **Task:** Refactor the referenced module/script, breaking it into submodules/scripts and ensuring the main script still works as previously stated. Group similar functions/classes into submodules or use one module per function/class, whichever is more efficient.
*   **Also:**
    1.  **Docstrings/JSDoc:** Add/Review existing JSDoc comments in functions, classes, and modules to ensure they align with defined guidelines (in **ENGLISH**) and accurately describe the corresponding code. Add any missing or incomplete comments.
    2.  **Type Hints:** Verify type hints (TypeScript or JSDoc) to ensure they correctly represent the function/method code. Add any missing or incorrect type hints.
    3.  **Dependencies:** Identify necessary dependencies and packages for the script and add them to the project using npm or yarn (e.g., `npm install <package-name>` or `yarn add <package-name>`).
    4.  **Cleanup:** Remove unused imports and unnecessary comments.
    5.  **Behavior:** **GUARANTEE THAT THE PREVIOUS BEHAVIOR OF THE ORIGINAL MODULE IS MAINTAINED.**

### 3.2. REVIEW_README
*   **Guidance:** Use **ASK** or **ARCHITECT** mode. **DO NOT MODIFY ANY CODE.**
*   **Task:** Analyze the referenced script (if a single one is provided) or each script file in the referenced folder and perform the following tasks one by one:
    1.  **Docstrings/JSDoc:** Add/Review existing JSDoc comments (in **ENGLISH**) to ensure they align with guidelines and accurately describe the code. Add missing/incomplete ones. Change ONLY that ones that are missing, incomplete, outdated or incorrect. **DO NOT MODIFY ANY OTHER CODE.**
    2.  **Type Hints:** Verify type hints (TypeScript or JSDoc) to ensure they correctly represent the code. Add missing/incorrect ones.
    3.  **Dependencies:** Identify and install necessary/missing packages using npm or yarn (see General Conventions, remember to consult the project's dependency manifest file first).
    4.  **Cleanup:** Identify unused imports and unnecessary comments. **Remove them.**
    5.  **README:** Create or update the `README.md` file with BASIC information about the project's MAIN purpose and functionalities, making it suitable for GitHub publication.
    6.  **Restriction:** **DO NOT MODIFY ANY EXISTING CODE.**

### 3.3. REVIEW_TEST
*   **Guidance:** Use **CODE** and **DEBUG** modes. Refer to General Conventions, especially testing rules (including TDD), documentation, types, and dependencies.
*   **Task:** Analyze the referenced module/script and perform the following tasks:
    1.  **Docstrings/JSDoc:** Add/Review existing JSDoc comments (in **ENGLISH**) to ensure they align with guidelines and accurately describe the code. Add missing/incomplete ones.
    2.  **Type Hints:** Verify type hints (TypeScript or JSDoc) to ensure they correctly represent the code. Add missing/incorrect ones.
    3.  **Dependencies:** Identify and install necessary/missing packages using npm or yarn (see General Conventions, remember to consult the project's dependency manifest file first).
    4.  **Cleanup:** Remove unused imports.
    5.  **Unit Tests:** Write unit tests for all functions, classes, and methods in the code, following these directives:
        *   Use Jest, Mocha, or Vitest frameworks.
        *   Follow the naming convention: `<filename>.test.js` or `<filename>.spec.js` (for JavaScript), `<filename>.test.ts` or `<filename>.spec.ts` (for TypeScript).
        *   Create `__tests__` or `tests` folders if they don't already exist.
        *   If the test folder exists, check for existing successful tests. Create only missing tests; do not overwrite existing ones.
        *   **CODE COVERAGE AFTER ALL TESTS MUST BE >= 90%.**
        *   Use **mocking** strategies for external dependencies (e.g., Sinon.js, Jest's built-in mocks).
        *   Design tests to achieve the **highest possible coverage** of existing scenarios. Apply TDD principles where applicable (ensure tests reflect requirements defined during planning or before coding).
        *   Ensure the isolated development environment is activated before running tests.
        *   **ALWAYS USE THE SYSTEM TEMPORARY FOLDER** for test files/objects.
        *   Use functions for tests; avoid test classes if possible, or keep them focused.
        *   Keep test files small (max 450 lines), breaking down scenarios if necessary.
        *   Execute full tests with: `npm test -- --coverage` or `yarn test --coverage`.
        *   Execute specific script tests with: `npm test <path/to/test-file>` or `yarn test <path/to/test-file>`.
        *   When encountering test errors, tackle them one by one until they pass.
