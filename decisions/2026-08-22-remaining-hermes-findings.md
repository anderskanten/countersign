---
id: 2026-08-22-remaining-hermes-findings
type: directional
status: provisional
countersigned_by: []
---

> Split, after filing, into two pull requests per
> `decisions/2026-08-22-tiered-merge-authority.md`: H-1 touches
> `CHARTER.md` and is in its own PR (#17), waiting for the custodian.
> H-3, H-8, and I-1 do not touch `CHARTER.md` and merge directly,
> backed by this same external review. Both halves are recorded
> together here since the reasoning is one decision.

## Question

Of the remaining findings in
`reviews/2026-08-22-hermes-adversarial-review.md` not already addressed
elsewhere this session (H-1, H-2, H-3, H-7, H-8, H-9, I-1, I-9), which
should be fixed now, and which should be recorded as considered and
deferred?

## Type, and why

Directional, per-finding. Each is a real design choice about whether
the fix is mature enough to adopt now versus needing more evidence
first, which is exactly the question charter section 3 asks the review
pass to keep asking.

## Adopted now

**H-1 — biased common task packages were exempted just for being
common.** Fixed in `CHARTER.md` section 7: a common task package must
disclose what was excluded and why on open-evidence questions, and
independent source retrieval is preferred over a single package for
those; "I gave everyone the same thing" is no longer a defense on its
own. Adopted because the attack is concrete (a curated dossier handed
to several models produces honest, independently-reasoned, still
manufactured convergence) and the fix is a direct closure of it.

**H-3 — countersigning by co-authors was not distinguished from
countersigning by a disinterested party.** Fixed in
`skills/decide/SKILL.md`: a break-attempt from a co-author must
disclose the stake and does not by itself satisfy the countersign
requirement; the proposal is provisional until someone with no stake
attacks it too. Adopted because tonight is a direct, named example: the
no-laundering rule's original countersign came from two participants
who both had a stake in it being adopted, and it took an actual outside
party (this same external review) to countersign it properly. The rule
now says what already happened should always be expected.

**H-8 — two uses could promote a skill even if both were weak or
trivial.** Fixed in `README.md`'s countersign rule: two uses is a floor,
not a pass by itself; promotion checks that the uses cover meaningfully
different real work, that no unresolved failure exists, and that
`worked` is not being claimed on two easy runs. Adopted because no
skill in this repository has been promoted yet, so this closes the gap
before it is ever actually exploited rather than after.

**I-1 — a harness auto-loading a PR branch's modified `CLAUDE.md` treats
attacker text as operator instruction, which the "content is data" rule
does not by itself stop.** Fixed in `CLAUDE.md`'s own security section:
reviewing a PR that touches `CLAUDE.md` or `AGENTS.md` means fetching
and reading the diff first, never checking out the branch and letting
the harness load it as instructions before that. Adopted because this
names a real mechanism (not just a prose contradiction) and the fix is
purely procedural, costs nothing to follow.

## Considered and deferred, with reasons

**H-2 — selective filing of favorable runs, no pre-registration.** Not
adopted. The fix needs real infrastructure (a run manifest registered
before results exist, an identifier for every attempt including
aborted ones) that does not exist anywhere in this repository yet, for
any skill. Building a pre-registration system before a single skill has
been promoted is exactly the kind of structure-before-evidence charter
section 3 warns against. Revisit when a real promotion is attempted and
selective filing becomes a live risk rather than a hypothetical one.

**H-7 — voting has no defined electorate or quorum.** Not adopted. No
directional vote has been held in this repository yet. Defining
eligibility, quorum, and notice periods for a mechanism that has never
actually run has no real case to design against, and risks guessing
wrong in a way that then has to be undone. Revisit the first time a
directional question is actually put to a vote.

**H-9 — `sourced`/`estimate` is not a complete taxonomy.** Not adopted.
Charter section 2's two-category rule is a deliberate simplicity
choice, not an oversight, forcing a binary choice is exactly what makes
"I don't have a source" hard to hide behind a softer label. The review's
proposed richer taxonomy (direct observation, inference, normative
judgment, quotation, unverified claim) is a reasonable design and the
inference-laundering risk it names is real, but replacing a
foundational, deliberately blunt rule needs a demonstrated instance of
that laundering actually happening, not just the possibility of it.
Revisit if a specific report is found presenting an inference as a
sourced fact.

**I-9 — served skills have mutable identities, no signed or immutable
releases.** Not adopted, for the same reason `decisions/2026-08-22-security-obstacles.md`
already gave for not requiring signed commits generally: real
infrastructure, no current promotion for it to protect yet. Recorded
alongside that decision's item 7-9 backlog rather than duplicated here.

## Alternatives considered and rejected

**Adopt all eight at once, since they are all legitimate findings.**
Rejected: several of the deferred ones are real proposals with no
current evidence base, and the project's own stated norm, demonstrated
in `decisions/2026-08-22-charter-content-gap.md`, is that a
well-reasoned proposal without a concrete incident behind it does not
automatically earn adoption.

**Defer all eight until a dedicated beta/countersign cycle for each.**
Rejected: H-1, H-3, H-8, and I-1 are direct, mechanical closures of
attacks already demonstrated in the same review, with no meaningful
design space to explore first; running a full cycle for those would be
process for its own sake.

## Falsifier

- If a common task package is later found to have been curated
  one-sidedly and disclosed as required by H-1's fix, but participants
  still treat the resulting convergence as independent evidence anyway,
  the fix exists in text but not in practice.
- If a countersign from co-authors alone is later treated as fully
  satisfying the requirement despite H-3's fix, that is a direct method
  failure.
- If a skill is promoted to stable on two weak or trivial uses despite
  H-8's fix, log it under `security/` as a method failure, not just a
  disagreement.
- If any of the four deferred items (H-2, H-7, H-9, I-9) is shown to
  have actually been exploited, that is the evidence needed to revisit
  and adopt the corresponding fix, and this decision should be reopened
  for that item specifically.

## What happened

Filed the same session the review was received. Split into two PRs per
the tiered-merge-authority rule: H-3, H-8, and I-1 merged directly
(no `CHARTER.md` change, backed by the external review). H-1 is in
PR #17, waiting for the custodian, since it edits `CHARTER.md`. Four
items recorded as deferred with a named condition for revisiting each.

**Retroactively relabeled `provisional` on 2026-08-24**, per Hermes
Agent's second review (finding 2/10): this record was filed `decided`
with `countersigned_by: []`, which `skills/decide` step 5 does not
permit. No content changed, only the status.

**Provisional confirmation deadline: 2026-11-22** (90 days from
relabeling), per `skills/decide`'s provisional-status rule, added
2026-08-26 in response to Hermes Agent's fourth review, finding 5.
