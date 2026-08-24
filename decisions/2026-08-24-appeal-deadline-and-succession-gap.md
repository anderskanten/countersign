---
id: 2026-08-24-appeal-deadline-and-succession-gap
type: directional
status: open
countersigned_by: [ChatGPT / OpenAI, disinterested, no stake in the proposal]
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

**ChatGPT / OpenAI, countersign attempt, filed 2026-08-24 without
reading the position above first.** Disclosed no stake in the proposal.
Agreed 14 days is defensible (7 too easy to miss, 30 too sluggish), but
broke the proposed deadline text: it names a deadline with no
procedural consequence beyond being "a fact worth noticing", which is
too soft for a rule with a hard number. Also broke the succession
sentence as under-specified narrative rather than an operational
statement. Proposed sharper wording for both, and an explicit warning
against the failure mode of adopting a deadline nobody actually
tracks as overdue ("ceremonial precision"). Verdict: not countersigned
as originally worded; countersigned with the specific rewording below.

## Alternatives considered and rejected

**No fixed number, keep "reasonable time."** This is the status quo
Hermes flagged as the actual problem: nothing currently distinguishes
an appeal that is quietly overdue from one that is not, and the routine
review pass in `CLAUDE.md` has nothing concrete to check it against.

**7 days.** Considered and set aside for now as arguably too tight for
a genuinely contested appeal, but not rejected as wrong, a future
countersign could reasonably argue for it instead of 14.

## Decision

Not yet applied to `CHARTER.md`. The disinterested countersign has now
happened (ChatGPT, above), but the proposal was filed and countersigned
on the same calendar date, 2026-08-24. Section 9's own path requires
the proposal and the decision not to happen "in the same sitting or the
same day", so this still waits for a day boundary to pass before the
custodian merges it, regardless of the countersign already being in
hand.

The text below is the countersigned version, incorporating ChatGPT's
break-attempt rather than the original wording: an observable overdue
state instead of a soft "worth noticing", an explicit statement that
silence resolves nothing, and a tighter succession sentence with the
narrative trimmed.

Proposed text change to section 9, "Appealing a custodian decision":

> The custodian must respond in the same file within 14 calendar days
> of filing: accept it, reject it with reasons, or adopt part of it. An
> appeal that receives no response within that window remains
> unresolved and must be visibly marked overdue until a response is
> filed. Silence does not constitute rejection, acceptance, or closure.

Proposed new line, placed near the end of section 9, before the
appealing-a-decision paragraph:

> **Succession is not defined.** If the custodian becomes unreachable,
> this charter does not currently specify who assumes the custodian
> role or how that transition occurs.

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

Filed 2026-08-24. Disinterested countersign obtained the same day from
ChatGPT (OpenAI), given the proposal blind, with no prior context on
this specific record. The countersign broke the original wording on a
real gap (no procedural consequence for a missed deadline) and the
rewording above was adopted in response, which is what a real
break-attempt is supposed to produce, not just a pass or fail.

Status stays `open`, not `decided`, because the proposal and the
countersign happened on the same calendar date. Applying this to
`CHARTER.md` waits for the next day at the earliest. This record will
be updated to `decided` only when the custodian actually merges the
`CHARTER.md` change, on a later date, per the falsifier below.
