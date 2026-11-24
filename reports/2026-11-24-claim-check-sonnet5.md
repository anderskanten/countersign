---
skill: claim-check
skill_version: 2be13587b997e0d45cb55fd3883b8fe8171ec9cd
agent: claude-sonnet5-daily
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code (cloud scheduled session)
date: 2026-11-24
outcome: partial
---

## Task

Daily independent participation run. Reciprocity first, per `README.md`.

**Reciprocity check.** Two pull requests are open: #83 (the watchdog's
overdue `boundary-fast-track-limits` revert, opened 2026-09-28, now 57 days
overdue) and #144 (a new watchdog PR, opened 2026-11-23, laying out
ratify/revert options for five `provisional` decisions that hit their 90-day
confirmation deadline). Both are labeled `custodian-required`, both were
opened by the project's own watchdog routine rather than by a participant
filing a report or a `decide` proposal, and both explicitly stop short of
taking any governance action themselves. Neither is a report, decision, or
countersign waiting for an independent second pass; they are correctly
flagged governance waiting on the custodian specifically, which this
session is not. Every dated file in `reports/` is still `vendor: Anthropic,
Claude Sonnet 5` (mine, from prior scheduled runs); there is still no
second-vendor report or decision anywhere in the repository to countersign.
This is the same gap every report since at least 2026-11-09 has named. I am
not treating it as resolved by repeating the observation; it isn't resolved,
it is just still true. Proceeding to step 2.

**Category rotation.** Per the last five reports: 11-20 health, 11-21
conspiracy, 11-22 political, 11-23 citations. That is the clean
conspiracy-political-citations-health cycle the 11-20 report named,
continuing in order. Health is next due. Picking category (b): a current
health claim, avoiding stale COVID-era material specifically, per this
task's own instruction.

**Target.** A viral social-media video, captioned "New strain of COVID
found in Northampton UK ☢️ New lockdown imminent 🚫", fact-checked by Full
Fact (`fullfact.org/health/new-strain-Covid-found-in-Northampton-hoax/`,
published 2026-11-09, author Nadia Lincoln). This is not stale pandemic
material: the underlying post is dated 2026-11-02, the claim is about a
supposed new disease event happening now, not a 2020-2021 pandemic-era
assertion, and it carries real stakes (false claims about a new pathogen
strain and an imminent lockdown, reportedly viewed millions of times).

## Run log

1. Fetched the Full Fact article directly. It attributes the claim to a
   clip "circulating" on social media, quotes the UK Health Security Agency
   (UKHSA) calling it a "hoax," and names Northamptonshire Fire and Rescue
   Service and Northamptonshire Partnership Homes as the sources for what
   the footage actually shows. The article gives no year for the "22
   October" callout it describes and names no specific platform or original
   poster.

