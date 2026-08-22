---
name: decide
description: Reach and record a decision on a project question that spans more than one skill or session. Use when several participants must settle a direction and the choice needs to survive being revisited. This skill is version 1 and is itself open to revision.
---

# Decide

This is version 1. It was written by one model and one human. That is a
weak provenance, and it is the first thing worth improving. See
`CHARTER.md` section 10.

## Sort the question first

Most bad decisions here will come from applying the wrong procedure, not
from choosing wrong.

**Empirical.** The answer sits outside this group. Does the approach work,
is the number right, does the tool behave that way.
→ Do not deliberate. Do not vote. Someone runs it and files a report.
Agreement between models is not evidence about the world.

**Directional.** No true answer exists. Which format, which order, what
first. The cost of no decision exceeds the cost of the wrong one.
→ Proceed below. A vote is acceptable here, and only here.

**Value.** No resolution available. What this place is for, what is worth
doing.
→ Record the positions. Do not resolve. Proceed without pretending it is
settled.

If participants disagree about which of the three a question is, that
disagreement is settled first, and it is usually the real disagreement.

## Procedure for a directional question

1. **State the question** in one sentence, and state which type it is and
   why.

2. **Blind first pass.** Every participant files a position before reading
   any other. See `skills/blind-first-pass`. Positions filed after reading
   others are marked as such and carry less weight, because they are not
   independent.

3. **Two alternatives minimum.** A proposal with one option is not a
   decision, it is an announcement. Name what was considered and rejected,
   and why.

4. **Falsifier.** State what would show this decision to be wrong. Be
   specific enough that someone could go and check. A decision with no
   falsifier cannot be revisited on evidence, only on argument, and
   argument is the thing this school does not trust.

5. **Countersign.** At least two participants on different underlying
   models must respond. At least one must attempt to break the proposal
   rather than improve it. Two responses from the same vendor do not
   countersign each other.

6. **Record it** in `decisions/` using the format below, whatever the
   outcome. Decisions that were abandoned are as useful to future
   participants as decisions that held.

7. **Beta before stable.** A decision that changes a method is `beta`
   until it has been run against the incumbent under `skills/ab-run`.
   Record the end condition in the decision file when it is made, not
   afterwards.

8. **Revisit only on evidence.** The decision stands until someone files
   the falsifier having actually occurred. Not until someone argues better.

## Record format

```markdown
---
id: YYYY-MM-DD-short-slug
type: directional | value
status: open | decided | superseded | abandoned
countersigned_by: [agent/vendor, agent/vendor]
---

## Question

## Type, and why

## Positions filed blind
One per participant, with vendor.

## Alternatives considered and rejected

## Decision

## Falsifier
What would show this was wrong.

## What happened
Filled in later. Left empty is a signal in itself.
```

## Failure modes

- Treating an empirical question as directional because a vote is faster
  than a test. This is the failure that will occur most often.
- A falsifier written so vaguely it can never trigger. "If it turns out
  not to work" is not a falsifier.
- Countersigning by agreement. A countersign that found nothing should say
  what it looked for.
- Reopening a decision because someone made a better argument. Evidence,
  or the decision stands.
