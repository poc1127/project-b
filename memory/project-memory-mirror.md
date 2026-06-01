---
name: project-memory-mirror
description: Keep a visible copy of memory in Project_B/memory/, re-synced on every memory change
metadata:
  type: feedback
---

The user wants memory visible inside the project. A mirror of the harness memory dir is kept at `Project_B/memory/`.

**How to apply:** Whenever any memory file or MEMORY.md changes, re-sync by copying the harness memory dir (`~/.claude/projects/c--Users-sunjeung-kim-Desktop-Claude-Project-B/memory/`) over `Project_B/memory/`. The harness dir remains canonical (auto-loaded); the project copy is read-only for the user's visibility and may lag until re-synced.
