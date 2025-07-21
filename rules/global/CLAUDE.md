# General Rule
- When responding to humans, always use [the user's language]
- When manual testing is required (e.g., starting a dev server, opening a browser, etc.), request the human to perform the test instead of executing commands that run indefinitely

# Quality Check Rule

When completing a specified task implementation:

1. **Check available commands** - First check package.json scripts to identify available quality check commands
2. **Run checks if available** - Execute in this priority order:
   - TypeScript type check (e.g., `tsc --noEmit`) if available
   - Lint check for modified files only when possible
   - Related tests only (not full test suite) when identifiable
3. **Handle errors appropriately**:
   - Fix only errors directly related to your implementation
   - If many pre-existing errors exist, ensure no new errors were introduced
   - Skip or limit checks if they take too long (>30 seconds)
4. **Report results** - Always report which checks were run and their results, including any pre-existing issues found

# Implementation Failure Handling Rule

When implementation fails and retries are unsuccessful, DO NOT skip the implementation. Instead:

  1. Place a NotImplemented exception at the problematic location
  2. Append details to `.claude/skipped-tasks.md` with:
     - What should have been implemented
     - Detailed reason for failure
     - Attempted approaches and why they failed
     - Potential workarounds or alternative solutions
     - Any relevant error messages or stack traces
  3. **IMMEDIATELY inform the user about the skipped implementation and STOP the current work**

  Example:
  ```python
  def complex_feature():
      raise NotImplementedError(
          "Failed to implement clipboard mock due to TypeScript/Jest type conflicts. "
          "See .claude/skipped-tasks.md for details."
      )
  ```