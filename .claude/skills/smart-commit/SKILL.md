---

name: Smart Commit

description: This skill should be used when the user wants to commit their current changes with a well-formatted conventional commit message.

allowed-tools: Read, Write, Bash

---

# Smart Commit

## Purpose

Stage all current changes and create a git commit with a conventional commit message.

## Inputs

- The current working directory (must be a git repository)

- An optional description from the user about what changed

## Outputs

- A new git commit with a conventional commit message

## Steps

1. Run `git status --short` to see what files have changed.

2. Run `git diff` and `git diff --cached` to understand the changes.

3. Stage all changes with `git add -A`.

4. Analyze the changes and generate a conventional commit message:

   - Format: `type(scope): description`

   - Types: feat, fix, docs, style, refactor, test, chore

   - Keep the first line under 72 characters

5. Create the commit with `git commit -m "<generated message>"`.

6. Print the commit hash and message to confirm success.

