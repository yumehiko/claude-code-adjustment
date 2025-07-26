# /task - Implementation Task List

Document directory: specs/$ARGUMENTS

You are tasked with creating actionable implementation tasks based on the design document at the path specified above. This is the final phase of the documentation process (Requirements → Design → Tasks).

## Your Tasks

### 1. Analyze Design
You must:
- Read requirements.md and design.md
- Identify all components to implement
- Determine task dependencies
- Plan implementation order

### 2. Create Tasks Document (in User's Language)
Generate `tasks.md` in the same directory as design.md, using the user's language, with:

#### Task Format
```markdown
- [ ] [Task Number]. [Task Description]
  - [Subtask 1 description]
  - [Subtask 2 description]
  - [Implementation details]
  - Run lint, tests, and build
  - Request UAT if needed
  - Verify requirements are fulfilled
  - _Requirements: [Requirement numbers addressed]_
```

#### TDD Task Format
```markdown
- [ ] [Task Number]. [Component Name - TDD Implementation]
  - Create test file in same directory as implementation
  - Define test cases covering all scenarios
  - Run tests to confirm RED state
  - Implement [Component] to pass tests
  - Run tests to achieve GREEN state
  - Refactor while maintaining GREEN
  - Run lint and type checks
  - _Requirements: [Requirement numbers]_
```

#### Organization
- Infrastructure and setup tasks first
- Core functionality implementation
- UI components (including demo page setup for visual verification)
- Integration work
- Testing and optimization last

#### UI Component Task Format
```markdown
- [ ] [Task Number]. [UI Component Name - Pure UI Implementation]
  - Create pure UI component without business logic
  - Define necessary custom hooks for UI state management
  - Implement component with all visual states
  - Add to demo page for visual verification
  - Request manual visual check
  - Run lint and type checks
  - _Requirements: [Requirement numbers]_
```

#### Demo Page Setup (First UI Task)
```markdown
- [ ] [Task Number]. Create UI Component Demo Page
  - Create demo page for displaying all UI components
  - Set up component showcase structure
  - Include all component states and variations
  - This page will be used for all visual verification
  - _Requirements: UI/UX requirements_
```

### 3. Task Guidelines
- **Test Location**: Always save tests in the same directory as the implementation (colocated)
- **Directory Specification**: For new class/component creation tasks, include the directory path from design.md
- **Logic Layer Tasks**: Use TDD approach with single task unit from RED to GREEN:
  - One task includes: test creation → RED state → implementation → GREEN state
  - This ensures atomic execution for coding agents
- **UI/Integration Tasks**: One complete unit including manual testing request
- Each task is one atomic unit for coding agent execution
- Start with action verbs (Create, Implement, Build)
- Include specific technical details
- Reference requirement numbers
- Respect dependencies

## Task Management
- Tasks numbered sequentially (1, 2, 3...)
- Subtasks use decimals (1.1, 1.2...)
- Checkbox format for tracking progress
- Each task includes requirement references

### 4. Get User Approval
After creating tasks.md:
1. Show the created tasks.md to the user
2. Ask for their approval or feedback
3. Make any requested modifications
4. Inform user that approved tasks can be executed with `/do` command

## Validation
- Ensure design.md and requirements.md exist
- Verify all design components have tasks
- Maintain requirement traceability
- Check task dependencies are logical