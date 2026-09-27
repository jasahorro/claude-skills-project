<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Claude Code Skills Basics

**Project Link:** [View Project](https://nextwork.ai/projects/5bae2568-dd25-5e78-80f4-66a02afac9ca)

**Author:** Maria Jasmin Ahorro  
**Email:** jasminahorro23@gmail.com

---

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/5bae2568-dd25-5e78-80f4-66a02afac9ca_n2t8w6j4)

## Introducing Today's Project!

In this project, I'm going to build Git-powered Claude Code skills that automatically create conventional commits, generate real changelogs from commit history, and chain them into an automated dev pipeline.

This will help me streamline development workflows, maintain consistent commit formatting, and automate project documentation effortlessly using Claude Code.

### Key tools and concepts

The key tools I used in this project include Claude Code, Git, Python, YAML, terminal interfaces like PowerShell and macOS Terminal, Notepad, and the Anthropic Console for managing OAuth authentication and monitoring token usage with /cost.

Key concepts and terms I learned include building custom Claude Code skills using .claude/skills/<skill-name>/SKILL.md files structured with explicit Purpose, Inputs, Outputs, and Steps. I learned how to configure YAML frontmatter using triple-dash --- boundaries at the top of skill files, utilizing the description field for natural language auto-triggering and the name field for slash command invocation like /changelog. I gained experience managing security and least-privilege boundaries with the allowed-tools field (Read, Write, Bash), as well as setting optional frontmatter parameters like model overrides and argument-hint. Additionally, I learned to build orchestrator skills like dev-pipeline to chain multiple skills into a single sequential wo

### How long this project took

This project took me approximately 50 minutes to complete. The most challenging part was understanding how YAML frontmatter triggers skills automatically via natural language and setting up the orchestrator skill to properly chain smart-commit and changelog in sequence.

### Project reflection

Here is a response tailored to complete your prompt based on the project you completed:

I did this project today to learn how to build custom, Git-powered Claude Code skills that auto-commit with conventional messages, generate changelogs from repository history, and chain into automated development pipelines. Another skill I want to learn is how to build automated testing or code-review skills in Claude Code to validate code quality before commits are made.

## Setting Up Claude Code and Git

In this step, I'm going to verify my Claude Code installation, set up a local project folder with a Git repository, and create initial starter code with my first commit.

This will help me establish a local Git history so that my Claude Code skills have real commit data to analyze and generate changelogs from.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/5bae2568-dd25-5e78-80f4-66a02afac9ca_c5r2w8j3)

## Building a Changelog Generator Skill

In this step, I'm going to create a .claude/skills/changelog folder with a SKILL.md file, write instructions to read Git commit history and generate a CHANGELOG.md, and test the skill manually using the /changelog slash command.

This will help me build my first custom Claude Code skill and verify that it can read real Git history to automate project documentation.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/5bae2568-dd25-5e78-80f4-66a02afac9ca_g6q3l5c7)

### What Claude did when I invoked the skill

When I ran /changelog, Claude read my git log and checked the working tree status, listed the project's files, and read app.py to describe what it does. On the first try it found no git repository, because I'd started Claude Code in my home folder instead of the project folder. Claude searched my user folder for git repos, and after I picked claude-skills-project it ran the skill there.

The CHANGELOG.md showed the project name, my feat: add greeting app commit from Step 1, a clean working tree with no uncommitted changes, and a one-line description of app.py: a Python script with a greet() function and an add() function.

## Configuring Skill Frontmatter

In this step, I'm going to add a YAML frontmatter block to my SKILL.md file with the name, description, and allowed-tools fields, create a new utils.py file to add a second commit, and test triggering the changelog skill using a natural language prompt.

This will help me configure automatic skill triggering based on prompt descriptions and set secure tool execution permissions for my Claude Code skills.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/5bae2568-dd25-5e78-80f4-66a02afac9ca_k7v9x3m1)

### How allowed-tools works as a security boundary

The allowed-tools field lists the tools Claude may use without asking for permission while the skill is running. My changelog skill lists Read, Write, and Bash. That's exactly what it needs: Bash to run git log and git status, Read to look at the project files, and Write to create CHANGELOG.md.

This matters because it follows the principle of least privilege. The skill gets only the tools its job requires. That keeps it fast, since I'm not stopped by a permission prompt at every step, and safe, because anything outside that list still needs my approval. It also documents what the skill does: anyone reading the file can see what it can touch before they run it.

## Building a Dev Pipeline with Smart Commit

In this step, I'm going to build a smart-commit skill to stage and commit changes with conventional messages, create a dev-pipeline orchestrator skill to chain smart-commit and changelog together, and test the full pipeline end-to-end.

This will help me automate my development workflow by executing multiple skills in sequence with a single command.

![Image](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/5bae2568-dd25-5e78-80f4-66a02afac9ca_n2t8w6j4)

### How the orchestrator coordinates skills

My dev-pipeline is an orchestrator skill: it doesn't do the work itself, it calls two other skills in order. First it runs /smart-commit, which checks git status and git diff, stages everything with git add -A, and writes a conventional commit message from the changes. Then it runs /changelog, which reads the updated git log, so the commit just made is included. The order matters. If the changelog ran first, it would miss the newest commit. Keeping each skill focused on one job means I can reuse them on their own or chain them together.
After the run, git log showed four commits, oldest first:
- c7ac83e feat: add greeting app
- c0e4ec5 docs: add CHANGELOG.md
- 0824e84 docs: update CHANGELOG.md with latest history
- a8e0dc1 feat(app): add multiply function ← the commit the pipeline just made

The regenerated CHANGELOG.md listed all four and updated the description of app.py to include the new multiply function.

## Adding Hook Triggers

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/5bae2568-dd25-5e78-80f4-66a02afac9ca)*
