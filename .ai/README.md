# AI Workspace Guide

This directory is the LLM memory layer for this project. It stores session files, decisions, and next steps — not long documentation.

## Boot Sequence

Every time you start a new work session, read in this order:

1. `CLAUDE.md` — project overview and boot rules
2. `.ai/README.md` — this file
3. `.ai/sessions/_tracker.md` — session index
4. Active session files in `.ai/sessions/` (status: `in_progress` or `paused`)
5. **Skip** `.ai/sessions/_archived/` unless the current task clearly needs historical context
6. Read only the project files relevant to the current task

## Working Rules

- Every focused task (feature, bug fix, refactor, research, architectural decision) gets its own session file.
- Update the active session file as work progresses.
- When a task is finished, mark the session as `done` in both the file and `_tracker.md`.
- Move `done` sessions to `_archived/` when they are no longer needed for active work, and update the tracker status to `archived`.
- Important decisions must be written into the session file, not only kept in chat memory.
- When a session file gets too long: summarize it, mark it `done`, archive it, and start a new session.

## What Belongs Here

- Durable decisions (and brief reason when it matters)
- Progress notes
- Next steps
- Relevant file references

## What Does Not Belong Here

- Long documentation — put that in normal project docs
- Duplicate explanations already in another file
- Temporary notes with no lasting value
- Full chat transcripts

## Session File Naming

Format: `YYYY-MM-DD-sN-slug.md`

- `N` = sequence number for that day, starting at 1
- Use `s1` even when there is only one session that day (consistency)
- `slug` = short, hyphen-separated description of the topic

Examples:
```
2026-05-25-s1-new-feature.md
2026-05-25-s2-bug-fix.md
2026-05-25-s3-api-refactor.md
```

## Session File Template

Copy this when starting a new session:

```markdown
# Session: <title>

- Created: YYYY-MM-DD
- Updated: YYYY-MM-DD
- Status: in_progress
- User: <name or unknown>
- Summary: One short sentence describing this session.

## Goal
One or two sentences only.

## Progress
- 

## Decisions
- 

## Next Steps
- 

## Relevant Files
- 
```

## Status Values

| Value       | Meaning                                      |
|-------------|----------------------------------------------|
| in_progress | Actively being worked on                     |
| paused      | On hold, may resume                          |
| done        | Completed, not yet moved to archive          |
| archived    | Moved to `_archived/`, skip during boot      |
