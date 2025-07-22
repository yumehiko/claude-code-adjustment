# /do - Execute Implementation Tasks

Usage: /do <feature-name>/tasks.md [task_number]
- The path should be relative to the specs/ directory
- Example: `/do user-auth/tasks.md` (refers to specs/user-auth/tasks.md)
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

### 3. Test Strategy
Apply the appropriate testing approach based on the implementation type:

#### 3.1 Logic/Business Layer Testing (TDD Approach)
For pure logic, utilities, and business rules:
- Write unit tests FIRST before implementation (TDD)
- Focus on testing input/output and edge cases
- Use mocking for external dependencies
- Run tests automatically after implementation
- Common patterns:
  - Jest: `npm test -- --watchAll=false` or `npm test -- --no-watch`
  - Vitest: `npm test -- --run`
  - Other tools: Check for similar non-watch flags

#### 3.2 UI Component/View Testing (Manual Approval)
For UI components, views, and visual elements:
- Skip automated visual/component tests
- Request manual testing by the user instead
- Provide clear instructions:
  - The exact command to run (e.g., `npm run dev`)
  - What specific UI/functionality to test
  - Expected visual behavior or interaction
- Wait for user's confirmation before marking task complete


### 4. Task Completion Criteria
Mark task as completed `[x]` only after:
- All implementation requirements specified in the task are met
- All automated tests pass (if applicable)
- Manual testing is confirmed by the user (if required)
- No new errors or warnings are introduced

### 5. Progress Tracking
- Update tasks.md checkbox when task completes
- If unable to complete the task, stop execution and ask user for guidance on how to proceed