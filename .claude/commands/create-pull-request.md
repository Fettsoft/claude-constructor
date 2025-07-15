# Create Pull Request Command

## Purpose

Create pull request for the increment implemented to satisfy the issue described in $ARGUMENTS.
Add, commit, push code for the finished increment. Create Pull request in GitHub using the `gh` CLI.
This command is called by an orchestrating command, and is one of the steps in a larger workflow.
You MUST follow all workflow steps below, not skipping any step and doing all steps in order.

## Workflow Steps

1. List unstaged changes using `git status`

2. Read the specification linked in $ARGUMENTS to and compare with unstaged changes to understand how the increment has been implemented and which unstaged changes are relevant to the increment. Ignore the specifications and state_management folders.

3. Create a git commit using the guidelines in `docs/commit.md`

4. Push the commit using `git push`

5. Create a pull request using `gh pr create --title "feat: [issue key] [brief description from commit]" --base main --head $(git branch --show-current)`

6. Add a link to the pull request in the $ARGUMENTS in a new section called `## Pull Request`

7. Report DONE to the orchestrating command
