# AGENTS.md

## Repo purpose

Single-assignment repo: `activity-3.md` (in Spanish) tasks you with building an **OpenCode agent — commands + skills — that generates evaluation-rubric drafts** from a description of an assessable activity.

There is no application code, build system, or test suite. Do not invent one.

## Task requirements (from `activity-3.md`)

The agent must, in order:

1. Analyze the activity described in a user-provided text document.
2. Ask the user for the **number of criteria** and **number of levels** (use the `question` tool).
3. Propose the evaluation criteria.
4. Propose level descriptions with numeric values.
5. Output a rubric as a **Markdown table**.

Deliverables (all three are required):

- Architecture design document (which commands/skills exist and each one's responsibility).
- Implementation of the commands and skills (typically under `.opencode/commands/` and `.opencode/skills/`).
- An example execution, including the generated Markdown rubric.

## Conventions

- Write user-facing docs, skill instructions, and example output in **Spanish**, matching `activity-3.md`.
- Configuration belongs in `opencode.json` if needed; see the `customize-opencode` skill when editing OpenCode's own config, commands, or skills.
- Prefer splitting the workflow across separate commands/skills per the design doc rather than one monolithic prompt — the design document must document that separation.
