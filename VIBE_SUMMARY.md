# Vibe Prompts Summary

Based on the `VIBE_GUIDE.md` file, the registered prompts and their purposes, ordered by a suggested execution precedence for developing a Vibe project, are:

1.  **`PLAN_NEW_PROJECT`**: Initiates the planning process for a new application or system, understanding the vision, defining requirements, scope, high-level architecture, technology, and planning tests and documentation.
2.  **`REVIEW_README`**: Analyzes script files or folders to add/review docstrings and type hints, identify and install dependencies, remove unused code, and create/update the README.md file with basic project information. **Does not modify existing code other than docstrings, type hints, dependencies, and cleanup.**
3.  **`REFACTOR`**: Refactors a referenced module/script, breaking it into submodules/scripts while ensuring the original behavior is maintained. Includes adding/reviewing docstrings and type hints, identifying dependencies, and cleaning up code.
4.  **`REVIEW_TEST`**: Analyzes a module/script to add/review docstrings and type hints, identify dependencies, remove unused code, and write unit tests using pytest, aiming for high code coverage (>= 90%).
5.  **`ADD_LOGS`**: Adds useful logging information to a referenced script, using an existing logging object and appropriate levels (DEBUG, INFO, WARNING, ERROR, CRITICAL), replacing `print()` with logging calls. **Does not modify existing code other than adding logs.**
6.  **`UPDATE_DOC`**: Creates or updates the DOC.md file with full documentation for a script or project, intended to guide other AI Agents in understanding and using the code. Also updates the README.md with a link to DOC.md.
7.  **`UPDATE_TODO`**: Creates or updates the TODO.md task list file by comparing specifications (SPEC.md) with the implementation (README.md, DOC.md) and coverage information (coverage.xml), listing the status of initialization, implementation, and testing for each feature. Also updates the README.md with links to DOC.md and TODO.md.

## Utility Prompts

Prompts that are not part of the main sequential development flow but serve utility purposes:

| Prompt Name       | Purpose                                                                                                                               |
| :---------------- | :------------------------------------------------------------------------------------------------------------------------------------ |
| `COMMIT_CHANGES`  | Uses git command line to check file status, group changes, add to staging, review diffs, and commit changes with meaningful messages. |

## Vibe Development Flow

::: mermaid
graph TD
    A[Start] --> B{New Application?};
    B -- Yes --> C[PLAN_NEW_PROJECT];
    C --> D[Define Requirements/Scope];
    D --> E[Propose Architecture/Technology];
    E --> F[Plan Tests TDD];
    F --> G[Plan Documentation];
    G --> H[Review and Finalize Plan];
    H --> I{Plan Approved?};
    I -- Yes --> J[Start Implementation];
    I -- No --> D;
    
    B -- No --> J[Start Implementation];

    J --> K{Development/Review Task?};
    K -- Yes --> L{Which Task?};
    L -- Refactor --> M[REFACTOR];
    L -- Review README --> N[REVIEW_README];
    L -- Review Tests --> O[REVIEW_TEST];
    L -- Add Logs --> P[ADD_LOGS];
    L -- Update Documentation --> Q[UPDATE_DOC];
    L -- Update TODO --> R[UPDATE_TODO];

    M --> K;
    N --> K;
    O --> K;
    P --> K;
    Q --> K;
    R --> K;

    K -- No --> U[End];

    subgraph Utility Prompts
        S[COMMIT_CHANGES]
    end
:::
