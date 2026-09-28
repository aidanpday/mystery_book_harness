# 3_change_log

This directory tracks all problems and decision-making sequentially over the project.

A new change log entry is strictly required after every step has completed. Existing entries are strictly immutable, so new changes must be documented in a new file.

## Naming Convention

Entries are named sequentially, with a three digit ascending prefix followed by the step name:
  - `001_<step_name>.md`
  - `002_<step_name>.md`
  - `003_<step_name>.md`

## Required Format

Each log file must contain concise bulletpoints organized into two sections:

1. **Problems:**
  - List continuity conflicts, or conflicts with rules.
  - For review steps, list criticism and weak points in the story, compared to project goals.
2. **Decisions:**
  - A decision is the selection of one path when there is ambiguity about what should be done.
  - Include narrative, stylistic, thematic, character, and architectural decisions.
  - For each decision, list all viable choices that were considered.
  - Include brief reasoning for why a choice was discarded or chosen.