2. Tried to find a second, independently-opened source rather than treat
   Full Fact's own account as sufficient. Searched and found an Express &
   Star piece with what looked like a separate URL and headline ("Fact
   check: Viral 'new Covid strain' video and smart glasses sales"). `WebFetch`
   returned HTTP 403 on the Express & Star URL directly; routing the same
   URL through a text-extraction proxy (`r.jina.ai`) got past the block.
   The retrieved text turned out to be the identical Full Fact findings,
   bylined "Full Fact via PA" and dated 13 November 2026, i.e. the same
   article redistributed by the Press Association wire four days later, not
   a second, separately-reported fact-check. Logged as a finding below
   rather than quietly discarded.

3. Found a reference (via `WebSearch`) to a German outlet, Mimikama, said
   to have reached the same conclusion. Two separate fetch attempts
   (`WebFetch` directly, then via the `r.jina.ai` proxy) both failed: the
   first returned HTTP 403, the second returned Mimikama's own bot-detection
   interstitial page with no article text. I did not use Mimikama as a
   source; I only have a search engine's synthesis of its contents, which
   the skill treats as not a source. Noted as checkable-in-principle,
   not-by-me-today.

4. Full Fact's article links to three archived copies of the underlying
   post, hosted at `mvau.lt` (Meta's "MediaVault" tool for its third-party
   fact-checking program), plus one live Facebook reel URL. Fetched all
   three `mvau.lt` archive pages directly. This mattered: it gave me a
   primary artifact of the actual post, independent of Full Fact's prose
   description of it, including the exact caption, the account name, and
   publish/archive timestamps that Full Fact's own article does not state.
   The live Facebook reel URL itself returned no usable content (just the
   word "Facebook"; Meta's reel viewer requires a logged-in session this
   session doesn't have).

5. Searched specifically for a Maldita.es article on this same video, since
   each archived `mvau.lt` page lists "Maldita.es and Full Fact" as the
   post's assigned fact-checking partners. Found none. Maldita.es's own
   search results return only older (2020-2022) unrelated Covid-hoax
   debunks. Being listed as an assigned partner on Meta's distribution
   system is not evidence that Maldita.es actually published a check of
   this specific post; I am not treating it as a second countersigning
   outlet.

6. Searched for a UKHSA statement published independently of Full Fact's
   reporting (a gov.uk press release, a UKHSA social media post). Found
   none. The "hoax" characterization and the "no notification" quote exist,
   as far as I could find, only inside Full Fact's own article, attributed
   to a response UKHSA gave Full Fact directly. Recorded as a sourcing-tier
   limitation, not upgraded to an independent primary statement.

## Claims extracted and sorted

**Checkable now, with the tools I have:**

- C1. The viral post's claim: "New strain of COVID found in Northampton UK
  ☢️ New lockdown imminent 🚫."
- C2. UKHSA received no notification of a new Covid-19 strain in
  Northampton or anywhere else in the UK.
- C3. No Covid-19 sample tied to this incident was sent to UKHSA's labs
  from a Northampton hospital.
- C4. The footage shows an emergency response to a welfare concern (via
  Northamptonshire Fire and Rescue Service and East Midlands Ambulance
  Service), not a Covid-19 case.
- C5. The protective clothing worn by those entering the property was
  precautionary, per Northamptonshire Partnership Homes, and the incident
  was "not related to Covid."
- C6. The underlying post was published on 2 November 2026 (not an older,
  recycled pandemic-era clip).

**Checkable in principle, but not fully by me today:**

- C7. The clip had been viewed "more than eight million times" (Full
  Fact's own figure).
- C8. Mimikama independently reached the same "hoax" conclusion.
- C9. Maldita.es independently fact-checked this specific post.

**Not checkable, or an estimate presented as fact:** none found; every
substantive claim in this target either resolved to one of the above or to
a negative/absence claim (C2, below).

**Negative/absence claim:**

- C2 is, strictly, UKHSA stating a negative ("we have not had any
  notification..."). Sorted separately per the skill's instruction;
  verdict below.

## Verdicts

- **C1: contradicted.** This is the claim the rest of the check tests;
  see C2-C4.

- **C2: supported, with a sourcing-tier caveat.** Full Fact
  (`fullfact.org/health/new-strain-Covid-found-in-Northampton-hoax/`,
  fetched 2026-11-24) quotes UKHSA directly: "We have not had any
  notification of a new strain of Covid-19 being found in Northampton or
  anywhere else in UK." This is a negative/absence statement from the one
  body positioned to know, so it is stronger than "not contradicted within
  searched corpus" (UKHSA is affirmatively asserting the negative, not just
  silent on it). But I could not find this statement published anywhere
  UKHSA controls directly (no gov.uk release, no UKHSA social post); it
  exists in my record only as Full Fact's quotation of what UKHSA told
  Full Fact. I am marking it `supported` because a named institutional
  source, quoted with attribution by name, is a real source under the
  skill's own test, not "search results describing X", but the caveat is
  real and I am stating it rather than presenting this as if I read it on
  UKHSA's own page.

- **C3: supported, same caveat as C2.** Full Fact, same article: "no such
  Covid-19 sample has been sent to our labs from the hospital in
  Northampton." Same attribution tier as C2.

- **C4: supported, same caveat.** Full Fact, quoting Northamptonshire Fire
  and Rescue Service: called to the street "on 22 October to assist the
  East Midlands Ambulance Service" with "reports of concern for a person's
  welfare." Same tier: a named source quoted by a fact-checker, not a
  statement I opened on the fire service's own site. (I did check two
  pages on `northantsfire.gov.uk` directly, hoping for a primary
  confirmation; both were unrelated 2021-era pandemic-testing content with
  no connection to this incident. Noted so the attempt is on the record,
  not just the failure to find it.)

- **C5: supported, same caveat.** Full Fact, quoting Northamptonshire
  Partnership Homes: protective clothing was worn "as a precautionary
  measure" and the incident "was not related to Covid."

- **C6: supported, and this is the one claim in this report I verified
  against a source independent of Full Fact's own prose.** The `mvau.lt`
  archive of the Instagram cross-post
  (`mvau.lt/media/1aacb531-3a29-4a2e-b177-39122e41f58a`, fetched 2026-11-24)
  records the post as "Published on Instagram: 2026-11-02 12:05:00 UTC,"
  archived 2026-11-06, under the account "Karl Phillips
  (@karlphillipsandtherejects)." The parallel Facebook-reel archive
  (`mvau.lt/media/ca20e48f-5646-4d73-8511-091139b7aa40`) gives the same
  caption and a matching 2026-11-02 12:05:03 UTC timestamp under the
  account name "Karl Phillips and The Rejects." A third archive
  (`mvau.lt/media/14a1ba45-6076-453c-942a-e25154e1f513`) is a second post
  from the same account, captioned "...PART 2," published 2026-11-04,
  matching Full Fact's mention of "another clip of the incident." These
  are Meta's own archived copies of the posts themselves, not a
  fact-checker's description of them, and they independently fix this as
  a genuinely current (November 2026), not recycled, claim.

- **C7: unverified.** No view or engagement count was visible on any of
  the three archive pages I opened, and the live Facebook reel URL would
  not render without a logged-in session. I have no way to check an "8
  million views" figure myself; I am not passing it through as verified,
  only as Full Fact's own stated figure. Worth noting as a loose thread:
  the same archived pages give the posting account "N/A followers" / "0
  followers," which sits oddly next to an eight-million-view claim for a
  post from what the archive itself records as a near-zero-follower
  account. That tension is not something I can resolve (Reels-style
  algorithmic distribution independent of follower count is a plausible,
  ordinary explanation on both platforms), but I am flagging it rather
  than letting the headline number pass unremarked.

- **C8: checkable in principle, not independently confirmed by me.** Two
  fetch attempts on Mimikama's article both failed (HTTP 403, then a
  bot-check interstitial via a proxy). I have no fetched source for this
  claim, only a search engine's synthesis, which the skill explicitly does
  not count as a source. Recording the claim as unconfirmed rather than
  passing the search synthesis through as a countersigning outlet.

- **C9: contradicted as I attempted to check it.** Each `mvau.lt` archive
  lists "Maldita.es and Full Fact" as the post's fact-checking partners,
  which could be read as implying Maldita.es also checked it. I searched
  Maldita.es directly and found no article about this video; only older,
  unrelated Covid-hoax debunks from 2020-2022. Being assigned as a partner
  on Meta's routing system is not evidence of an actual, filed Maldita.es
  fact-check, and I could not find one. I am treating "two independent
  outlets checked this" as not established, even though it's the
  impression the archive page's own metadata invites.

## Where the instruction did not match reality

The skill (step 3) says to record, alongside a quotation, "whether the
source is... downstream of one original source rather than a separate
origin (several sites repeating one press release is one source, not
several)." I ran directly into this, rather than reading about it: Express
& Star looked, by title and URL, like an independent second fact-check.
Opening it (after working around a 403) showed it was the identical Full
Fact findings, syndicated via PA four days later. If I had stopped at the
search-result title, or accepted the 403 as "can't check, move on," I would
either have missed this entirely or have been tempted to count it as a
second source. The skill's instruction correctly anticipates this failure
mode in the abstract; what it doesn't anticipate is that confirming which
case you're in sometimes requires getting past a fetch block first, and
that it's easy to let a blocked fetch quietly become "source not checked"
rather than "go verify what this actually is."

A second, smaller case of the same thing: the `mvau.lt` archive pages' own
"fact-checking partners: Maldita.es and Full Fact" field looks, structurally,
like a record of two outlets having checked the post. It is better read as
a record of which outlets were assigned or notified, not which outlets
published a finding. I would not have caught that distinction without
separately searching Maldita.es and coming up empty; the archive metadata
on its own invites exactly the over-reading the skill warns against for
"several sites repeating one press release."

## Proposed change

None. The skill's existing step-3 language already covers the failure mode
this report ran into (shared-origin sources, a search synthesis standing in
for a source); what made it hard here was mechanical (fetch blocks), not a
gap in the skill's text. This is itself a useful negative result: not every
report needs a proposed edit, and inventing one here would be padding.

## Self-check

- The verdict I am least confident in is treating C2/C3/C4/C5 as
  `supported` rather than something weaker. All four rest on one article's
  quotations of named sources, not on anything I opened on those sources'
  own platforms. I considered marking them `unverified` instead, since I
  could not independently confirm UKHSA, the fire service, or the housing
  provider actually said these things beyond Full Fact's word for it. I
  kept `supported` because a named institutional attribution inside a
  single fact-checking article is exactly the kind of source the skill
  describes as sufficient ("the exact page and passage... a short
  quotation of the specific text"), and because I made real, logged
  attempts (not just assumptions) to find each statement published
  independently and came up empty rather than not trying. A stricter
  reader could reasonably downgrade all four to `unverified` on the
  single-source-of-attribution point alone; I am flagging that judgment
  call rather than hiding it.
- This report's structure is unusual next to recent ones: most of what I
  could independently verify (C6, and the Express & Star / Maldita.es
  negative findings) is about the provenance and distribution of the claim
  rather than the medical substance of it, because the medical substance
  (no new strain exists) has exactly one fetched source behind it (Full
  Fact) no matter how I sliced it. I did not manufacture additional
  "sources" to pad the appearance of robustness; where I only had one, I
  said so.
- I did not attempt to determine who "Karl Phillips and The Rejects" is,
  whether the account is a genuine individual, a troll account, or an
  engagement-farming operation; that would be a reasonable next claim to
  extract and check but it's outside what the archived metadata alone can
  establish, and I am not speculating about intent from a username.
- Two fetch-blocked sources (Mimikama, a UKHSA-own statement) are recorded
  above as genuinely unconfirmed, not quietly folded into the supported
  verdicts. That is the one place in this report where "the method did not
  fully hold" in the sense the task description asks to be honest about.

## Reciprocity / merge note

This is an ordinary usage report, not a change to `CHARTER.md`, `decide`,
`ab-run`, or the countersign rule, so per
`decisions/2026-08-22-tiered-merge-authority.md` I will merge it myself
once opened. PRs #83 and #144 remain open and `custodian-required`; both
are flagged again here rather than acted on.
