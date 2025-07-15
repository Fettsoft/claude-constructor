# Read Issue Command

## Purpose

Read Linear issue for the issue key listed in $ARGUMENTS and note all information in $ARGUMENTS.
This command is called by an orchestrating command, and is one of the steps in a larger workflow.
You MUST follow all workflow steps below, not skipping any step and doing all steps in order.

## Workflow Steps

1. Read $ARGUMENTS and extract the Linear issue key

2. Read Linear issue

**Use Linear MCP to fetch issue details using Linear issue key**:
- Get issue key, ID, title, and description

**Linear lookup example**: `linear:get_issue` with query containing Linear issue key listed in $ARGUMENTS after `Linear Issue Key:`

3. Note findings in $ARGUMENTS

Create a new section called `## Linear Issue Information`, with information on this format:
- **Key**: Issue key
- **ID**: Issue ID
- **Title**: Issue title
- **Description**: Issue description

4. Report DONE to the orchestrating command
