---

name: Changelog Generator

description: This skill should be used when the user asks to generate a changelog, review commit history, or summarize what has changed in the project.

allowed-tools: Read, Write, Bash

---

# Changelog Generator

## Purpose

Generate a CHANGELOG.md from the project's git commit history.

## Inputs

- The current working directory (must be a git repository)

## Outputs

- A `CHANGELOG.md` file written to the project root

## Steps

1. Run `git log --pretty=format:"%h %s (%cr)" --reverse` to get the full commit history.

2. Run `git status --short` to check for uncommitted changes.

3. Read the project's root directory listing to identify key files.

4. Write a `CHANGELOG.md` to the project root with these sections: project name (from the folder name), commit history (formatted as a readable list), current working tree status, and a list of tracked files with one-line descriptions.

5. Print the path to the generated file to confirm it was written successfully.

