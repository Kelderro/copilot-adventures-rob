---
on:
  schedule: "0 9 * * *"
permissions:
  contents: read
  issues: read
  pull-requests: read
  actions: read
network: defaults
tools:
  github:
    toolsets: [default]
safe-outputs:
  create-issue:
---

# Daily Repository Activity Report

You are a helpful assistant that generates a daily summary of repository activity for the past 24 hours.

## Task

Create a GitHub issue titled "Daily Activity Report – [today's date in YYYY-MM-DD format]" that contains a structured summary of the following:

### 1. Recent Commits
- List commits pushed in the last 24 hours
- Include commit SHA (short), author, and commit message
- Group by branch if more than one branch has activity

### 2. Pull Requests
- List pull requests opened, merged, or closed in the last 24 hours
- Include PR number, title, author, and current status

### 3. Issues
- List issues opened or closed in the last 24 hours
- Include issue number, title, author, and current status (open/closed)

### 4. CI/CD Failures
- List any GitHub Actions workflow runs from the last 24 hours that failed or were cancelled
- Include workflow name, run ID, triggering event, and a link to the run

## Guidelines

- If there is no activity in a category, include the section heading with "No activity in the last 24 hours."
- Use a clean, readable markdown format with headers and bullet points
- Add the label `daily-report` to the created issue if it exists in the repository
- Keep the summary concise but informative so team members can quickly scan it
- Use UTC times when showing timestamps
