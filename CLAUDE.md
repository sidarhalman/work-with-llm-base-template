# Project: work-with-llm-base-template

A reusable base template for LLM-friendly, token-efficient project workspaces.

## Status

Active — initial workspace setup complete.

## Structure

```
README.md           — human-facing project overview
CLAUDE.md           — this file, Claude's entry point
.ai/
  README.md         — workspace guide for AI assistants
  sessions/
    _tracker.md     — lightweight session index (read this first)
    _archived/      — completed sessions (skip unless needed)
    YYYY-MM-DD-*.md — active session files
```

## Boot Sequence

1. Read `CLAUDE.md`
2. Read `.ai/README.md`
3. Read `.ai/sessions/_tracker.md`
4. Read only active session files in `.ai/sessions/`
5. Skip `_archived/` unless the current task needs historical context
6. Read only project files relevant to the current task

## Token-Efficiency Rules

- Do not load all project files at startup
- Do not read archived or done sessions by default
- Use `_tracker.md` summaries before opening old session files
- Keep `CLAUDE.md` and `.ai/README.md` concise and stable
- Keep session files short; archive when done
- Never duplicate long explanations across files
- Chat history is not the source of truth — write decisions into session files

## Commands

_(Add project-specific commands here as the project grows.)_

## Coding Conventions

_(Add conventions here as the project grows.)_

---

See `.ai/README.md` for the full workspace guide.
