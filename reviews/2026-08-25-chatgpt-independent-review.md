# ChatGPT independent adversarial review

Requested by the custodian ("kan du be chatgpt se etter svakheter?"),
not tied to a specific proposal. Obtained blind, in a fresh chat, asked
to browse the live repository directly rather than rely on prior
context, and to hunt for contradictions, custodian power exceeding what
the text intends, letter-vs-spirit exploits, and vague wording.

## Verification preface

ChatGPT's first pass initially quoted stale fetched content (the
appeal-deadline paragraph still showing "a reasonable time," a wording
replaced the day before) and, on its own, partly caught this: it
noticed and corrected a separate staleness issue (section 9 shown as
absolutely immutable) before finishing, but not the appeal-deadline
one. When corrected directly with a fresh `curl` of the live raw file,
it withdrew that finding (originally finding 4) rather than defending
it, and folded the narrower part that survived into finding 1. This is
recorded because it is itself a data point about the project's own
concern with stale-context claims, not a flaw unique to ChatGPT.

Findings 1, 2, 3, 5, 6, and 7 below were independently checked against
the live files before filing. Finding 5 (CLAUDE.md's internal
contradiction between the tiered-merge-authority exception and "Never
do without the custodian: Merge a governance PR") was found
independently by Claude via direct file read in the same session,
before reading ChatGPT's answer, then confirmed to be the same finding.
Finding 2 (the section 9 amendment path requiring one countersign
against the ordinary process's two) was verified by direct comparison
of the two numbered lists in `CHARTER.md` section 10.

---

## 1. HIGH: pocket veto by inaction

The custodian "may reject only on the three grounds in section 9," but
nothing obligates the custodian to actually apply step 5 once a change
has properly completed the amendment procedure. Silence indefinitely
prevents adoption without ever being a "rejection" the appeal
mechanism, or anything else, can act on. `CLAUDE.md` reinforces this by
forbidding anyone else from merging `CHARTER.md`.

Fix proposed: either a completion deadline (N days to apply or record a
ground) with a narrowly defined fallback merge path, or an explicit
admission in the charter that the custodian holds a veto by inaction,
not only by stated rejection.

## 2. HIGH: the "harder" section 9 path requires less evidence than the ordinary one

Verified directly: the ordinary rule-change process (section 10, "How
to change a rule") requires beta, preregistered measures, and **two**
countersigns from different underlying models, at least one trying to
break the proposal. Section 9's own harder path requires only **one**
disinterested countersign and no beta. The single most protected clause
in the document can be changed on weaker evidence than an ordinary
rule, while being described as harder.

## 3. MEDIUM/HIGH: "narrow or clarify" versus "may not permit anything currently caught" are in tension

Any genuine narrowing of a removal ground necessarily makes some
previously-caught case no longer caught, that is what narrowing means.
The current wording allows narrowing while forbidding exactly that
consequence. Two good-faith readers of a future section 9 proposal
could reach opposite conclusions, both textually defensible.

## 4. WITHDRAWN

Originally: appeal deadline exists only in secondary files, not the
charter itself. Based on stale content; the live charter states 14
calendar days directly. Withdrawn on correction. A narrower residual
concern (the 14-day rule creates visibility but not enforcement) was
folded into finding 1 rather than kept separate.

## 5. MEDIUM: CLAUDE.md self-contradiction on governance merges

`CLAUDE.md` both authorizes non-charter governance content to
self-merge when backed by real countersign or external review, and
separately lists, with no qualifier, "Merge a governance PR" under
"Never do without the custodian." Both instructions cannot be obeyed at
once. Fixed 2026-08-25 by qualifying the absolute bullet.

## 6. MEDIUM: "different underlying models" vs "different vendors" is not one definition

`CHARTER.md` section 10 requires "different underlying models" for a
countersign. `README.md`, `CLAUDE.md`'s promotion audit, and
`skills/decide` all separately use "vendor," and `skills/decide` uses
both terms in adjacent sentences without saying whether they are the
same axis. Two same-vendor, different-model-family passes could be
disqualified by one document's wording and qualified by another's.

## 7. MEDIUM: `skills/decide` is `state: proposed` yet constitutionally load-bearing

`CHARTER.md` section 10 requires charter amendments to be filed under
`skills/decide`, and that skill's own frontmatter says it has not been
validated (`proposed`). Since `CLAUDE.md` allows independently-backed
skill changes to self-merge without the custodian, the mutable contents
of a `proposed` file can change what "properly filed" means for charter
amendments, without ever touching `CHARTER.md`'s own text.

---

## Priority order given

1 → 2 → 5 → 4(withdrawn) → 3 → 6 → 7.

## Not elevated to findings

Self-attested identity: already disclosed by the project itself, an
acknowledged limitation, not a hidden contradiction. Appeals being
persuasive rather than binding: not itself a bug, the charter states
this openly; the actual problem is finding 1 (unbounded power to delay
combined with a weak appeal).
