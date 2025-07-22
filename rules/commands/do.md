# /do - Execute Implementation Tasks

Usage: /do <tasks_document_path> [task_number]
- tasks_document_path: Path to the tasks.md file
- task_number (optional): Specific task number to execute

You are tasked with executing implementation tasks from the tasks.md document. This command executes the approved implementation plan created by /task command.

## Execution Process

### 1. Read Task List
- Load tasks.md from the specified path
- If task_number is specified:
  - Execute the specified task if it's uncompleted
  - If already completed, inform user and stop
- If task_number is not specified:
  - Identify the lowest-numbered uncompleted task (marked with `[ ]`)
- Execute only this single task

### 2. Execute The Task
- First, read the design.md file from the same directory to understand the technical context and design decisions
- Follow the implementation approach specified in the task description

### 3. Test Execution Guidelines
When running tests as part of task execution:
- **AVOID watch mode**: Always use one-time test execution commands
- Use flags like `--no-watch`, `--watchAll=false`, or `--run` to prevent watch mode
- Common patterns:
  - Jest: `npm test -- --watchAll=false` or `npm test -- --no-watch`
  - Vitest: `npm test -- --run`
  - Other tools: Check for similar non-watch flags
- If the test command doesn't support non-watch mode, run tests manually and inform the user
- Set reasonable timeouts (e.g., 30-60 seconds) for test execution

### 3.1 Manual Testing Requirements
When manual testing is required (e.g., starting dev server, browser testing, GUI interaction):
- Request the user to perform the manual test
- Provide:
  - The exact command to run (e.g., `npm run dev`)
  - What specific functionality to test
  - Expected behavior or outcome
- Wait for user's confirmation before proceeding

### 4. Task Completion Criteria
Mark task as completed `[x]` only after:
- All implementation requirements specified in the task are met
- All automated tests pass (if applicable)
- Manual testing is confirmed by the user (if required)
- No new errors or warnings are introduced

### 5. Progress Tracking
- Update tasks.md checkbox when task completes
- If unable to complete the task, stop execution and ask user for guidance on how to proceed