# Code Review Command

## Purpose

Review code changes for the active increment and give a verdict of NEEDS_CHANGES or APPROVED.
This command is called by an orchestrating command, and is one of the steps in a larger workflow.
You MUST follow all workflow steps below, not skipping any step and doing all steps in order.

## Workflow Steps

When this command is run with a state management file as $ARGUMENTS.

1. Read state management file to understand the context for what you need to review

2. Update Linear issue status to "Code Review" using `linear:update_issue`

3. Read the specification linked in the state management file

4. Analyze current codebase against the specification requirements

5. Verify completion criteria:
   - [ ] Single behavior is fully implemented
   - [ ] All quality gates pass (see below)
   - [ ] No breaking changes introduced
   - [ ] Feature works in both development and build modes
   - [ ] Business rules are enforced consistently

6. Ultrathink about your findings and provide detailed feedback:
   - What's implemented correctly
   - What's missing or incomplete
   - Any issues found
   - Specific next steps if changes needed

7. Final verdict: APPROVED or NEEDS_CHANGES with clear reasons

8. Once APPROVED, add a comment to the Linear issue describing the findings and verdict, using `linear:create_comment`

9. Report DONE to the orchestrating command.

## Review Process

### Specification Alignment
- Compare implemented behavior vs. specified behavior
- Verify no scope creep beyond the minimal increment
- Check adherence to domain principles

### Code Quality
- Review test coverage and quality
- Check domain model consistency
- Verify error handling
- Assess code organization

### Integration
- Verify frontend/backend integration if applicable
- Check build pipeline success
- Validate development/production compatibility

### Quality Gates

Run all quality gates and verify that they pass.

## Output Format

Provide structured feedback:
- **Summary**: Brief status
- **Completed**: What works correctly
- **Issues Found**: Specific problems
- **Missing**: What still needs implementation
- **Next Steps**: Actionable items
- **Decision**: APPROVED or NEEDS_CHANGES

**Update Linear issue based on decision**:
- If APPROVED: Update status to "Ready For Human Review"
- If NEEDS_CHANGES: Update status to "In Progress" and add comment with required changes
