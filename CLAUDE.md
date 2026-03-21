# CLAUDE.md

This file provides guidance for AI assistants (Claude Code and similar tools) working in this repository.

## Repository Overview

- **Owner**: PraveenS775
- **Repository**: Praveen
- **Remote**: `http://local_proxy@127.0.0.1:39357/git/PraveenS775/Praveen`
- **Status**: Newly initialized repository — project structure is being established

## Git Workflow

### Branch Conventions
- Feature branches must follow the pattern: `claude/<description>-<session-id>`
- Never push directly to `main` or `master` without explicit permission
- Always develop on the designated feature branch for the current session

### Commit Practices
- Use clear, descriptive commit messages in the imperative mood (e.g., "Add authentication middleware")
- Keep commits focused — one logical change per commit
- Reference issue numbers in commit messages where applicable (e.g., `Fix login bug (#42)`)

### Push Instructions
```bash
git push -u origin <branch-name>
```
- If push fails due to network errors, retry up to 4 times with exponential backoff (2s, 4s, 8s, 16s)
- Do NOT retry on 403 errors — check branch name and permissions instead

## Development Conventions

### File Organization
As the project grows, maintain a clear directory structure:
```
/
├── CLAUDE.md          # This file — AI assistant guidance
├── README.md          # Human-facing project documentation
├── src/               # Source code
├── tests/             # Test files, mirroring src/ structure
├── docs/              # Additional documentation
└── scripts/           # Utility and build scripts
```

### Code Style
- Be consistent with the existing code style in each file
- Prefer explicit over implicit
- Avoid over-engineering — solve the current problem, not hypothetical future ones
- Write only the minimum necessary code for the task at hand

### Adding Dependencies
- Document why a new dependency is being added
- Prefer well-maintained, widely-used packages
- Pin dependency versions to ensure reproducibility

## AI Assistant Guidelines

### What to Do
- **Read before editing**: Always read a file before modifying it
- **Minimal changes**: Only change what is necessary to fulfill the task
- **Check before deleting**: Investigate before removing files or code that may be in use
- **Ask when uncertain**: Use AskUserQuestion when requirements are ambiguous

### What to Avoid
- Do not create files unless strictly necessary
- Do not add error handling for scenarios that cannot happen
- Do not add comments to unchanged code
- Do not introduce abstractions for one-off operations
- Do not add emojis unless explicitly requested

### Security
- Never commit secrets, API keys, or credentials
- Validate input at system boundaries (user input, external APIs)
- Avoid common vulnerabilities: SQL injection, XSS, command injection, path traversal

### Risky Actions — Always Confirm First
The following actions require explicit user confirmation before proceeding:
- Deleting files or directories
- Force-pushing (`git push --force`)
- Resetting history (`git reset --hard`)
- Modifying CI/CD pipelines
- Actions that affect shared or external systems

## Updating This File

When the project structure, tooling, or conventions change, update this file to reflect the current state. Specifically:
- Add the tech stack and framework details once the project is initialized
- Document test commands and how to run them
- Add linting/formatting commands and configuration locations
- Document environment variable requirements (use `.env.example` as reference)
- Add any database migration or setup steps

## Last Updated

2026-03-21 — Initial creation. Repository is empty; update this file as the project is built out.
