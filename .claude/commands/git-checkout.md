# Git Checkout Command

## Purpose

Check out a new git branch to be ready for implementation start, for the issue described in $ARGUMENTS.
This command is called by an orchestrating command, and is one of the steps in a larger workflow.
You MUST follow all workflow steps below, not skipping any step and doing all steps in order.

## Workflow Steps

1. Ensure that you are on the main branch, using `git checkout main`

2. Ensure that you have the latest changes, using `git pull`

3. Check out a new branch, using `git checkout -b feat/{issue key}`

4. Report DONE to the orchestrating command
