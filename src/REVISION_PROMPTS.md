# GENERAL GUIDANCE
  **WRITE ALL THE CODING FILES IN ENGLISH
  **ALWAYS WRITE DOCSTRINGS AND FUNCTION COMMENTS IN ENGLISH, TRANSLATING IF NECESSARY
  **WHEN RUNNING COMMANDS, ALWAYS CHECK IF THERE ARE AN VIRTUAL ENVIRONMENT AND IF SO, USE THEM
  **ALWAYS USE UV TOOL TO ADD PACKAGES AND RUN PYTHON CODE

# REFACTOR MODULE
  ** Please refactor the referenced module/script breaking it into submodules/scripts and make sure the main script will still working as priviously stated. Group similar function/classes into submodules or use one module by function/class whatever more efficient.
  *** Also:
  - **Add/Review existing docstrings in functions and classes** to ensure they align with the defined guidelines and accurately describe the corresponding code. Add any missing or incomplete docstrings, skipping the already compliant ones. 
  - **Verify type hints** to ensure they correctly represent the function/method code. Add any missing or incorrect type hints.  
  - **Identify dependencies and required packages** for the script and add them to the project using the `uv` tool (see instructions below).
  - **Remove unused imports.
  - **Avoid unnecessary comments, like telling some removal or something like that.
  - **GUARANTEE THAT THE PREVIOUS BEHAVIOR OF THE ORIGINAL MODULE IS MAINTAINED.

# UPDATE TODO
  **Please create or update the todo list file TODO.md comparing what is defined on the @/SPEC.md (if exists) with what was implemented described in @/README.md and @/DOC.md . For each feature, include the feature name from TOOLS.md and checks for: it was initialized?, it was implemented?, it was tested? How much? Check the @coverage.xml (read only) for this information.
  ** Update the README.md file to include links to the DOC.md and TODO.md files with a brief descriptions of them.

# REVIEW ONLY
  **I need you to analyze each script file on the referenced folder and perform the following tasks one by one:**
  - **Add/Review existing docstrings in functions and classes** to ensure they align with the defined guidelines and accurately describe the corresponding code. Add any missing or incomplete docstrings, skipping the already compliant ones. 
    **ALWAYS WRITE DOCSTRINGS AND FUNCTION COMMENTS IN ENGLISH, TRANSLATING IF NECESSARY.**  
  - **Verify type hints** to ensure they correctly represent the function/method code. Add any missing or incorrect type hints.  
  - **Identify dependencies and required packages** for the script and add them to the project using the `uv` tool (see instructions below).
  - **Remove unused imports.
  - **Avoid unnecessary comments, like telling some removal or something like that.
  - **Create or update the `README.md` file** with basic information about the project's functionalities, making it suitable for publication on GitHub.  
  - **DO NOT MODIFY ANY EXISTING CODE**

# REVIEW AND TEST
  **I need you to analyze the referenced module/script and perform the following tasks:**
  - **Add/Review existing docstrings in functions and classes** to ensure they align with the defined guidelines and accurately describe the corresponding code. Add any missing or incomplete docstrings, skipping the already compliant ones. 
    **ALWAYS WRITE DOCSTRINGS AND FUNCTION COMMENTS IN ENGLISH, TRANSLATING IF NECESSARY.**  
  - **Verify type hints** to ensure they correctly represent the function/method code. Add any missing or incorrect type hints.  
  - **Identify dependencies and required packages** for the script and add them to the project using the `uv` tool (see instructions below). **ALWAYS READ the @pyproject.toml file before determine what should be installed.
  - **Write unit tests** for all functions, classes, and methods in the code, following these directives:  
  - **Remove unused imports.
  - **Follow the naming convention: `test_<module_name>_<function>_<scenario>.py` for test scripts.  
  - **Create a `tests`/<module_name> folders if they does not already exists. 
  - **If the`tests`/<module_name> folder exists, check if there are any existing successfull tests. If so, create only missing tests and do not overwrite the existing ones.
  - **THE CODE COVERAGE AFTER ALL TESTS SHOULD BE >=90%**.
  - **ALWAYS use the `pytest` framework** for unit testing.  
  - **Use **mocking strategies** for external dependencies.  
  - **Design the tests to achieve **the highest possible coverage** of existing scenarios.  
  - **Ensure the virtual environment is activated** before running any tests.
  - **ALWAYS USE THE SYSTEM TEMPORARY FOLDER** when creating objects or files for testing.  
  - **Dont's use classes. Use functions to implement the test cases.
  - **PLEASE CREATE SMALL TEST FILES WITH MAXIMUM 450 LINES. BREAK SCENARIOS INTO SMALLER SCRIPTS IF NECESSARY.
  - **If any packages need to be installed, use the `uv` tool** as follows:  
    - `uv add --group dev [package_name]` → For build dependencies or runtime dependencies.  
    - `uv add [package_name]` → For regular dependencies.  
  - **To execute the tests, use the command:**  
    uv run pytest -vv tests/<test_script>
  - **WHEN FOUND ERRORS ON TESTS, TACKLE ONE BY ONE UNTIL IT PASSES IN ORDER TO STEP FURTHER
    uv run pytest -vv -k <scenario> tests/<test_script>

# ADD LOG INFO
  **I need you to analyze the referenced script and perform the following tasks:**  
  - Add useful logging information to the script.
  - **Always use the available logging object** to add the log information. If the logging object is not available, ask to create one.
  - **Use the following log levels:**  
    - `logging.DEBUG` → For detailed information, typically of interest only when diagnosing problems.  
    - `logging.INFO` → For general information.
    - `logging.WARNING` → For an indication that something unexpected happened, or indicative of some problem in the near future (e.g. ‘disk space low’). The software is still working as expected.  
    - `logging.ERROR` → For a more serious problem, the software is not able to perform some function.  
    - `logging.CRITICAL` → For a very serious error, indicating that the program itself may be unable to continue running.  
  - Replace print statements with logging statements. 
  - **DO NOT MODIFY ANY EXISTING CODE JUST ADD THE LOGGING STATEMENTS**

# APPLY COMMIT
  **I need you to analyze the referenced script/folder and perform the following tasks:**
  - Using the git command line, commit the changes to the repository in the following way: 
      - Discover the file changes with the command: `git status`
      - Group the changes by nature: modifications, new files, deletions.
      - Use the command `git add <file>` to add the changes and new files to the staging area.
      - Commit each group of changes with a meaningful but not so long message (less than 150 characters) IN BRAZILIAN PORTUGUESE AND TECHNICAL BUT SIMPLE LANGUAGE using the command: `git commit -m "<message>"`.
      - Use the command `git diff` to see the changes in each file and compose your message.
