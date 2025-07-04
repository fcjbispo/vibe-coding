# Tech Context

This document outlines the technologies used, development setup, technical constraints, dependencies, and tool usage patterns.

## Technologies Used
[List the primary programming languages, frameworks, databases, and other technologies used in the project. Refer to `VIBE_SPECIFICS_<LANGUAGE>.md` files for language-specific details.]

## Development Setup
[Describe the necessary steps and tools for setting up the development environment.]

## Technical Constraints
[Detail any technical limitations or constraints that impact the project.]

## Dependencies
[List external libraries, packages, or services that the project relies on.]

## Tool Usage Patterns
[Explain how specific tools are used within the development workflow.]

## VIBE GUIDE Source Document References
This section lists the original source files for sections within the `VIBE_GUIDE.md`.

- **PART 1: GENERAL CONVENTIONS:** Originated from `CONVENTIONS.md`
- **PART 2: AGENT'S MEMORY BANK:** Originated from `MEMORY_BANK.md`
- **PART 3: VIBE - AI SOFTWARE DEVELOPMENT GUIDE:** Originated from `VIBE.md`

## Language-Specific Guidelines References
This section lists the official URLs for retrieving specific guidelines for different programming languages.

- **DOTNET:** `https://github.com/fcjbispo/vibe-coding/blob/master/VIBE_SPECIFICS_DOTNET.md`
- **JAVA:** `https://github.com/fcjbispo/vibe-coding/blob/master/VIBE_SPECIFICS_JAVA.md`
- **NODEJS/JAVASCRIPT:** `https://github.com/fcjbispo/vibe-coding/blob/master/VIBE_SPECIFICS_NODEJS_JAVASCRIPT.md`
- **PYTHON:** `https://github.com/fcjbispo/vibe-coding/blob/master/VIBE_SPECIFICS_PYTHON.md`

## Memory Bank Initial Setup
This section records the initial setup command for the memory bank.

To initialize the memory bank, execute the following command:

```bash
# This command is a placeholder and should be replaced with the actual command
# to initialize the memory bank, if applicable.
echo "Memory bank initialized."

## MCP Server Integration
This section documents the integration with MCP (Model Context Protocol) servers.

- **Guideline:** Agents should utilize available MCP servers to extend their capabilities.
- **Permission:** If access to a tool is not pre-approved, the agent must request permission from the user before use.
- **Available Servers:**
  - `fbpyutils_ai_tools`: Provides tools for web scraping, searching, and other utilities.
