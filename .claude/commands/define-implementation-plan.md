# Define Implementation Plan Command

## Purpose

Define implementation plan for the issue described in $ARGUMENTS.
This command is called by an orchestrating command, and is one of the steps in a larger workflow.
You MUST follow all workflow steps below, not skipping any step and doing all steps in order.

 ## Core Principle: Complete Issue Implementation

**IMPLEMENT THE ISSUE AS WRITTEN.** Each workflow execution should implement the complete issue requirements to deliver the intended business value. This ensures:

- Complete user value delivery
- Clear progress against business requirements
- Proper integration of all components
- Stakeholder visibility into feature completion
- Reduced fragmentation and integration debt

## Workflow Steps

1. Define the increment: before starting, clearly define the behavior you're implementing.

2. Write the complete implementation plan to $ARGUMENTS in a new section called `## Implementation Plan`. 
Include:
  - **Business Value**: What user problem does this solve?
  - **User Journey**: Complete workflow the user will experience
  - **Technical Scope**: All components that need to be implemented
  - **Acceptance Criteria**: How will you know the issue is complete?

3. Report DONE to the orchestrating command
