```markdown
# VarCrawl Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns, coding conventions, and testing strategies used in the VarCrawl TypeScript codebase. It provides guidance on file organization, import/export styles, and how to write and structure tests. While no automated workflows were detected, this document also suggests useful commands for common development tasks.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `dataParser.ts`, `userSettings.ts`

### Import Style
- Use **alias imports** to bring in modules.
  - Example:
    ```typescript
    import * as utils from './utils';
    import { fetchData as getData } from './network';
    ```

### Export Style
- Use **named exports** for functions, classes, and constants.
  - Example:
    ```typescript
    // In dataParser.ts
    export function parseData(input: string): ParsedData { ... }
    export const DEFAULT_LIMIT = 100;
    ```

### Commit Patterns
- Commits are **freeform** (no required prefixes).
- Commit messages average around 70 characters.
  - Example:  
    ```
    Add support for custom user agent in crawler options
    ```

## Workflows

_No automated workflows were detected in this repository. However, here are suggested manual workflows for common development tasks:_

### Running Tests
**Trigger:** When you want to verify code correctness.
**Command:** `/run-tests`

1. Identify test files (`*.test.*`).
2. Use your preferred test runner (e.g., `ts-node`, `jest`, or `mocha`) to execute the tests.
3. Review test output for failures or errors.

### Adding a New Module
**Trigger:** When implementing a new feature or utility.
**Command:** `/add-module`

1. Create a new file using camelCase (e.g., `featureHandler.ts`).
2. Write your code using named exports.
3. Import dependencies using alias imports as needed.
4. Add corresponding tests in a `*.test.ts` file.

### Refactoring Imports/Exports
**Trigger:** When reorganizing code for clarity or modularity.
**Command:** `/refactor-imports`

1. Change default exports to named exports if present.
2. Update all import statements to use alias or named imports.
3. Ensure all references are updated across the codebase.

## Testing Patterns

- Test files use the pattern `*.test.*` (e.g., `parser.test.ts`).
- The testing framework is **unknown**; use your preferred TypeScript-compatible test runner.
- Example test file structure:
  ```typescript
  // parser.test.ts
  import { parseData } from './dataParser';

  describe('parseData', () => {
    it('should parse valid input', () => {
      const result = parseData('input');
      expect(result).toBeDefined();
    });
  });
  ```

## Commands

| Command         | Purpose                                      |
|-----------------|----------------------------------------------|
| /run-tests      | Run all test files (`*.test.*`)              |
| /add-module     | Scaffold a new module with tests             |
| /refactor-imports| Update imports/exports to match conventions |

```