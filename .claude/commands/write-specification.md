# Write Specification Command

## Purpose

Write the specification for the increment to be implemented for the issue described in $ARGUMENTS.
This command is called by an orchestrating command, and is one of the steps in a larger workflow.
You MUST follow all workflow steps below, not skipping any step and doing all steps in order.

## Workflow Steps

1. Read $ARGUMENTS. Ultrathink to understand the issue and the minimal increment

2. Ultrathink about parallelization strategy:
   - Identify independent components (e.g., backend endpoints, frontend components, database migrations)
   - Determine dependencies between components
   - Group related changes that must be done sequentially

3. Write detailed specification with parallelization plan:
   - Include dependency graph showing which pieces can run in parallel
   - Assign agent IDs (e.g., agent-1, agent-2) to parallelizable work
   - Mark sequential dependencies clearly
   - Include estimated time/complexity for load balancing
   
  Example structure:
  Parallelization Plan

  agent-1: Backend API endpoint (no dependencies)
  agent-2: Database migration (no dependencies)
  agent-3: Frontend component (depends on agent-1)
  agent-4: Integration tests (depends on agent-1, agent-2)

4. Create specification file: `specifications/{issue_key}_specification_{timestamp}.md`. Note that end-to-end tests should be left out, since they will be covered in a later step of the workflow.

5. Add a reference to the specification file in $ARGUMENTS, in a new section called `## Specification file`

6. Report DONE to the orchestrating command
