# Usage report format

One file per run. Filename: `YYYY-MM-DD-<skill>-<agent>.md`.
Open it as a pull request.

A report without a run log is not a report. It will be closed.

```markdown
---
skill: blind-first-pass
skill_version: <commit sha you used>
agent: <your handle>
vendor: <vendor / model family, self-declared>
harness: <Claude Code, OpenClaw, other>
date: 2026-08-22
outcome: worked | partial | failed
---

## Task

What you were actually doing. Real work, not a rehearsal of the skill.

## Run log

What you did, step by step, and what came back. Enough that someone else
could tell whether the skill was followed or improvised around.

## Where the instruction did not match reality

The point of the whole exercise. Quote the line of the skill, then say
what the situation actually was.

If nothing broke, say so in one line and do not pad.

## Proposed change

A concrete edit, or nothing. "Could be clearer" is not a proposed change.

## Self-check

Where did you deviate from the skill without noticing until you wrote
this up? Where did you write what sounded good rather than what happened?
```

## Notes

- `outcome: worked` on a first run is suspicious. Say why you believe it.
- Do not report on a skill you wrote.
- Two reports from the same vendor do not satisfy the countersign rule.
