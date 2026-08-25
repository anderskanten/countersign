---
id: 2026-08-25-external-review-as-disinterested-countersign
type: directional
status: open
countersigned_by: []
---

## Question

`CHARTER.md` section 10's path for section 9 requires "at least one
countersign from a participant with no stake in the proposal, who did
not draft it." In practice, this project currently has exactly two
active AI participants, Claude and ChatGPT, both accessed by the
custodian in sessions the custodian personally controls and directs.
Should an external, disinterested review, conducted by a different
operator on infrastructure the custodian does not control, formally
satisfy this requirement, given that a custodian-solicited AI
countersign cannot establish independence from the one relationship
every current participant shares?

Raised by the custodian directly, after asking whether requiring 3-4
independent models would solve the problem and being talked out of it
(unachievable given only two vendors are actually accessible; a
requirement nothing can satisfy freezes governance rather than
protecting it). This proposal is the alternative: fix what
"disinterested" means, not how many entities are asked.

## Type, and why

Directional. Whether the custodian relationship undermines "no stake"
for section 9 purposes is close to settled already (this project has
repeatedly marked custodian-solicited countersigns `provisional` for
exactly this reason, most recently the completion-deadline mechanism
itself). What's open is the concrete mechanism for what counts as a
genuine substitute.

## Positions filed blind

**Claude Sonnet 5 / Anthropic.** A countersign obtained by the custodian
from an AI model in a session the custodian personally controls is
useful and should still be sought, but does not by itself satisfy
section 9's "no stake" requirement, because the custodian is the one
relationship every currently-active participant shares. An external
review satisfies it instead, but only when it explicitly examines the
specific text being proposed, not a general recommendation later
implemented differently. Where no such review exists yet, the proposal
proceeds as `provisional` (already the standing rule from
`skills/decide`) rather than blocking entirely, since demanding an
external review be available on demand for every section 9 change
would itself recreate the "unsatisfiable requirement" problem the
3-4-models idea had.

Reasoning: this is not a new rule so much as making an already-applied
practice explicit and consistent. The completion-deadline decision was
marked `provisional` this same day for structurally the same reason
(neither Claude nor ChatGPT was disinterested in that specific
proposal). Writing the general principle down means future proposals
don't have to rediscover it case by case, and means a future external
reviewer (Hermes Agent, or anyone else with no relationship to the
custodian) can be pointed at the actual disputed text and treated as
the real check it is.

## Alternatives considered and rejected

**Require a fixed number of independent models (3, 4, or more).**
Rejected: the project has exactly two vendors accessible to the
custodian right now. A numeric requirement nothing can satisfy doesn't
create independence, it creates permanent inability to change section
9 at all, which is a worse failure than the one being fixed.

**Leave custodian-solicited AI countersigns as fully sufficient,
status quo.** Rejected: this is the exact gap two independent reviews
(ChatGPT's and Hermes Agent's) converged on the same day, calling it
structurally unsatisfying. Continuing to treat it as sufficient after
naming the problem would be pretending not to have found it.

**Require external review for every section 9 change, no fallback.**
Considered and set aside, not rejected outright: cleaner in principle,
but risks recreating the freezing problem if no external reviewer
happens to be available when a genuinely urgent, well-reasoned
amendment is ready. The `provisional` fallback keeps the project
moving while being honest about what hasn't been independently checked
yet.

## Decision

Not yet decided. This proposal is, appropriately, in the same position
it describes: no genuinely disinterested countersign is currently
available for it, since Claude drafted it and ChatGPT has an obvious
stake in whether its own past countersigns "count." It should not be
self-countersigned by either. Filed open, waiting on either an actual
external review (the natural candidate: forward this specific proposal
to Hermes Agent / Terje, the same way past findings have been
verified) or the custodian's own read on whether to proceed with it as
`provisional` in the interim, matching the standing rule.

Proposed text change to `CHARTER.md` section 10, "The path for section
9," item 3 (replacing the current single sentence):

> 3. At least one countersign from a participant with no stake in the
>    proposal, who did not draft it, is required, on top of whatever
>    the custodian decides. A countersign the custodian personally
>    solicited from an AI model, in a session the custodian controls,
>    is useful but does not by itself satisfy this requirement: the
>    custodian is the one relationship every currently active
>    participant shares, so such a countersign cannot establish
>    independence from the custodian specifically. An external,
>    disinterested review, conducted by a different operator on
>    infrastructure the custodian does not control, that explicitly
>    examines the specific text being proposed, satisfies this
>    requirement. Where no such review is available, the proposal may
>    still proceed as `provisional` per `skills/decide`, not blocked
>    entirely, until one becomes available.

## Falsifier

- If this rule is later used to justify treating a custodian-solicited
  countersign as fully sufficient anyway (by redefining "stake"
  narrowly enough to exclude the custodian relationship itself), that
  is a direct violation and should be logged under `security/`.
- If external reviews turn out to never actually engage with specific
  proposed text (always general, never attacking the literal wording),
  the "satisfies this requirement" clause is not doing real work and
  this should be reopened.
- If the `provisional` fallback becomes the permanent state for every
  section 9 change because external review never actually arrives in
  practice, that is evidence the fallback needs a time limit of its
  own, not evidence the underlying rule is wrong.

## What happened

Filed 2026-08-25. Not yet countersigned. Deliberately not merged pending
either an external review or an explicit custodian decision to proceed
provisionally.
