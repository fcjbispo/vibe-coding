# VIBE ESPECIFICS - .NET

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
