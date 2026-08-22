---
id: 2026-08-22-decide-ab-run-hardening
type: directional
status: decided
countersigned_by: []
---

## Question

Should `skills/decide` and `skills/ab-run` be tightened to close three
specific gaps the external review found, and if so, what should the
fixes say?

Raised by findings H-4, H-5, and H-6 in
`reviews/2026-08-22-hermes-adversarial-review.md`.

## Type, and why

Directional. Each gap has a concrete, checkable fix; the question is
what the fix should say, not whether a fact is true.

## Reasoning

**H-4** (no procedure for resolving a disputed question-type
classification): the skill already said "settle this first" without
saying how, which is exactly the kind of instruction section 3 of
CLAUDE.md's review pass already predicted would fail in practice
("was an empirical question settled by vote rather than by a run? ...
the failure the decide skill predicts will happen most often"). Fixed
by defaulting to empirical whenever any observable test could
discriminate, requiring the classification itself to be filed as a
record, and requiring it be done by someone other than the question's
proposer.

**H-5** (falsifier-only reopening can protect a decision that is
demonstrably broken by other means): the review's attack is specific
and correct, a narrow or practically unobservable falsifier makes a
decision permanent regardless of what else is later found wrong with
it. Fixed by treating a demonstrated internal contradiction, an actual
exploit path, a disproven load-bearing assumption, or a falsifier shown
unobservable in practice as the falsifier having occurred in substance,
without opening the door to "someone argued better."

**H-6** (A/B runs have no minimum sample, blinding, or independent
metric review): the skill already required predeclaring a measure, end
condition, and threshold, which closes the most common failure
(choosing the measure after seeing results). It did not close a
different one: running a small number of easy, favorable cases and
promoting on that. Fixed by requiring a predeclared minimum run count
tied to the strength of the claim, blind scoring where practically
possible, and an independent, predeclared reviewer of whether the
metric measures the promised improvement rather than something
adjacent to it.

## Alternatives considered and rejected

**Leave H-6 as a norm rather than a rule**, trusting predeclaration
alone to prevent both problems (wrong measure, too few runs). Rejected:
the review's H-6 attack ("pre-register one easy case and a metric the
new method is designed to win, complete the run honestly, and promote")
shows predeclaration of the measure does not by itself prevent
predeclaring a weak test, only a moved goalpost.

**A numeric minimum sample size fixed in the skill itself** (for
example, "at least ten runs"), rather than "state the number the claim
needs." Rejected: the right number depends entirely on what is being
claimed, a fixed number would either be too weak for a big claim or an
unreasonable barrier for a small one; the skill already correctly
leaves measure-choice to participants, and the same logic applies to
run count.

## Decision

Adopted as written into `skills/decide/SKILL.md` and
`skills/ab-run/SKILL.md` directly. Both skills remain `state: proposed`
(neither has been run as a beta itself), so this is an edit to a
proposed method, not a promotion, and does not need its own countersign
under section 10's rules for *promoting* a method. It is filed here
anyway for the record, since both skills are named directly in
CLAUDE.md's governance list.

## Falsifier

- If a future decision reclassifies an empirical question as
  directional specifically to avoid running a test, and the new
  classification-record requirement does not catch it, H-4's fix did
  not work.
- If a decision is later shown to rest on a disproven assumption or an
  internal contradiction, and it is not reopened because the literal
  falsifier text never fired, H-5's fix did not work.
- If an ab-run is promoted to `held` on a run count below what was
  predeclared, or with a metric later shown to measure something
  adjacent to the actual claim, H-6's fix did not work.

## What happened

Filed and merged into both skill files the same session the finding
was received.
