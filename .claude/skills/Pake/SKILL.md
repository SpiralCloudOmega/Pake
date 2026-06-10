```markdown
# Pake Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and conventions used in the Pake TypeScript codebase. You'll learn how to structure files, write imports/exports, follow commit message guidelines, and implement and test features in a way that matches the project's established style.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `myFeature.ts`, `userService.ts`

### Import Style
- Use **alias imports** for modules.
  - Example:
    ```typescript
    import utils from './utilsAlias';
    ```

### Export Style
- Use a **mixed export style** (both default and named exports).
  - Example:
    ```typescript
    // Named export
    export function doSomething() {}

    // Default export
    export default class MainClass {}
    ```

### Commit Messages
- Follow **Conventional Commits**.
- Use prefixes like `chore:` and `fix:`.
- Keep messages concise (average ~34 characters).
  - Example:
    ```
    fix: correct typo in userService
    chore: update dependencies
    ```

## Workflows

### Adding a New Feature
**Trigger:** When implementing a new capability or module  
**Command:** `/add-feature`

1. Create a new file using camelCase naming (e.g., `newFeature.ts`).
2. Write your code, using alias imports for dependencies.
3. Export your main function or class (use default or named as appropriate).
4. Add or update corresponding test files (`newFeature.test.ts`).
5. Commit with a message like `chore: add newFeature module`.

### Fixing a Bug
**Trigger:** When resolving a defect or issue  
**Command:** `/fix-bug`

1. Locate the relevant file(s) using camelCase naming.
2. Apply the fix, maintaining code style.
3. Update or add tests in `*.test.ts` files to cover the fix.
4. Commit with a message like `fix: handle edge case in parser`.

### Running Tests
**Trigger:** Before pushing or merging changes  
**Command:** `/run-tests`

1. Identify test files matching `*.test.*`.
2. Run tests using the project's test runner (framework unknown; check package scripts).
3. Review results and fix any failing tests.

## Testing Patterns

- Test files are named with the pattern `*.test.*` (e.g., `userService.test.ts`).
- The specific test framework is not detected; check the repository for further details.
- Place tests alongside or near the modules they cover.
- Example test file:
  ```typescript
  import { doSomething } from './doSomething';

  test('should perform action', () => {
    expect(doSomething()).toBe(true);
  });
  ```

## Commands
| Command        | Purpose                                 |
|----------------|-----------------------------------------|
| /add-feature   | Scaffold and implement a new feature    |
| /fix-bug       | Apply and commit a bug fix              |
| /run-tests     | Run all test files before pushing       |
```