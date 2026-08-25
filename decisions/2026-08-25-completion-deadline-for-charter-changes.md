---
id: 2026-08-25-completion-deadline-for-charter-changes
type: directional
status: open
countersigned_by: []
---

## Question

Two independent adversarial reviews obtained the same day (ChatGPT's
fresh review, finding 1; Hermes Agent's third review, finding 1) both
identified the same structural gap: the custodian "may reject only on
the three grounds in section 9," but nothing obligates the custodian to
actually apply step 5 once a proposal has completed the amendment
procedure. Silence indefinitely blocks adoption without ever being a
stated rejection anything can be appealed against. Should
`CHARTER.md` gain a completion deadline, after which a fully-vetted,
already-countersigned proposal merges automatically if the custodian
has neither applied it nor recorded one of the three grounds?

Raised by the custodian directly, who asked for the automatic-merge
version specifically (not just a visibility/overdue-marking fix, which
was the first, lighter option proposed) and explicitly connected it to
the already-disclosed succession gap: "da vil dette virke uansett" (then
this works regardless), i.e., the mechanism should also cover the case
where the custodian is genuinely unreachable, not only inactive by
choice.

## Type, and why

Directional. Whether some forcing function should exist is effectively
settled (asked for directly); what's open is the concrete mechanism and
number.

## Positions filed blind

**Claude Sonnet 5 / Anthropic.** 30 calendar days, measured from when a
proposal completes all steps the amendment procedure already requires
(held per `skills/ab-run` where applicable, real countersign obtained,
and for section 9 changes specifically, the day-gap requirement already
satisfied). A scheduled, non-interpreting check, the same pattern
already running for boundary-action deadlines, applies the exact
countersigned text on file, no new judgment, no paraphrase. 30 rather
than the appeal's 14: a charter amendment is higher-stakes and deserves
more time for genuine deliberation, but a multi-week gap is long enough
that "the custodian is unreachable for a while" no longer permanently
blocks the project, which is the actual failure mode this responds to,
per the custodian's own framing.

## Alternatives considered and rejected

**Visibility only (mark overdue, no automatic merge).** This was the
first fix proposed and initially recommended, on the grounds that no
skill has ever reached `beta` yet, so building enforcement for a
scenario that has never occurred is solving a hypothetical. The
custodian explicitly asked for the stronger version instead, connecting
it to the succession gap rather than treating it as premature. Once
tied to "what happens if I'm actually gone," it is not hypothetical
risk-aversion, it is the same category of gap the project already
disclosed openly in section 9's succession line.

**Shorter deadline (14 days, matching appeals).** Rejected: an appeal
is a response to a specific disagreement; a charter amendment can be
substantively harder to evaluate and deserves more time before any
automatic fallback engages.

**No deadline at all, status quo.** Rejected: this is exactly the gap
two independent reviews converged on the same day, and the custodian
asked directly for a fix, not a defense of the status quo.

## Decision

Not yet decided. Proposed addition to `CHARTER.md` section 10,
immediately after "The custodian applies step 5, and may reject only on
the three grounds in section 9. Disliking the outcome is not one of
them.":

> **A completion deadline applies once a proposal is ready.** The
> custodian has 30 calendar days from the point a proposal completes
> every step the amendment procedure above already requires (including,
> for a section 9 change, section 9's own harder path) to either apply
> step 5 or record which of the three grounds in section 9 blocks it.
> Passing that window with neither recorded is not resolution by
> silence: a scheduled, non-editing check applies the exact
> countersigned text on file, with no interpretation and no new
> judgment, the same way an overdue boundary-action deadline already
> reverts automatically. This applies whether the custodian is simply
> silent or genuinely unreachable; it is the operative half of the
> succession gap named above, not a separate mechanism.

This is a change within section 10 (the sentence it extends is itself
in section 10, not section 9), so the ordinary process applies: real
countersign, custodian merge, no same-day restriction from section 9's
harder path.

## Falsifier

- If this mechanism ever actually merges a change the custodian would
  have rejected had they seen it in time, that is evidence the deadline
  is too short or the pre-deadline warning (still to be built into the
  watchdog) failed, and this should be reopened.
- If the watchdog implementing this ever merges anything beyond the
  literal, already-countersigned text on file, exercising any
  interpretation or judgment, that is a direct violation of this
  decision's own limit and should be logged under `security/`.
- If 30 days proves too short in practice (a genuinely difficult
  proposal needing more deliberation gets auto-merged before real
  consideration), that is evidence for a longer window, not for
  removing the deadline.

## What happened

Filed 2026-08-25. Not yet countersigned or merged. The implementing
watchdog routine will be built once this text is confirmed, extending
the existing boundary-deadline check rather than creating a second,
separate automation.
