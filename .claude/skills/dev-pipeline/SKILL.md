---

name: Dev Pipeline

description: This skill should be used when the user wants to commit their changes and update the project changelog in one step.

allowed-tools: Read, Write, Bash

---

# Dev Pipeline

## Purpose

Commit current changes with a well-formatted message, then regenerate the project changelog.

## Steps

1. Run the `/smart-commit` skill to stage and commit all current changes.

2. Run the `/changelog` skill to regenerate CHANGELOG.md with the updated commit history.

3. Print a summary showing the new commit and the path to the updated changelog.

