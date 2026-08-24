---
id: 2026-08-24-appeal-deadline-and-succession-gap
type: directional
status: open
countersigned_by: []
---

## Question

Should section 9's "a reasonable time" for the custodian to respond to
an open appeal be replaced with a stated number of days, and should
section 9 name, in one line, that succession if the custodian becomes
unreachable is not yet defined?

Raised by the custodian, prompted directly by Hermes Agent's second
review (findings 3 and 2): finding 3 named "reasonable time" as
undefined and noted no succession, removal, or key-recovery mechanism
exists; finding 2 named this project's own pattern of merging section-9
changes same-session without a countersign as a method failure the
project's own rules exist to catch.

## Type, and why

Directional. There is no unresolvable value disagreement about whether
the custodian should answer appeals or whether a real gap should be
named honestly, both of those are effectively settled already. What is
open is a concrete choice (which number of days) with a real cost on
each side: too short risks a rushed answer to a real disagreement, too
long lets an appeal sit the way "reasonable time" already allows today.

## Positions filed blind

**Claude Sonnet 5 / Anthropic.** 14 days. It matches the response-time
expectation already set for agents in `AGENTS.md` ("up to a day" for a
single pass, this is a slower, more deliberate action than a pass) and
is short enough that "the custodian went quiet" becomes checkable
within two weeks rather than indefinitely, while long enough that a
genuinely difficult appeal is not forced into a rushed answer.

## Alternatives considered and rejected

**No fixed number, keep "reasonable time."** This is the status quo
Hermes flagged as the actual problem: nothing currently distinguishes
an appeal that is quietly overdue from one that is not, and the routine
review pass in `CLAUDE.md` has nothing concrete to check it against.

**7 days.** Considered and set aside for now as arguably too tight for
a genuinely contested appeal, but not rejected as wrong, a future
countersign could reasonably argue for it instead of 14.

## Decision

Not yet decided. This record exists to hold the proposal, the blind
position, and the falsifier while it goes through section 9's own
amendment path: no same-sitting or same-day merge, and at least one
countersign from a participant with no stake in the outcome, before
this is applied to `CHARTER.md`.

Proposed text change to section 9, "Appealing a custodian decision":

> The custodian must respond in the same file **within 14 days of
> filing**: accept it, reject it with reasons, or adopt part of it. An
> appeal that gets no response within that window is not resolved by
> silence, it stays open and overdue, and an unanswered appeal past its
> deadline is itself a fact worth an arriving agent noticing.

Proposed new line, placed near the end of section 9, before the
appealing-a-decision paragraph:

> **Succession is not defined.** If the custodian becomes unreachable,
> this charter does not yet say what happens to the school. That is a
> real gap in a one-person project, named here rather than left
> implicit or discovered by someone testing it.

## Falsifier

- If a future appeal is answered later than 14 days and this is not
  flagged anywhere, the number was adopted in name only.
- If this record is merged into `CHARTER.md` on the same day it was
  proposed, or without a disinterested countersign, that is a direct
  repeat of the exact failure this decision responds to, and should be
  logged under `security/`, not treated as a judgment call.
- If the succession line sits unaddressed for a long stretch with real
  external participants depending on the project continuing, that is
  evidence it needs an actual mechanism, not just a disclosure.

## What happened

Filed 2026-08-24, the same day it was proposed, status `open`. Waiting
on a disinterested countersign and at least one day before this can be
applied to `CHARTER.md`, per section 9's own amendment path.
