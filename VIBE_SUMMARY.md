# Vibe Prompts Summary

Based on the `VIBE_GUIDE.md` file, the registered prompts and their purposes, ordered by a suggested execution precedence for developing a Vibe project, are:

1.  **`PLAN_NEW_PROJECT`**: Initiates the planning process for a new application or system, understanding the vision, defining requirements, scope, high-level architecture, technology, and planning tests and documentation.
2.  **`REFACTOR`**: Refactors a referenced module/script, breaking it into submodules/scripts while ensuring the original behavior is maintained. Includes adding/reviewing docstrings and type hints, identifying dependencies using the appropriate dependency management tool, and cleaning up code.
3.  **`UPDATE_TODO`**: Creates or updates the `TODO.md` task list file by comparing what is defined in `@/SPEC.md` (if it exists) with what was implemented as described in `@/README.md` and `@/DOC.md`. For each feature, include the feature name from `TOOLS.md` (if applicable) and check: was it initialized? was it implemented? was it tested? How much? Check the `@coverage.xml` (read-only) for this information. Also updates the `README.md` file to include links to the `DOC.md` and `TODO.md` files with brief descriptions of them.
4.  **`UPDATE_DOC`**: Creates or updates the `DOC.md` file with full documentation for a script or project, intended to guide other AI Agents in understanding and using the code. Also updates the `README.md` file to include link to the `DOC.md`.
5.  **`REVIEW_README`**: Analyzes script files or folders to add/review docstrings and type hints, identify and install dependencies using the appropriate dependency management tool, remove unused code, and create/update the `README.md` file with basic project information. **Does not modify existing code other than docstrings, type hints, dependencies, and cleanup.**
6.  **`REVIEW_TEST`**: Analyzes a module/script to add/review docstrings and type hints, identify dependencies using the appropriate dependency management tool, remove unused code, and write unit tests using the appropriate framework, aiming for high code coverage (>= 90%).
7.  **`ADD_LOGS`**: Adds useful logging information to a referenced script, using an existing logging object and appropriate levels (DEBUG, INFO, WARNING, ERROR, CRITICAL), replacing `print()` with logging calls. **Does not modify existing code other than adding logs.**

## Utility Prompts

Prompts that are not part of the main sequential development flow but serve utility purposes:

1.  **`APPLY_CHECKPOINT`**: Includes `CKP_*.md` in `.gitignore`, verifies repository changes, summarizes them in a commit message, and offers immediate commit or file creation.
2.  **`COMMIT_CHANGES`**: Uses git command line to check file status, group changes, add to staging, review diffs, and commit changes with meaningful messages.

## Vibe Development Flow

:::mermaid
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
    L -- Update TODO --> N[UPDATE_TODO];
    L -- Update Documentation --> O[UPDATE_DOC];
    L -- Review README --> P[REVIEW_README];
    L -- Review Tests --> Q[REVIEW_TEST];
    L -- Add Logs --> R[ADD_LOGS];

    M --> K;
    N --> K;
    O --> K;
    P --> K;
    Q --> K;
    R --> K;

    K -- No --> U[End];

    subgraph Utility Prompts
        S[APPLY_CHECKPOINT]
        T[COMMIT_CHANGES]
    end
    S --> T
:::
