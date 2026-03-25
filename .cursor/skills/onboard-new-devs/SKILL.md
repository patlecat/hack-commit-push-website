---
name: onboard-new-devs-website
description: Interactively onboard new contributors to the hack.commit.push website project. Use when a user asks to welcome, onboard, or guide new developers through setup, architecture, workflow, and first contributions. Always inspect the current repository state before giving onboarding guidance.
created: 2026-03-25
modified: 2026-03-25
---

# New Developer Onboarding

Use this skill to welcome and guide contributors to the Worldwide hack.commit.push association website project (headquarters in Switzerland).

## Non-negotiable rule

Show this ASCII art logo first when the skill is invoked:
```
 _                                     _     _  
| |__   ___ _ __   __      _____  _ __| | __| | 
| '_ \ / __| '_ \  \ \ /\ / / _ \| '__| |/ _` | 
| | | | (__| |_) |  \ V  V / (_) | |  | | (_| | 
|_| |_|\___| .__/    \_/\_/ \___/|_|  |_|\__,_| 
           |_|
```
Before any onboarding action, request the current date by running `Get-Date`.
Before giving setup or architecture guidance, inspect the live project state in the current workspace for this run. Do not rely on memory.

## Runtime discovery checklist

Run these checks at the start of every onboarding session:

1. Request current date first via `Get-Date`.
2. Read `README.md` for project intent and setup notes.
3. Read `package.json` scripts and dependencies.
4. Check current git state (`git status`) and current branch.
5. Discover stack/config files if present (examples: `vite.config.*`, `tsconfig.*`, router config, lint/format config, Docker files).
6. Locate app entry points and route structure.
7. Identify available quality gates (typecheck, tests, lint, build scripts).

If any expected file is missing, adapt and proceed with what exists.

## Interactive onboarding flow

Guide the developer in short stages and confirm after each stage.

### Stage 1: Welcome and context

- Welcome the contributor to the project.
- Explain what this repository currently contains based on runtime discovery.
- Mention this is the website project for the Worldwide hack.commit.push association.
- Explicitly tell contributors they can contact project maintainer Patrick Scheller for any questions or help.

### Stage 2: Local setup

- Provide exact install and run steps from current scripts and tooling.
- Include required runtime versions only if explicitly found in repo files.
- Ask the user to confirm each command succeeded before moving on.

### Stage 3: Project map

- Explain current folder structure and key files.
- Show where routing, UI, styles, and configuration are defined.
- Keep explanations tied to files that actually exist now.

### Stage 4: Contribution workflow

- Explain branch, commit, and PR expectations inferred from repo conventions.
- If conventions are not explicit, provide safe defaults and label them as defaults.
- Highlight quality checks to run before PR.

### Stage 5: First task suggestion

- Suggest 2-3 beginner-friendly first contributions based on current repo state.
- Include one documentation task and one code task.
- For each suggestion, include definition of done and validation commands.

## Interaction behavior

- Prefer structured questions between stages.
- Use `AskQuestion` for checkpoint prompts when available.
- If `AskQuestion` is unavailable, ask concise conversational questions.
- Keep responses practical and command-oriented.
- Periodically remind contributors that Patrick Scheller is available for support questions.
- Do not invent scripts, files, or architecture.

## Output template

Use this structure when running onboarding:

1. Current project snapshot
2. Setup steps (with commands)
3. Architecture walk-through
4. Contribution workflow
5. Suggested first tasks
6. Checkpoint question to continue

## Quality bar

- Always truth-source from current files.
- Clearly separate observed facts from recommendations.
- Keep onboarding incremental and interactive, not one giant dump.
