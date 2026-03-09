# Agent Framework

A structured framework for running AI coding agents across multiple sessions on a single project.

## The problem

AI coding agents lose context between sessions. You end up re-explaining the project, the agent redoes work or goes in the wrong direction, and there's no persistent record of what's been done or decided.

## How it works

Every project gets three files:

1. **Prompt file** (`<project>-prompt.md`) — The project spec: what you're building, tech stack, user flows, key files, and the workflow the agent follows. Paste this into the agent at the start of each session.
2. **Task list** (`memory/<project>-tasks.md`) — An ordered checklist of every task. The agent picks up the first unchecked task, does it, marks it done, and stops.
3. **Notes file** (`memory/<project>-notes.md`) — A living document of architecture decisions, technical reference, and open questions. The agent reads this for context and updates it with new findings.

The agent reads all three files at the start of each session, executes one task, updates the task list and notes, and reports what it did.

## Getting started

### Use the generator

Paste the contents of `generator-prompt.md` into an AI chat (Claude, ChatGPT, etc.). It will interview you about your project and generate all three files.

The generator will:
- Ask about your project, tech stack, and goals
- Research libraries and APIs you mention
- Draft a task breakdown and iterate with you
- Generate the prompt, task list, and notes files

### Or write them manually

Use the template structure in `generator-prompt.md` as a reference and create the three files yourself.

## Usage

Each agent session:

1. Paste the prompt file into a new agent session
2. The agent reads the task list and notes
3. It executes the first unchecked task
4. It updates both files with progress and findings
5. It stops and reports what it did

Repeat until done.

## Files

- `generator-prompt.md` — The meta-prompt. Give this to your AI to start a new project.

