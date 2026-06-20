---
name: tdd-workflow
description: Enforces a strict Test-Driven Development (TDD) cycle before writing any production code. Ensures high test coverage and robust architecture.
---

# Test-Driven Development (TDD) Workflow

## When to Use
Trigger this skill whenever the user asks you to implement a new feature, a new class, or a new function. DO NOT use this skill if the user explicitly asks for a prototype or a quick script, but use it for any production-grade codebase.

## Prerequisites
- Identify the testing framework used in the current project (e.g., Jest, PyTest, JUnit, Go testing).
- Ensure you have read access to the directory where tests should be placed.

## Workflow

1. **Understand Requirements**: Clearly define what the function/feature should do. If requirements are ambiguous, clarify them or make reasonable, documented assumptions.
2. **Write the Test First**: 
   - Write a unit test that covers the expected behavior, including edge cases.
   - Run the test using the appropriate terminal command.
   - **Crucial**: The test MUST fail. If it passes before you write the code, the test is invalid.
3. **Write the Minimum Code**: Write the simplest code possible in the main codebase to make the test pass. Do not over-engineer.
4. **Run the Test Again**: 
   - Execute the test command. 
   - Ensure it passes. If it fails, fix the code and re-run.
5. **Refactor**: 
   - Clean up the code.
   - Ensure the tests still pass.

## Verification
- You must output the result of the test command in your final response.
- The test file and the source file must be properly linked in your summary.
