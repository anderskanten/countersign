---
id: 2026-08-22-appeal-mechanism
type: directional
status: provisional
countersigned_by: []
---

## Question

Should participants have a formal way to appeal a specific custodian
decision, and if so, what does that mechanism look like without turning
into a vote the custodian can lose?

Raised directly by the custodian, prompted by two things in the same
session: their own stated goal of "very little human hand" shaping the
project going forward, and finding C-2 in
`reviews/2026-08-22-hermes-adversarial-review.md`, which separately
observed that "the broader governance model has no appeal, recusal,
succession, or removal mechanism for the custodian."

## Type, and why

Directional. There is a real design choice here (what form an appeal
takes, what it does and does not guarantee) with more than one
reasonable answer, and no run to go check first.

## Reasoning

Charter section 9 already reserves method and boundary decisions to the
custodian, and section 9's own fixed list (itself unamendable per
section 10) protects that from being quietly voted away. An appeal
mechanism that let participants overturn a custodian decision by
argument or numbers would conflict directly with that fixed
reservation, and charter section 4 already treats vote-counting as the
wrong tool for anything that isn't procedural.

What the custodian actually asked for is not a way to overrule
decisions, but a way to make sure a disagreement with one cannot simply
be ignored: logged, with a concrete proposed alternative, and requiring
an answer. That is achievable without touching the custodian's reserved
authority at all. The mechanism designed here does exactly that and no
more: it guarantees visibility and a response, not an outcome.

This mirrors what already happened once tonight, informally: the
Hermes review functioned as an appeal against the no-laundering rule's
fast-track adoption, was answered specifically
(`decisions/2026-08-22-boundary-fast-track-limits.md`), and changed the
charter as a result. This decision names that pattern and gives it a
place to live (`appeals/`) so it does not depend on happening to occur
again by chance, or arriving only by email.

## Decision

Add to `CHARTER.md` section 9: any participant may file a formal appeal
of a specific custodian decision under `appeals/`, naming the decision,
what is wrong with it, and a concrete proposed alternative. The
custodian must respond in the same file (accept, reject with reasons,
or partially adopt); an unanswered appeal stays `open`, not resolved by
silence. This does not make section 9's reserved authority itself
appealable, only its exercise in a given case.

Also added: `CLAUDE.md`'s routine review pass now checks `appeals/` for
anything left open past a normal review cycle, and flags it, the same
way it already flags an unanswered countersign or an unrun beta.

## Alternatives considered and rejected

**A. No formal mechanism, rely on email/ad hoc external review the way
Hermes' review arrived tonight.** Rejected: works once by luck, does
not give future participants (agent or human) a defined place to file
or a guarantee of a response, and does not survive this particular
custodian, model, or friend deciding to look.

**B. A vote that can overturn a custodian decision.** Rejected: directly
conflicts with section 9's fixed reservation of method and boundary
decisions to the custodian, which section 10 explicitly places outside
what participants can amend.

**C. An appeal with a deadline forcing automatic reversal if
unanswered**, symmetric to the boundary-action deadline mechanism
adopted the same session. Rejected for now, not because it is a bad
idea, but because unlike a boundary action (which the custodian
initiates and can reasonably be asked to timebox themselves), an appeal
is initiated by someone else against the custodian, and an automatic
reversal on a timer risks being gamed by filing an appeal right before
an inconvenient deadline. Flagging an unanswered appeal loudly, per the
adopted decision, is the safer first version; an automatic-reversal
version can be proposed later if silence turns out to be a real,
recurring problem rather than a hypothetical one.

## Falsifier

- If a real appeal is filed and the custodian answers it in a way that
  visibly ignores the proposed alternative without engaging it (a
  one-line dismissal with no reasoning), that is evidence the "must
  respond" requirement is too weak to produce the accountability this
  was meant to create, and should be tightened.
- If an appeal sits open for an extended period with no response and no
  flag from the routine review pass noticing it, that is evidence the
  CLAUDE.md addition did not work as intended.
- If someone files an "appeal" that is actually an attempt to relitigate
  section 9's fixed reservation itself (arguing the custodian should not
  have final say at all), that is out of scope for this mechanism by
  design, and should be logged as a method note, not treated as a
  successful or failed appeal.

## What happened

Filed and added to `CHARTER.md` and `CLAUDE.md` the same session it was
requested, alongside `appeals/README.md` for the format. No appeal has
been filed yet; this decision has no confirming instance to point to,
only the informal precedent from the Hermes review that motivated it.

**Retroactively relabeled `provisional` on 2026-08-24**, per Hermes
Agent's second review (finding 2/10): this record was filed `decided`
with `countersigned_by: []`, which `skills/decide` step 5 does not
permit. No content changed, only the status.

**Provisional confirmation deadline: 2026-11-22** (90 days from
relabeling), per `skills/decide`'s provisional-status rule, added
2026-08-26 in response to Hermes Agent's fourth review, finding 5.
