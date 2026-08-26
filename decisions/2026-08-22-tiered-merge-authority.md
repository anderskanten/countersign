---
id: 2026-08-22-tiered-merge-authority
type: value
status: provisional
countersigned_by: []
---

## Question

Should every governance-adjacent change (skills, README's countersign
rule, CLAUDE.md's own rules, decisions/, appeals/) require the
custodian's explicit merge, or only changes to `CHARTER.md` itself,
with everything else able to proceed once it already has real,
independent adversarial backing?

Raised directly by the custodian: "Jeg vil gjerne ta viktige
avgjørelser, men mye av det vi har snakket om i dag mener jeg skal gå
automatisk. Men selve charteret er noe jeg burde bestemme, eller kunne
rette i sin helhet."

## Type, and why

Value, not directional or empirical. This is a question about what the
custodian's role is for, not a fact to test or a format to pick. The
charter already states a value position here (section 9: the custodian
decides method and the boundary), and this decision is the custodian
narrowing where they personally want to exercise that, not a discovery
about what works better.

## Reasoning

The custodian's stated goal all session has been minimal personal
authorship of content, while still wanting the final say on `CHARTER.md`
specifically, distinct from everything else the charter's method
produces. That is a coherent, narrower line than the blanket
"governance-related" test CLAUDE.md previously used, which folded
skills, README's countersign rule, and CLAUDE.md's own operational
rules into the same category as the charter, even though only the
charter is what section 9 actually reserves to the custodian.

The line drawn: `CHARTER.md` always needs the custodian, with no
exception for process quality. Everything else may merge without
waiting, but only when it already has real independent adversarial
backing (a completed blind-pass-and-countersign, or an external
disinterested review like the one in `reviews/`), not merely because
one agent asserts it is correct.

This is deliberately not a blanket loosening. A single agent's
unvalidated proposal to a skill still needs the custodian under this
rule, the same as before. What changes is that once the actual
"figuring it out together" the custodian wants has already happened,
independently and adversarially, a second human gate on top of it is
not adding safety, it is just adding latency.

## Alternatives considered and rejected

**Keep the existing blanket rule** (custodian for anything touching
charter, decide, ab-run, or the countersign rule). Rejected: this is
what the custodian directly asked to change, having watched a full
session of it in practice and concluded the friction was not landing
where the actual risk was.

**Loosen everything, including `CHARTER.md` itself, when backed by a
real process.** Rejected outright by the custodian: the charter's text
is the one thing they want personal, complete authority over,
independent of how good the process behind a proposed change is. This
is not up for the same cost-benefit reasoning as the rest, it is a
stated line, not a discovered one.

**Loosen the rule but leave the threshold ("real independent
adversarial backing") undefined**, trusting judgment case by case.
Rejected: an undefined threshold is exactly how charter section 9's
boundary authority got exploited earlier this same session before
`decisions/2026-08-22-boundary-fast-track-limits.md` closed it. The
same mistake was not worth repeating one document later.

## Decision

Adopted, written into `CLAUDE.md`'s non-negotiable #2. `CHARTER.md`
changes always require the custodian. Other governance-adjacent changes
may merge without the custodian when they implement something already
backed by a completed blind-pass-and-countersign or an external
disinterested review; a PR mixing a charter change with other files is
split so the charter portion still waits.

Applied immediately to two pending PRs from the same session:
`fix/decide-ab-run-gaps` (touches only `skills/decide` and
`skills/ab-run`, no `CHARTER.md`, backed by the Hermes review) qualifies
for merge without further custodian action. `fix/remaining-hermes-findings`
mixed a `CHARTER.md` change (H-1) with non-charter changes (H-3, H-8,
I-1); it is split so the charter portion still waits for the custodian
and the rest does not.

## Falsifier

- If a PR is merged under this rule's non-charter path without actually
  having a completed countersign or external review behind it, that is
  a direct violation and should be logged under `security/`.
- If a `CHARTER.md` change is ever merged without the custodian under
  any justification, including a boundary/emergency claim, that
  violates this decision's one absolute line and should trigger an
  immediate revert regardless of how the change is later judged on the
  merits.
- If splitting mixed PRs turns out to be impractical often enough that
  it becomes a recurring source of errors or dropped changes, that is
  evidence the split requirement itself needs revisiting, not that
  charter changes should stop needing the custodian.

## What happened

Decided and written into `CLAUDE.md` the same session it was requested.
Applied immediately to the two PRs in flight at the time.

**Retroactively relabeled `provisional` on 2026-08-24**, per Hermes
Agent's second review (finding 2/10): this is a `type: value` record
(what authority an agent should hold) that was filed `decided`, which
`skills/decide`'s own rule for value questions ("record the positions,
do not resolve") does not permit, and it also has `countersigned_by:
[]`. The rule has been operating in practice since it was written, so
this note does not undo it; it corrects the record to say plainly that
this is an adopted operational default, not a resolved value question,
and that no disinterested countersign has checked it.

**Provisional confirmation deadline: 2026-11-22** (90 days from
relabeling on 2026-08-24), per `skills/decide`'s provisional-status
rule, added 2026-08-26 in response to Hermes Agent's fourth review,
finding 5.
