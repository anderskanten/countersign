---
name: decide
description: Reach and record a decision on a project question that spans more than one skill or session. Use when several participants must settle a direction and the choice needs to survive being revisited. This skill is version 1 and is itself open to revision.
state: proposed
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
settled. A value record's `status` can never be `decided`. If an
operational default was adopted anyway so work could continue, that is
`provisional`, and the record must say plainly that the value question
itself remains open, not that it was settled.

If participants disagree about which of the three a question is, that
disagreement is settled first, and it is usually the real disagreement.
Settle it like this, not by discussion alone:

- Default to **empirical** if any observable test, run, or check could
  discriminate the answer at all, even an expensive or slow one.
  Directional and value are for when no such test exists, not for when
  a test exists but voting is faster.
- File the classification itself as its own short record: which type,
  and the specific reason. A participant who did not propose the
  question classifies it. The proposer classifying their own question
  is the exact case this check exists for.
- An unresolved classification dispute blocks voting on the underlying
  question. Reclassifying an inconvenient empirical claim as
  directional to get a faster vote is a method failure, not a
  procedural shortcut.

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

   A break-attempt from someone who helped write the proposal must
   disclose that stake, and does not by itself satisfy this step. A
   proposal countersigned only by its own co-authors, however genuine
   the attempt, is provisional until a participant with no stake in the
   outcome, one who did not draft it and does not benefit from it
   holding, has attacked it too. Record co-author attempts as what they
   are, useful, disclosed, and not yet the real thing.

   **`status: decided` requires this step to have actually happened.** A
   record with `countersigned_by: []` cannot be filed as `decided`,
   whatever its type. File it as `provisional` instead, and say in
   "What happened" that it is operating ahead of its own countersign,
   not that it was decided. This applies retroactively: a record found
   to have been marked `decided` without a countersign is a defect in
   that record, correct it on discovery rather than treating the label
   as settled fact.

   **`provisional` is not a permanent status.** It has 90 calendar days
   from the date it was marked `provisional` to receive a real
   countersign satisfying this step. Passing that window unresolved
   does not revert the text automatically, unlike a boundary action:
   nothing checked this record's substance at all yet, so silently
   auto-reverting live, working text on a timer is its own risk. A
   scheduled check instead opens a pull request, at the deadline,
   proposing that the custodian either ratify the record (ordinary
   custodian sign-off, no countersign substitute) or revert the text it
   produced. The custodian decides; the check never merges this one
   itself.

6. **Record it** in `decisions/` using the format below, whatever the
   outcome. Decisions that were abandoned are as useful to future
   participants as decisions that held.

7. **Beta before stable.** A decision that changes a method is `beta`
   until it has been run against the incumbent under `skills/ab-run`.
   Record the end condition in the decision file when it is made, not
   afterwards.

8. **Revisit only on evidence.** The decision stands until someone files
   the falsifier having actually occurred. Not until someone argues
   better. "Evidence" for this purpose is not limited to the exact
   falsifier firing: a demonstrated internal contradiction with another
   rule already in force, a working exploit path the decision enables,
   a load-bearing assumption shown false, or a falsifier shown to be
   unobservable in practice all count as the falsifier having occurred
   in substance. A narrow or impossible-to-observe falsifier is itself
   a defect in the decision, discovering that is evidence, not
   argument.

## Record format

```markdown
---
id: YYYY-MM-DD-short-slug
type: directional | value
status: open | provisional | decided | superseded | abandoned
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
- Reclassifying an inconvenient empirical question as directional so it
  can be settled by a vote instead of a test.
- Writing a falsifier narrow enough, or unobservable enough, that the
  decision can never actually be revisited on evidence. That narrowness
  is itself a finding once noticed, not a permanent shield.
- Filing `status: decided` on a value question, or on any record with
  `countersigned_by: []`. Both are the exact failure this format exists
  to prevent, and both have happened here before. Use `provisional`.
