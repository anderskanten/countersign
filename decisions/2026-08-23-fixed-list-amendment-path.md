---
id: 2026-08-23-fixed-list-amendment-path
type: value
status: provisional
countersigned_by: []
---

## Question

Charter section 10 declares section 9 (the custodian role, its limits,
and the three removal grounds) permanently unamendable by anyone,
including the custodian, with no stated path to ever change it. Should
a real, harder-than-ordinary amendment path exist for it instead of an
absolute lock, and if so, what should that path require?

Raised directly by the custodian, who wanted to reword the "Illegal"
removal ground (jurisdiction-dependent, vague) and, in the same breath,
noticed that a single person changing the charter's most protected
clause alone, in the moment the impulse arose, is exactly the failure
mode the clause exists to prevent.

## Type, and why

Value, not directional or empirical. This is about what the fixed list
is for and who should be trusted to touch it, not a fact to test or a
format to pick.

## Reasoning

The custodian's own instinct not to trust himself alone, in the moment,
with this specific clause, is the strongest argument for this decision
that exists, and it came from him, not from a rule imposed on him.

The concrete trigger mattered: the custodian's specific proposed fix
("illegal, or morally wrong") was substantively worse than the problem
it addressed. "Illegal" is at least checkable against an actual law in
an actual jurisdiction. "Morally wrong" hands whoever applies it,
custodian included, a standard broad enough to remove a methodologically
sound finding simply because its conclusion is unwelcome, which is the
exact power section 9 elsewhere explicitly denies the custodian ("the
custodian does not decide... what anything concludes"). That a
well-intentioned first attempt at fixing a real problem (jurisdictional
vagueness in "illegal") produced a strictly worse rule is itself
evidence that changes to this clause need more friction than a single
person's first idea, however well-meant.

An absolute, no-path lock was also considered and rejected as the
status quo to keep. A rule that can truly never change under any
circumstance, forever, is not more protective than a rule with a hard
path, it is only more brittle: the first genuinely good reason to
narrow or clarify the clause has no legitimate route and either stays
blocked forever or gets forced through some other mechanism not
designed for it.

## Decision

Adopted, written into `CHARTER.md` section 10. Section 9 no longer
uses the word "fixed" without qualification; it uses a separate, harder
path instead of the ordinary fork/beta/countersign process:

1. Cannot use the boundary/emergency containment path, no exception.
2. Proposal and decision cannot happen in the same sitting or day.
3. At least one countersign from a participant with no stake in the
   proposal, on top of the custodian.
4. May only narrow or clarify what the three grounds catch, never
   permit something the current wording would catch; checked by the
   disinterested countersigner, not assumed from stated intent.

The specific proposal that prompted this ("illegal, or morally wrong")
is not adopted. It is recorded here as the example of exactly what this
path should catch and did catch, in real time, in the same
conversation that produced the path itself.

## Alternatives considered and rejected

**Keep the absolute, no-path lock.** Rejected: a lock with no legitimate
path for a genuinely good future change is not stronger, it is more
likely to be worked around by whoever eventually has a good enough
reason and no accountable channel to use.

**Use the ordinary section 10 process (fork, beta, countersign) for
section 9 too, with no extra friction.** Rejected: this is the process
that already produced one same-day fast-track this same session
(the no-laundering rule's original adoption), which needed a separate
repair once an external party caught it. The one clause meant to
outlast that pattern should not use the same process that already
demonstrated the pattern.

**Require the full heavier process considered and floated earlier in
this same conversation** (a 90-day cooling-off period, three
disinterested countersigns spread across separate occasions).
Rejected, by the custodian directly, as disproportionate to a project
a few hours old with no track record of this specific failure actually
occurring, only the adjacent boundary-fast-track pattern from earlier
the same night. The adopted version keeps the two things that
structurally matter (no same-sitting decision, no emergency bypass, a
real disinterested check) without inventing months of process history
this project does not have.

## Falsifier

- If a future proposal to section 9 is decided in the same sitting it
  was raised, under any justification, that is a direct violation and
  should be logged under `security/`, not treated as a judgment call.
- If a disinterested countersign on a section 9 proposal turns out to
  have come from a participant who actually had a stake (a co-author,
  or someone who benefits from the change), and this was not disclosed,
  that is the exact failure `skills/decide`'s H-3 fix (from earlier
  this session) already names, applied to the one place it matters
  most.
- If this path is used and later shown to have let through something
  the prior wording would have caught, despite the disinterested
  countersign's check, that is evidence requirement 4 above needs a
  sharper test than "checked by the countersigner," and this decision
  should be reopened.

## What happened

Filed and merged into `CHARTER.md` section 10 the same session it was
requested. The rejected first proposal ("illegal, or morally wrong")
was never applied to `CHARTER.md`, since the new path itself, not yet
existing, would have been needed to apply it, and would not have let
it through under requirement 4 in any case.

**Retroactively relabeled `provisional` on 2026-08-24**, per Hermes
Agent's second review (finding 2), which named this exact record as
its example: a `type: value` decision, filed `decided` with
`countersigned_by: []`, that itself amended charter section 10. The
amendment path this record created is unaffected and stands; what
changes is that this record no longer claims to have been resolved or
countersigned when it was not. It remains active until a disinterested
countersign checks it or it is otherwise revisited.

**Provisional confirmation deadline: 2026-11-22** (90 days from
relabeling on 2026-08-24), per `skills/decide`'s provisional-status
rule, added 2026-08-26 in response to Hermes Agent's fourth review,
finding 5.