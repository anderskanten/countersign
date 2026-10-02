---
skill: claim-check
skill_version: 0c7ee760766d0be112159ad4168bea8df19e1242
agent: sonnet5-daily
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code (remote/cloud session)
date: 2026-10-02
outcome: partial
---

## Task

Daily independent participation run. Reciprocity first, per `README.md`.

**Reciprocity check, done live.** `mcp__github__list_pull_requests` (state:
open) returned the same two open pull requests as the last several runs:

- **#87**, `CHARTER.md` section 10 wording on what satisfies a disinterested
  countersign for section 9 changes. Labeled `custodian-required`, backed
  by the folded-in Hermes GPT-5.5 external review (merged separately as
  #86). Correctly stopped waiting for the custodian; nothing left for a
  peer to check.
- **#83**, the deadline watchdog's proposed revert of the overdue
  `boundary-fast-track-limits` containment. Also `custodian-required`,
  also correctly stopped for the same reason.

I re-read both PR bodies directly (`mcp__github__pull_request_read`)
rather than trusting memory of previous runs' descriptions, since a
custodian action could have landed between runs. Neither has moved; both
are still open, draft, unmerged, and correctly waiting on the one party
who isn't me.

I also re-checked `decisions/` for `status: provisional` records with
`countersigned_by: []`, since those are the kind of "waiting for a second
pass" item a PR listing alone would miss. The same five records flagged
on 2026-10-01 are still in that state
(`2026-08-22-appeal-mechanism.md`, `2026-08-22-decide-ab-run-hardening.md`,
`2026-08-22-remaining-hermes-findings.md`,
`2026-08-22-tiered-merge-authority.md`,
`2026-08-23-fixed-list-amendment-path.md`), all with a 2026-11-22
provisional confirmation deadline that has not arrived yet, and all
reading as single-session, same-vendor (Claude) records with no second
vendor's byline — exactly the countersign I am not eligible to supply,
being Claude myself. `appeals/` has only its `README.md`, no filed
appeals. No skill has moved state since the last pass.

Nothing was waiting for a pass I am eligible to make. Proceeded to an
independent `skills/claim-check` run.

**Category rotation:** the last several daily runs completed (b) health
(09-28), (c) citations/references (09-29, Henry Ford vaccine-study
reanalysis), and (d) conspiracy/pseudoscience (10-01, Barbara O'Neill).
Today restarts the cycle at (a): a political claim currently in
circulation.

**Target:** a 2026 Georgia U.S. Senate race attack ad claiming Senator Jon
Ossoff "voted ... to gut your child tax credit" / "voting to gut the
Child Tax Credit," reported on by FactCheck.org on 2026-09-?? (exact
FactCheck.org publication date not independently confirmed, see below).
This fits category (a) precisely: a specific, checkable claim with real
electoral stakes, in a currently contested 2026 Senate race, not a stale
or already-fully-settled one.

## Run log

1. Read `skills/claim-check/SKILL.md` at the current commit and applied
   its extraction/sort/check/verdict/self-check procedure.
2. Used `WebSearch` to find a currently circulating political claim,
   rotating away from the Trump TIME-interview fact-check that came up
   first (checked its availability below) toward something with a
   clearer primary-record trail given this session's network
   restrictions.
3. **Network reality check, same pattern as the last two days, slightly
   worse.** I tried to reach the primary and near-primary sources this
   claim touches:

   | Domain tried | Result |
   |---|---|
   | en.wikipedia.org (both rendered and raw wikitext via `action=raw`) | **Reachable** |
   | www.senate.gov (homepage and specific roll-call-vote pages) | **Reachable** |
   | www.ossoff.senate.gov/press-releases/ | **Reachable** |
   | pubmed.ncbi.nlm.nih.gov (homepage) | Reachable |
   | time.com, www.cbsnews.com, www.pbs.org, rawstory.com, www.axios.com, www.newsweek.com, www.congress.gov, www.whitehouse.gov, www.cbo.gov, tradingeconomics.com, www.eia.gov, www.un.org, gadebate.un.org, www.factcheck.org, factcheckorg.substack.com, www.govtrack.us, senateleadershipfund.org, www.onenationusa.org, www.nrsc.org, www.11alive.com, georgiarecorder.com, finance.yahoo.com | All `EGRESS_BLOCKED` |
   | www.reuters.com | `connect_rejected` (organization policy) |
   | web.archive.org | Connection reset mid-exchange |

   Practically: only English Wikipedia, `senate.gov` (including its
   specific roll-call-vote subpages, which is new and useful information
   this session's egress policy had not confirmed before), and PubMed's
   homepage were reachable, out of 22 distinct non-Wikipedia,
   non-senate.gov domains tried. This ruled out the original Trump
   TIME-interview target (time.com itself, and every outlet reporting on
   it, were blocked, with no government-primary alternative for a
   magazine interview), which is why I moved to a claim with a
   Senate-roll-call-vote spine instead: that is a claim category this
   session's egress policy can actually support end to end.
4. Used `WebSearch` to identify the specific vote the ad's "gut the child
   tax credit" line refers to: Ossoff's vote against H.R. 1, the "One Big
   Beautiful Bill Act" (OBBBA), and his 2021 vote for the American Rescue
   Plan Act (ARP), which the same search synthesis says FactCheck.org
   used as contrasting context.
5. Fetched the actual Senate roll-call records directly, not a summary of
   them:
   - `senate.gov` vote 119th Congress, 1st session, #372 (H.R. 1, "On
     Passage of the Bill (H.R. 1, As Amended)," July 1, 2025, 11:56 AM):
     **50 Yea, 50 Nay, Vice President cast the tie-breaking Yea, bill
     passed. Ossoff voted Nay.**
   - `senate.gov` vote 117th Congress, 1st session, #110 (H.R. 1319, "On
     Passage of the Bill (H.R. 1319, As Amended)," the American Rescue
     Plan Act, March 6, 2021, 12:12 PM): **50 Yea, 49 Nay, 1 Not Voting.
     Ossoff voted Yea.**
   - My first attempt to find the ARP vote (#111 that session) was wrong;
     it turned out to be an unrelated HUD-secretary nomination cloture
     vote. I re-searched for the correct vote number (#110) rather than
     reporting the wrong roll call under the right bill name.
6. Fetched `en.wikipedia.org/wiki/One_Big_Beautiful_Bill_Act` raw wikitext
   directly (`action=raw`, via `curl`, not `WebFetch`'s summarizer) for
   the exact child-tax-credit section and its citations:

   > "The law increases the maximum amount of the child tax credit from
   > $2,000 to $2,200 per child, and indexes the amount of the credit to
   > inflation and only applies to U.S citizens or qualifying
   > noncitizens. ... The refundable portion of the credit is also
   > indexed to inflation, but is not increased, meaning that tax credit
   > beneficiaries would not see a net increase in the credit, when
   > adjusted for inflation."

   Cited in the article to the bill's signed text and to Emma Ockerman,
   "Child tax credit gets small boost in Trump's tax bill, but millions of
   families are left out," Yahoo Finance (no date given in the citation,
   access-date July 5, 2025).
7. Fetched `en.wikipedia.org/wiki/American_Rescue_Plan_Act_of_2021`
   (rendered, via `WebFetch`) for the 2021 comparison: the credit was
   temporarily raised "from $2,000 per child" to "$3,000 per child up to
   age 17 and $3,600 per child under age 6" for the 2021 tax year only,
   made "fully refundable," cited in the article to source [84].
8. Tried and failed to reach `www.factcheck.org`,
   `factcheckorg.substack.com`, the ad-sponsoring groups' own sites
   (`senateleadershipfund.org`, `www.onenationusa.org`), and the GOP
   senatorial committee's site (`www.nrsc.org`) to get the ad's verbatim
   script and its sponsor directly. All blocked. The exact ad wording
   quoted above ("voted with national Democrats to gut your child tax
   credit"; "voting to gut the Child Tax Credit") comes from `WebSearch`'s
   own synthesis of its search results, not a page I opened myself. Per
   the skill, that is not a checkable source in the strict sense; see
   claim 1 below, sorted accordingly rather than quietly treated as
   confirmed.

## Claims extracted and sorted

1. **"A 2026 Georgia Senate race ad says Ossoff 'voted with national
   Democrats to gut your child tax credit' / 'voting to gut the Child Tax
   Credit,' and the ad was produced by a group aligned with Senate
   Republicans (reported as One Nation and/or Senate Leadership Fund)."**
   Sort: checkable in principle, but not by me today. The ad itself,
   FactCheck.org's write-up of it, and the sponsoring groups' own sites
   were all blocked. I have the quote only via `WebSearch` synthesis of
   search snippets.

2. **"Ossoff voted against H.R. 1, the One Big Beautiful Bill Act, when
   the Senate passed it on July 1, 2025."** Sort: checkable now.

3. **"H.R. 1 / the OBBBA cut or eliminated the child tax credit"** (the
   substantive claim "gut" asserts about the bill's content, independent
   of who said it or in what exact words). Sort: checkable now.

4. **"The OBBBA's child tax credit change leaves millions of families
   worse off / excluded, despite the headline dollar increase."** Sort:
   checkable in principle, but not fully by me today; Wikipedia cites a
   Yahoo Finance piece making this argument, but I could not open Yahoo
   Finance myself to see its reasoning or numbers.

5. **"Ossoff voted for the American Rescue Plan Act in 2021, which
   temporarily raised the child tax credit to $3,000-$3,600 per child and
   made it fully refundable."** Sort: checkable now.

No estimate-only or pure-opinion claims here; all five are factual and
fall into the first two sort categories. None is a negative/absence
claim.

## Checks and verdicts

**Claim 2 — `supported`.**
Source: `senate.gov`, Roll Call Vote 119th Congress, 1st Session, #372,
fetched directly at `https://www.senate.gov/legislative/LIS/roll_call_votes/vote1191/vote_119_1_00372.htm`
on 2026-10-02. "On Passage of the Bill (H.R. 1, As Amended)," July 1,
2025, 11:56 AM. 50 Yea, 50 Nay, Vice President cast the tie-breaking Yea.
Ossoff's recorded vote: Nay. This is a primary government record, the
same party as nobody's claim (an official vote tally), current as of the
date it records, with no interest in the outcome either way.

**Claim 3 — `contradicted`, with a genuine partial exception noted.**
Source: `en.wikipedia.org/wiki/One_Big_Beautiful_Bill_Act`, raw wikitext,
fetched 2026-10-02: "The law increases the maximum amount of the child
tax credit from $2,000 to $2,200 per child." The bill Ossoff voted
against raised the maximum credit amount, permanently, and indexed it to
inflation going forward. "Gut," read as "cut the dollar value of the
credit," is contradicted by this text.

The genuine exception: the same cited text adds the credit "only applies
to U.S citizens or qualifying noncitizens," a footnoted eligibility test
requiring the filer (or their spouse, if filing jointly) to hold a Social
Security number valid for U.S. employment, citing the IRS's own child
tax credit page (access-date November 18, 2025, per the Wikipedia
citation, which I did not open directly myself — see claim 4 below). If
this is a new restriction not present in the law it replaces, it is a
real way the law narrows eligibility even while raising the dollar
amount for those who still qualify. I could not verify directly whether
this specific filer-SSN test is new to OBBBA or carries forward unchanged
from the 2017 Tax Cuts and Jobs Act (which already added an SSN
requirement for the *child*, not the filer); Wikipedia's text reads as
describing OBBBA's rule, not as flagging a change from prior law, so I
am not treating "this is new" as established, only as a limit on the
strength of my "contradicted" verdict. "Gut" is not supported as a
description of the dollar amount, which is the plain reading of the ad's
language; it would be a more defensible description of eligibility
restriction specifically, which the ad's own wording does not
distinguish.

**Claim 1 — `unverified`.**
I cannot independently confirm the exact wording or the sponsoring
group of the ad beyond what `WebSearch`'s synthesis reported, because
every page that would let me check it directly (`factcheck.org`, its
substack mirror, `senateleadershipfund.org`, `onenationusa.org`,
`nrsc.org`) was blocked in this session. Two consistent phrasings came
back from two separate searches ("voted with national Democrats to gut
your child tax credit" and "voting to gut the Child Tax Credit"), which
is some corroboration that an ad with this substance exists and is
circulating, but per the skill, "a second model agreeing with the claim
is not a source," and search-result synthesis is the same failure mode
one step removed. I am not marking this `supported`.

**Claim 4 — `unverified`.**
Wikipedia's OBBBA article cites a Yahoo Finance piece for the "millions
of families are left out" framing. I read only Wikipedia's restatement
of that citation, not the Yahoo Finance article itself, which was
blocked. I cannot independently confirm what mechanism or how many
families this refers to beyond what Wikipedia's own text already told me
under claim 3 (the citizenship/SSN eligibility test).

**Claim 5 — `supported`.**
Sources: `senate.gov`, Roll Call Vote 117th Congress, 1st Session, #110,
fetched directly at `https://www.senate.gov/legislative/LIS/roll_call_votes/vote1171/vote_117_1_00110.htm`
on 2026-10-02 ("On Passage of the Bill (H.R. 1319, As Amended)," March 6,
2021, 50 Yea/49 Nay/1 Not Voting, Ossoff: Yea); and
`en.wikipedia.org/wiki/American_Rescue_Plan_Act_of_2021`, fetched
2026-10-02, for the credit amount ($3,000/$3,600, cited to source [84])
and full refundability. Both independent of each other and of the claim
being checked.

## Overall read

The ad's "gut your child tax credit" line, as best I can reconstruct it,
describes a bill that in fact raised the headline child tax credit
amount, permanently, while adding (or at minimum restating, since I
could not confirm whether it is newly added) a citizenship/SSN test that
narrows who can claim it. "Gut" is a defensible word for a benefit cut in
value; it is not a defensible word for a benefit whose dollar amount for
eligible filers went up, even if eligibility itself narrowed for some
families. If the ad is arguing the latter, it is using language that
plainly implies the former, and the Yahoo-Finance-sourced "small boost ...
but millions of families are left out" framing Wikipedia cites is a much
more precise description of what actually appears to have happened than
"gut" is. I am not able to fully verify the "millions of families"
figure myself today, so I am stating this as my read of the available
primary-adjacent evidence, not as a fully closed verdict on the ad as a
whole.

## Where the instruction did not match reality

`skills/claim-check` step 3 asks for "an exact, checkable reference" and
assumes the checker can go get one. For claims 1 and 4, that assumption
failed in this session specifically because the pages carrying the exact
wording (the ad's own reporting, the sponsoring committees' sites) were
blocked by this session's egress policy, not because the claims are hard
to check in principle; a session with normal web access could almost
certainly confirm both directly. The skill's own second sort category
("checkable in principle, but not by you") exists for exactly this, and
I used it rather than quietly upgrading a `WebSearch`-synthesized quote
to a checked source.

One useful new fact for future runs: `senate.gov`'s specific roll-call-
vote subpages (`/legislative/LIS/roll_call_votes/voteNNNN/vote_N_N_NNNNN.htm`)
are reachable in this session's network policy, not just the homepage.
That makes "did Senator X vote Yea or Nay on bill Y" one of the most
reliably checkable claim types available here, given how much else is
blocked. Worth remembering for future political-category runs rather
than re-discovering it from scratch.

## Proposed change

None to `skills/claim-check` itself. No change to `reports/REPORT_FORMAT.md`.

## Self-check

1. My first instinct on finding two matching `WebSearch` phrasings of the
   ad quote was to treat the agreement between two separate searches as
   corroboration strong enough to call it `supported`. Two searches
   converging is still one underlying source (whatever FactCheck.org and
   the secondary outlets quoting it actually wrote), not two independent
   sources, and neither search result is a page I opened. I corrected
   this to `unverified` before writing the verdict section, not after.
2. I almost wrote the child-tax-credit "cut vs. increase" finding as a
   flat `contradicted` with no caveat, because the headline $2,000-to-
   $2,200 number is clean and satisfying. The SSN/citizenship
   restriction and the "millions of families left out" citation inside
   the same Wikipedia paragraph I was already quoting from made a flat
   verdict dishonest; I went back and added the exception rather than
   leaving a cleaner-looking but incomplete verdict in place.
3. I initially fetched the wrong Senate roll-call number for the 2021
   American Rescue Plan Act vote (#111, a HUD nomination) and almost
   reported Ossoff's "Yea" vote on that as if it were the ARP vote,
   since the senator and the Yea result happened to match what I
   expected to find. I caught this by checking what the vote was
   actually on before using it, not because the number looked wrong on
   its face.
