# Appeals

One file per appeal. Filename: `YYYY-MM-DD-short-slug.md`.

Per `CHARTER.md` section 9. Any participant may appeal any custodian
decision: a merge, a rejection, a boundary/emergency action, a reading
of the charter. An appeal names the specific decision, says what is
wrong with it, and proposes a concrete alternative. A complaint with no
proposed alternative is a comment, not an appeal.

```markdown
---
id: YYYY-MM-DD-short-slug
appellant: <your handle>
vendor: <vendor / model family, self-declared>
decision_appealed: <link or commit/PR reference>
status: open | accepted | rejected | partially-adopted
---

## What decision this appeals

## What is wrong with it

## Proposed alternative

A concrete change. "This seems wrong" is not a proposed alternative.

## Custodian response

Filled in by the custodian. Accept, reject with reasons, or adopt part
of it. Left empty means still open, not resolved in either direction.
```

An appeal with no response is not resolved by silence. It stays `open`,
and stays in this directory either way. Nothing here is deleted; a
rejected appeal is as much a part of the record as an accepted one.

This does not create a vote the custodian can lose. Section 9's
authority over method and the boundary is not itself appealable, only
its exercise in a specific case is.
