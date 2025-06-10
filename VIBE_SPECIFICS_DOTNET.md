# VIBE SPECIFICS - .NET

This document contains guidelines, code examples, and references to specific tools/libraries for the .NET platform, aligned with the `VIBE_GUIDE.md`.

## General Guidelines
*   Use NuGet for package management.
*   Follow .NET coding conventions (e.g., PascalCase for public members, camelCase for private fields).
*   Prioritize the use of interfaces and dependency injection.

## Testing
*   Use xUnit, NUnit, or MSTest for unit tests and Moq for mocking.
*   Example of test execution: `dotnet test`.

## Dependency Management
*   `*.csproj` files for project dependencies.

## 1. Environment and Dependency Management
*   **Package Manager:** Use NuGet for managing project dependencies.
*   **SDK Versioning:** Use `global.json` to specify the .NET SDK version for consistent development environments.
*   **Type Safety:** C# is a strongly-typed language; ensure all variables, parameters, and return types are explicitly defined.

## 2. Testing
*   **Frameworks:** Use xUnit, NUnit, or MSTest for unit tests.
*   **Mocking:** Use mocking frameworks like Moq or NSubstitute for isolating dependencies in tests.
*   **Test Execution:** Run tests using `dotnet test`.
*   **Code Coverage:** Integrate code coverage tools like Coverlet. To collect coverage, use `dotnet test --collect:"XPlat Code Coverage"`.

## 3. Prompts Specifics

### 3.1. REFACTOR
*   **Guidance:** Primarily use **CODE** mode. Refer to General Conventions, especially SOLID, documentation, types, dependencies, and testing.
*   **Task:** Refactor the referenced module/script, breaking it into submodules/scripts and ensuring the main script still works as previously stated. Group similar functions/classes into submodules or use one module per function/class, whichever is more efficient.
*   **Also:**
    1.  **Docstrings/XML Comments:** Add/Review existing XML documentation comments in functions, classes, and interfaces to ensure they align with defined guidelines (in **ENGLISH**) and accurately describe the corresponding code. Add any missing or incomplete comments.
    2.  **Type Hints:** Verify type hints (explicit types in C#) to ensure they correctly represent the function/method code. Add any missing or incorrect type hints.
    3.  **Dependencies:** Identify necessary dependencies and packages for the script and add them to the project using NuGet (e.g., `dotnet add package <PackageName>`).
    4.  **Cleanup:** Remove unused usings and unnecessary comments.
    5.  **Behavior:** **GUARANTEE THAT THE PREVIOUS BEHAVIOR OF THE ORIGINAL MODULE IS MAINTAINED.**

### 3.2. REVIEW_README
*   **Guidance:** Use **ASK** or **ARCHITECT** mode. **DO NOT MODIFY ANY CODE.**
*   **Task:** Analyze the referenced script (if a single one is provided) or each script file in the referenced folder and perform the following tasks one by one:
    1.  **Docstrings/XML Comments:** Add/Review existing XML documentation comments (in **ENGLISH**) to ensure they align with guidelines and accurately describe the code. Add missing/incomplete ones. Change ONLY that ones that are missing, incomplete, outdated or incorrect. **DO NOT MODIFY ANY OTHER CODE.**
    2.  **Type Hints:** Verify type hints (explicit types in C#) to ensure they correctly represent the code. Add missing/incorrect ones.
    3.  **Dependencies:** Identify and install necessary/missing packages using NuGet (see General Conventions, remember to consult the project's dependency manifest file first).
    4.  **Cleanup:** Identify unused usings and unnecessary comments. **Remove them.**
    5.  **README:** Create or update the `README.md` file with BASIC information about the project's MAIN purpose and functionalities, making it suitable for GitHub publication.
    6.  **Restriction:** **DO NOT MODIFY ANY EXISTING CODE.**

### 3.3. REVIEW_TEST
*   **Guidance:** Use **CODE** and **DEBUG** modes. Refer to General Conventions, especially testing rules (including TDD), documentation, types, and dependencies.
*   **Task:** Analyze the referenced module/script and perform the following tasks:
    1.  **Docstrings/XML Comments:** Add/Review existing XML documentation comments (in **ENGLISH**) to ensure they align with guidelines and accurately describe the code. Add missing/incomplete ones.
    2.  **Type Hints:** Verify type hints (explicit types in C#) to ensure they correctly represent the code. Add missing/incorrect ones.
    3.  **Dependencies:** Identify and install necessary/missing packages using NuGet (see General Conventions, remember to consult the project's dependency manifest file first).
    4.  **Cleanup:** Remove unused usings.
    5.  **Unit Tests:** Write unit tests for all functions, classes, and methods in the code, following these directives:
        *   Use xUnit, NUnit, or MSTest frameworks.
        *   Follow the naming convention: `Test_<ClassName>_<MethodName>_<Scenario>.cs`.
        *   Create `Tests/<ProjectName>` folders if they don't already exist.
        *   If the `Tests/<ProjectName>` folder exists, check for existing successful tests. Create only missing tests; do not overwrite existing ones.
        *   **CODE COVERAGE AFTER ALL TESTS MUST BE >= 90%.**
        *   Use **mocking** strategies for external dependencies (e.g., Moq, NSubstitute).
        *   Design tests to achieve the **highest possible coverage** of existing scenarios. Apply TDD principles where applicable (ensure tests reflect requirements defined during planning or before coding).
        *   Ensure the isolated development environment is activated before running tests.
        *   **ALWAYS USE THE SYSTEM TEMPORARY FOLDER** for test files/objects.
        *   Use methods for tests; avoid test classes if possible, or keep them focused.
        *   Keep test files small (max 450 lines), breaking down scenarios if necessary.
        *   Execute full tests with: `dotnet test --collect:"XPlat Code Coverage" --results-directory ./TestResults/ --logger "trx;LogFileName=test_results.trx"`.
        *   Execute specific script tests with: `dotnet test --filter "FullyQualifiedName~<TestClassName>"`.
        *   When encountering test errors, tackle them one by one until they pass.
