---
skill: claim-check
skill_version: 13ec667
agent: claude-sonnet-5
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code
date: 2026-08-22
outcome: partial
---

## Task

Verified the factual claims on a live third-party page,
`sertifiseringssenteret.no/truck/krav-til-truckforerbevis/`, which states
requirements for a Norwegian truckførerbevis (forklift operator
certificate): age, validity, legal basis, and training content. This was
real work, not a rehearsal: the operator runs a certification business and
wanted to know whether the page holds up against primary sources before
relying on it.

## Run log

1. Fetched the target page and extracted every distinct factual claim
   (age requirement, training start age, validity/expiration, legal
   basis, training content, employer duty, prerequisites for telescopic
   trucks).
2. Sorted claims into the three buckets the skill specifies.
3. For legal-basis and validity claims, went to Lovdata directly:
   `forskrift om utførelse av arbeid` chapter 10 (2011-12-06-1357). For
   the age claim, went to `forskrift om arbeid av barn og ungdom`
   (1998-04-30-551) via Arbeidstilsynet's own summary. For the
   registration claim, went to search results describing Stiftelsen
   Sentralregisteret (founded 1989 by Direktoratet for arbeidstilsynet).
4. Recorded a verdict per claim below.

## Claims and verdicts

1. **"For å få utstedt bevis må du være fylt 18 år"** (certificate not
   issued before age 18) - `supported`. Matches the structure in
   forskrift om arbeid av barn og ungdom: practical training on this
   class of equipment can start at 17 under supervision, issuance at 18.
2. **Training may start at 17** - `supported`, same source as above.
3. **No upper age limit** - `unfalsifiable as stated`. This is a claim
   of absence. No source imposes an upper limit, but absence of a limit
   in the sources I checked is not the same as a source stating there is
   none.
4. **"Beviset registreres i Sentralregisteret"** - `supported`.
   Stiftelsen Sentralregisteret is a real, independent register
   established in 1989 on the initiative of the labour inspection
   authority, and issues competence certificates for truck, crane, and
   machine.
5. **"...og har ingen utløpsdato"** (no expiration date) - `supported`.
   Chapter 10 of forskrift om utførelse av arbeid requires documented
   training (§ 10-2) and certified training for listed equipment (§
   10-3), but I found no clause anywhere in that chapter setting a
   validity period or renewal interval.
6. **Legal basis is forskrift om utførelse av arbeid, specifically
   §10-3** - `supported`, confirmed on both Arbeidstilsynet's own page
   and Lovdata.
7. **Training must be delivered by "godkjent sertifisert
   opplæringsvirksomhet"** - `supported`, Arbeidstilsynet states a
   business providing this training must itself be certified by a
   certification body.
8. **Modul 1-4 course structure** (general theory / classroom theory
   with exam / practical modules) - not a checkable external claim. This
   is the operator's own curriculum packaging, not a fact asserted about
   the world. The regulation specifies required content areas
   (oppbygging, betjening, bruksegenskaper, bruksområde, vedlikehold og
   kontroll) without mandating a four-module structure, so the page is
   free to organise it this way. Filed as not-applicable rather than
   forcing a verdict.
9. **C1/C2 (telescopic truck) requires prior T/M/G8 certification** -
   `checkable in principle, but not by me in this run`. This would need
   the specific Arbeidstilsynet læreplan document for teleskoptruck,
   which I did not pull.
10. **T1-T5 has no prerequisite knowledge or prior training required** -
    `checkable in principle, but not by me in this run`, same reason.

## Where the instruction did not match reality

Skill step 2 sorts claims into three buckets: checkable now, checkable in
principle but not by me, and "not checkable, an estimate presented as
fact." Claim 3 (no upper age limit) and claim 8 (the module structure)
did not fit cleanly into any of the three. Claim 3 is a negative claim
where I can show no contradicting source exists but cannot show a source
that affirmatively states "there is no upper limit." Claim 8 is not a
factual claim about the world at all, it is a description of the
target's own product design, so calling it "unverified" or "an estimate
presented as fact" would misrepresent what it actually is. The skill has
no fourth bucket for "not a factual claim" or fifth for "claim about
absence." I used `unfalsifiable as stated` for the first and excluded
the second from a verdict entirely, which is an improvisation, not
something the skill told me to do.

A genuinely useful finding while checking the validity claim: at least
one other Norwegian training-provider page found during the same search
(not the target of this check) asserts truck certificates "must be
renewed every five years." I did not find that claim supported anywhere
in the regulation. I am not filing a claim-check on that page since it
was not the target, but noting it here because it means the "no
expiration date" position on the checked page is the one that holds up,
not the majority position among the pages I saw in search results.
Popularity of a claim is not support, in either direction.

## Proposed change

Add a fourth category to step 2, or a note after it: "A claim about the
absence of something (no limit, no expiration, no requirement) is
supported by the absence of a contradicting source, but flag it as an
absence-claim rather than marking it identically to a claim you
positively confirmed against a source that states it outright." And add
one line clarifying that a checked page may contain non-factual content
(product structure, marketing framing) that should be set aside rather
than forced into a verdict.

## Self-check

I nearly marked claim 3 (no upper age limit) as plain `supported`
alongside the others, which would have overstated what "I found no
source imposing a limit" actually shows. Separating it out as
`unfalsifiable as stated` took a second pass, after I had already
written the first draft of the verdict table. I also did not
independently verify claims 9 and 10 by pulling the specific
læreplan-dokument, and initially wrote "supported" from general
plausibility before catching that I had not actually opened a source
for either. Both are marked `checkable in principle, but not by me in
this run`, which is accurate; `supported` would not have been.
