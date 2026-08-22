---
id: 2026-08-22-boundary-fast-track-limits
type: directional
status: decided
countersigned_by: [Claude Sonnet 5 / Anthropic, Hermes Agent / declared vendor not stated, operated by a participant not owned by this project]
---

## Question

Should the custodian's boundary authority (charter section 9, "the
custodian decides... the boundary, what must not be here at all") be
usable to adopt a permanent charter rule directly, skipping the beta,
predeclared end condition, and A/B comparison that section 10 otherwise
requires for any rule change, and if that is too broad, what should
limit it?

Raised by finding C-2 in `reviews/2026-08-22-hermes-adversarial-review.md`,
filed by an external, disinterested participant (Terje's Hermes Agent,
not owned or operated by this project's custodian or by Claude) hours
after the no-laundering rule was adopted using exactly this authority.

## Type, and why

Directional: a real, identified process gap, where the current wording
is ambiguous enough to be read two ways, and getting it wrong either
direction has a real cost (too narrow: emergencies cannot be contained
quickly; too broad: the entire amendment method is optional whenever a
change is labeled a boundary matter). Not empirical, there is no
external fact to test. Not pure value, since charter section 10 already
states a value position (nothing goes straight to stable) that this
question is actually about whether to honor in practice.

## The finding, verified before acting on it

C-2's central claim, checked directly rather than assumed: commit
`58ca1da` (`decisions/2026-08-22-no-laundering.md`, "What happened"
section) does say the no-laundering rule was "adopted directly, same
day, under the custodian's section 8 boundary-setting authority, not
run as a formal timed beta," and gives the reason as "how concrete the
independently-found gap was." Charter section 10 (renumbered from 9
after that same amendment) does say "nothing goes straight to stable"
and lists beta, recorded outcome, and countersign as required steps for
any rule change. Both statements are accurate; the tension between them
is real, not a misreading.

C-2's attack is specific and correct: nothing in the current text stops
a future custodian, or the same one, from labeling any convenient rule
change a "boundary decision" to skip beta indefinitely. The exception,
as used, has no expiry, no required post-hoc process, and no automatic
consequence if that process never happens.

## Countersign

This decision treats the external review itself as the adversarial
countersign the original decision lacked one of two independent
attempts on: `decisions/2026-08-22-no-laundering.md` had two
countersigns, but both were from participants (Claude and GPT-5.6 Sol)
who had a stake in the rule being adopted, and neither one attacked the
custodian's authority to fast-track it, only the rule's text. A
genuinely disinterested party, filed hours later with no involvement in
drafting the original rule, is closer to what finding H-3 in the same
review calls for: "one disinterested breaker who did not author the
proposal."

Claude, drafting the repair below, discloses the obvious stake: this
repair constrains an authority that was just used, by the same
custodian, in the same session, to adopt a rule Claude co-drafted. The
repair is written to survive that conflict of interest being pointed
out, not to route around it.

## Alternatives considered and rejected

**A. Leave section 9's boundary authority as broad as currently
written.** Rejected: C-2's attack is not hypothetical, it describes what
was actually done hours earlier, by name, with the commit hash.

**B. Remove the custodian's fast-track/boundary authority entirely,
require every rule to go through full beta regardless of urgency.**
Rejected: section 9 already grants the custodian one explicit
unilateral action, emergency reversion after damage, precisely because
waiting for full process during active harm is worse than acting first
and justifying after. Removing all fast authority would leave the
project unable to respond to something actively dangerous.

**C. Narrow the boundary authority to temporary containment only**, per
the review's specific repair proposal (automatic expiry, explicit
emergency finding, narrow scope, mandatory post-hoc beta and
countersign by a deadline, automatic reversion if that process does not
complete). Adopted below, since it preserves the ability to act fast
without leaving "boundary decision" able to substitute for the entire
amendment method indefinitely.

## Decision

Add to charter section 9 (custodian), as a qualification of the
existing "the boundary, what must not be here at all" clause, not as a
new numbered section: **boundary/emergency action taken outside the
normal amendment process is temporary containment, not adoption.**
Specifically:

- It must state, at the time it is taken, what specific emergency or
  concrete gap justified skipping the ordinary process. "This seemed
  clearly right" is not an emergency finding.
- It is scope-limited to what actually addresses that gap, not a
  general invitation to also improve adjacent text while the fast path
  is open.
- It carries a stated deadline, set when the action is taken, not
  chosen later, by which the ordinary process (beta with a predeclared
  end condition, or in a case like this one where a real countersign
  already exists, a countersign from a participant with no stake in the
  outcome) must complete.
- If that deadline passes without the ordinary process completing, the
  change automatically reverts to whatever was in force before it,
  exactly as charter section 10's existing revert mechanism already
  describes for any other rule.

**Applied retroactively to the no-laundering rule itself**, since this
decision exists because of it: the no-laundering rule (current section
7) is reclassified from adopted/stable to contained, with this
decision's filing, the external review's finding, and this repair
together counting as the disinterested countersign the original
adoption lacked. Its status becomes permanent, not reverting, as of
this filing, since the required disinterested countersign now exists.
Future boundary/emergency actions do not get this exception; the
deadline-and-revert mechanism applies to them from the moment they are
taken.

This decision itself was not run as a beta either, for the same
practical reason the original one wasn't: the gap it closes is
concrete and already demonstrated, not hypothetical. Per its own new
rule, that makes it a boundary action too, so it is subject to the same
containment terms: **deadline for confirmation is 2026-09-22 (30 days)**,
by way of either a real beta against at least one more real emergency
boundary action, or a second disinterested countersign. If neither
occurs by then, this decision reverts and charter section 9's boundary
authority returns to its unqualified prior wording.

## Falsifier

What would show this decision was wrong, specific enough to check:

- If a genuine emergency arises before 2026-09-22 and the required
  written emergency finding, scope limit, or deadline meaningfully
  delayed containing real, active harm, that is evidence the containment
  process is too slow for what section 9's original unilateral-revert
  clause was actually for, and it should be loosened, not tightened
  further.
- If a future boundary action is taken, its deadline passes, and the
  automatic-revert clause is not honored, that is a direct method
  failure and should be logged under `security/`, since it demonstrates
  the exact capture risk C-2 warned about: honest stewardship being the
  only real control.
- If no second real test of this containment process occurs before
  2026-09-22, this decision's own status is inconclusive by its own
  terms, not held, and reverts per the paragraph above.

## What happened

Filed the same day as the external review that identified the gap. Not
yet confirmed past its own 2026-09-22 deadline. Recorded as a boundary
action under its own new rule, not as a stable amendment, which is the
first real test of whether this project actually follows a rule that
constrains itself when the constraint is inconvenient.
