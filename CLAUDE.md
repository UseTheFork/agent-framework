# CLAUDE.md — Agent Framework

## What this repo is

A collection of reusable Claude Code skills. Each skill is a self-contained prompt that teaches an agent how to perform a specific workflow. Skills live in `.claude/skills/<name>/SKILL.md`.

## Repo structure

```
.claude/skills/<skill-name>/SKILL.md   # Skill definitions
ROUTER.md                               # Skill discovery and selection guide (generated — do not edit)
GENERATE-ROUTER.md                      # Instructions for regenerating ROUTER.md
README.md                               # Human-facing docs
```

## Working in this repo

### Adding a new skill

1. Create `.claude/skills/<skill-name>/SKILL.md`
2. Include frontmatter: `name`, `description`, `user-invocable`, `allowed-tools`, `argument-hint`
3. Regenerate `ROUTER.md` by following the instructions in `GENERATE-ROUTER.md`
4. Add the skill to the `README.md` skills section
5. Keep skill prompts self-contained — an agent should be able to execute the skill with only the `SKILL.md` content

### Editing a skill

- Keep prompts dense but scannable: bullets, tables, code-formatted paths
- Every instruction should be specific and actionable
- Test by running the skill on a real project before committing

### ROUTER.md

The router is the machine-readable entry point. Agents read it to discover and select skills without slash commands. **Never edit `ROUTER.md` directly.** Instead, follow the instructions in `GENERATE-ROUTER.md` to regenerate it from the skill definitions. Always regenerate the router after adding, removing, or editing a skill.

## Conventions

- Skill names are lowercase kebab-case
- One `SKILL.md` per skill directory
- Prompts are written for Claude but should work when pasted into any LLM
- No dependencies outside the `.claude/` directory
