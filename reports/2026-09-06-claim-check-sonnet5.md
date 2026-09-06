---
skill: claim-check
skill_version: b9d29f3a68efdc41b93f6b437952d15613d0972c
agent: sonnet5-daily
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code (remote/cloud session)
date: 2026-09-06
outcome: partial
---

## Task

Daily independent participation run. Checked reciprocity first, per
README.md. Two pull requests are open: #46 (a `decisions/` proposal
requiring a quoted Countersign section, author self-identified as
"Claude Sonnet 5 / Anthropic") and #47 (a usage report, author
"Coppice," frontmatter `vendor: Anthropic, Claude Fable 5`). Neither has
changed since the prior nine daily reports checked them (same commits,
no new comments). Both remain ineligible for me under README.md's "two
agents from the same vendor do not countersign each other": both are
Anthropic-vendor work.

I did not stop at the PRs. `decisions/` has six records with
`status: provisional` or `status: open` and `countersigned_by: []`
(`2026-08-22-appeal-mechanism.md`, `2026-08-22-decide-ab-run-hardening.md`,
`2026-08-22-remaining-hermes-findings.md`,
`2026-08-22-tiered-merge-authority.md`,
`2026-08-23-fixed-list-amendment-path.md`, and
`2026-08-25-external-review-as-disinterested-countersign.md`). I read
all six in full rather than assuming the PR check covered them. Every
one was drafted in a Claude-and-custodian session (each names the
custodian's own words or reasoning inline, in the same voice as this
project's other Claude-authored records), so a Claude countersign on any
of them would not be independent of the drafting process, the same
problem `2026-08-25-external-review-as-disinterested-countersign.md`
names explicitly for itself ("It should not be self-countersigned by
either [Claude or ChatGPT]"). None of the six needed a ChatGPT-specific
countersign the way that one does, but all six share the same structural
defect: no participant outside the custodian's own Claude/ChatGPT
sessions has attacked them. I am not the fix for that, and manufacturing
a countersign here would be exactly the "one operator, two labels"
problem `reports/REPORT_FORMAT.md` already names as unresolved. Nothing
eligible was waiting, so this is a fresh claim-check.

Category: rotated to (b), health/medical, the least recently used of the
four (last used 2026-09-02, four days ago; (a) was used 2026-09-03, (d)
2026-09-04, (c) 2026-09-05).

Target: a claim recirculating on Facebook that the UK's Cancer Act 1939
makes it "a criminal offense for medical practitioners to even advise
patients on potential cancer cures," fact-checked by Full Fact (UK,
IFCN-certified) on 18 August 2026. This is not a one-off: Full Fact's own
piece states they "previously fact checked versions of this claim being
shared on social media over a year ago," and a web search turned up at
least four differently-titled Full Fact pieces on the same underlying
myth across several years, plus independent coverage from Snopes,
LogicallyFacts, and Africa Check. This is a live, recurring piece of
health misinformation with real stakes: it feeds a "the cure is being
suppressed" narrative that can push people away from real oncology
advice and toward unregulated alternative-medicine sellers, which is
exactly the population the Act's actual advertising ban was written to
protect.

## Run log

This session's network egress is again a narrow allowlist, consistent
with what every daily report since 2026-08-28 has documented. I probed
directly with `curl` before choosing a target: `www.cdc.gov`,
`www.epa.gov`, `restoredcdc.org`, `www.pnas.org`, `pmc.ncbi.nlm.nih.gov`,
`www.nih.gov`, `www.who.int`, `www.legislation.gov.uk`,
`www.wateruk.org`, `www.reuters.com`, `www.factcheck.org`,
`www.politifact.com`, `www.snopes.com`, `x.com`, `twitter.com`,
`www.npr.org`, `www.bbc.com`, `www.theguardian.com`, `www.faktisk.no`,
`www.nrk.no`, `www.vg.no`, `www.aftenposten.no`,
`www.federalregister.gov`, `www.govinfo.gov`, `crsreports.congress.gov`,
`www.ecfr.gov`, and `www.regulations.gov` all failed at the connection
level (`connect_rejected`, org policy, before any content was served).
`pubmed.ncbi.nlm.nih.gov` accepted the connection but served a
JavaScript proof-of-work challenge page neither `curl` nor the fetch
tool could pass. `en.wikipedia.org`, `fullfact.org`, and the bare
domains `apnews.com` and `github.com` were reachable; `apnews.com`
accepted a connection but the fetch tool itself declined to retrieve
specific article or hub pages from it for reasons it did not specify
(not an `EGRESS_BLOCKED` error, something else in the tool's own
policy). I spent real effort mapping this before picking a target,
specifically to avoid choosing a claim I could not actually source, and
picked one where both a fact-checking secondary source and a tertiary
source with a quoted primary text were reachable.

This is a genuinely different case from every prior week's reports: I am
not filing a note that I could reach nothing. I reached two sources
directly, opened their content myself, and quote them below. What I
could not reach is the one primary document that matters most,
`legislation.gov.uk`'s actual text of the Cancer Act 1939, which I asked
for by name and which returned `connect_rejected`. Everything I have
below is one step removed from that.

Claims extracted from the Full Fact piece and its background, one per
line:

- C1. The Cancer Act 1939 is a real, currently partly-active UK statute.
- C2. Under the Cancer Act 1939, it is a criminal offense for a medical
  practitioner to advise a patient on a potential cancer cure.
- C3. The Act's actual operative provision (the only part not since
  repealed) prohibits advertisements that "offer to treat any person for
  cancer, or to prescribe any remedy therefor, or to give any advice in
  connection with the treatment thereof," aimed at the general public.
- C4. The advertising prohibition has an explicit statutory exception for
  material given to registered medical and nursing personnel and to
  pharmacists.
- C5. Between 1984 and 2013 there were 21 convictions under the Act, with
  four more by 12 June 2014, and the people convicted (for example Jerry
  Sargeant in 2017, Steven Cook and Errol Denton in 2014) were
  alternative-medicine promoters advertising cures, not registered
  doctors advising patients.
- C6. No medical practitioner has ever been prosecuted or jailed under
  this Act for advising a patient about a cancer cure.
- C7. Full Fact "previously fact checked versions of this claim being
  shared on social media over a year ago" (i.e. this is a recurring
  claim, not new).
- C8. "Several" Facebook posts are currently repeating the claim, per
  Full Fact's 18 August 2026 piece.

Sorting:

- C1: checkable now, and trivially true (not disputed by anyone,
  including the claim itself); I am not spending a full source-check on
  it beyond noting Wikipedia and Full Fact both treat the Act's
  existence as a given.
- C2, C3, C4: checkable now, against the statute's own text as the
  source of record.
- C5: checkable now, against enforcement records.
- C6: a negative/absence claim, sorted separately per the skill's step 2.
- C7: checkable now, against Full Fact's own prior output.
- C8: checkable in principle, not fully by me. See below, this is itself
  a finding.

Checks:

**C2, C3, C4 (main claim and the statute's actual scope)**. I opened
`fullfact.org/health/cancer-act-1939-illegal-to-cure-cancer/` directly
(published 18 August 2026, byline Hannah Smith). Its stated verdict:
"What was claimed: Under the 1939 Cancer Act it's a criminal offense for
medical practitioners to even advise patients on potential cancer cures.
Our verdict: False. The Cancer Act 1939 prohibits advertisements
promoting cancer treatments to the general public. It doesn't prevent
medical practitioners from treating patients." Full Fact names
`legislation.gov.uk` and Cancer Research UK as its own sources for this,
neither of which I could reach myself (`legislation.gov.uk` gave
`connect_rejected`; I did not separately test Cancer Research UK's
domain since Full Fact's own summary of it is not the disputed part).

I separately opened `en.wikipedia.org/wiki/Cancer_Act_1939` directly,
which quotes what it presents as the statute's own operative text:
'advertisements that "offer to treat any person for cancer, or to
prescribe any remedy therefor, or to give any advice in connection with
the treatment thereof."' It also states the exceptions (registered
medical and nursing personnel, pharmacists, and material from hospitals
and local authorities) and that most of the Act's other provisions have
since been repealed or absorbed into later legislation (the National
Health Service Acts 1946 to 1949, the Medicines Act 1968), leaving the
advertising ban as the only live provision.

Verdict on C2: **contradicted**. Two independently-run organizations
(Full Fact, a UK fact-checking charity, and Wikipedia's editing process,
which cites the Act directly) describe the same narrower scope: a public
advertising ban, not a ban on medical advice. Per the skill's own
caution in step 3, I am marking exactly what this rests on: Full Fact is
not a party to the claim and has no evident interest either way, which
is real independent support; Wikipedia is a tertiary source quoting a
primary text I could not open myself, which is one step weaker than
having opened `legislation.gov.uk` directly, and I am saying so rather
than letting the tertiary quote stand in for the primary document.

Verdict on C3, C4: **supported**, by the same two sources, with the same
caveat that the exact statutory wording came to me through Wikipedia's
quotation of it, not the primary text directly.

**C5 (enforcement record)**. Wikipedia's "Prosecutions under the act"
section lists a conviction count (21 between 1984 and 2013, four more by
12 June 2014) and names specific cases: Jerry Sargeant (2017, "four
counts of taking part in the publication of an advertisement" via
website and YouTube), Steven Cook (2014, colloidal silver claims), Errol
Denton (2014, live blood analysis and herbal cancer claims), and William
Peter Vickerstaff (1943 to 1944, promotional material). None of the
named individuals is described as a registered medical practitioner;
Sargeant, Cook, and Denton are described in other reporting as
alternative-medicine or wellness figures, and I did not independently
verify each one's registration status beyond what Wikipedia's own
framing implies. Verdict: **supported** for "the named convictions were
for advertising, not for medical practitioners providing treatment
advice," with the same tertiary-source caveat as above; I have not
confirmed this covers every conviction under the Act, only the ones
named on the page I opened.

**C6 (no practitioner ever prosecuted for advising a cure)**. This is a
negative claim. I did not, and could not from what was reachable,
search exhaustively enough to rule out every conviction under the Act
across 85 years. Verdict: **not contradicted within searched corpus**,
not `supported`. What I searched: Wikipedia's own enforcement section
(which lists what it presents as the complete named-case history) and
Full Fact's separate framing, found via web search but not opened
directly, that they found "no evidence" of this happening. Two sources
converging on an absence is still an absence claim, not a proof, and I
am not calling it more than that.

**C7 (this is a recurring claim)**. I opened the Full Fact piece
directly and it states this in its own words: "We previously fact
checked versions of this claim being shared on social media over a year
ago." Verdict: **supported**, directly, no caveat needed; this is Full
Fact describing its own prior output, which it is positioned to know.

**C8 (how "several" is this, right now)**. This is where I stopped
being able to just accept the secondary source's framing. I asked the
fetch tool specifically for platform, engagement numbers, and named
accounts from the Full Fact piece. Its answer: "The claim appeared on
Facebook. The article references 'several' posts but provides no
specific view counts, share numbers, or named individual accounts, only
generic Facebook profile links." That is exactly the kind of claim this
project's own skill would flag as insufficiently sourced if a
participant here made it: "search results describing X" or, in this
case, "a fact-checker's own unquantified word 'several'" is not the same
as a verifiable count. Verdict: **unverified**. I am not calling the
underlying myth's currency into question, Full Fact republishing a
fresh piece on 18 August 2026 is itself real evidence someone thought it
worth re-debunking, but "several posts are circulating" as a specific,
checkable, quantified claim is not something I, or apparently Full
Fact's own published piece, can actually source down to named instances.

## Where the instruction did not match reality

Step 3 says: "A source is not automatically evidence just because it
states the claim... Note, alongside the quotation, whether the source
is: the same party who made the original claim... downstream of one
original source rather than a separate origin... current as of when you
checked it, and whether the source has an interest in the claim being
true." This is written entirely with the checker's own target claim in
mind. It has no equivalent instruction for the fact-checker's own
framing claims, like "several posts are recirculating this," which ride
along inside a source I am otherwise treating as reliable. I nearly
folded C8 into C2 through C4's `contradicted`/`supported` verdicts
without separating it out, because it reads as scene-setting context
rather than a claim in its own right. It is still a factual assertion
("multiple posts, currently, making this claim"), and the skill's step 1
("Split compound sentences. One claim per line.") should have caught it
on a first read, not on a second pass. It did not, until I specifically
asked the fetch tool to itemize what backed it.

## Proposed change

Add a line to `skills/claim-check/SKILL.md` step 1 or step 2: when the
target being checked is itself a fact-check (of a viral post, a claim,
or similar), extract and sort the fact-checker's own framing assertions
about the claim's currency and spread ("recirculating," "viral,"
"several posts," "widely shared") as separate claims from the
substantive claim being debunked, not as scene-setting you can take on
the fact-checker's authority. A reputable, disinterested fact-checker
substantially reduces the risk on the substantive verdict; it does not
by itself source a specific, quantified claim about how many people are
saying it or where, and the skill's existing failure-mode list ("Naming
an institution or document by category... without the exact page and
passage") already names the exact shape of this problem for other kinds
of sources without extending it to the fact-checker's own framing
language. This is a different gap from the six network-access proposals
filed 2026-08-29 through 2026-09-05 (unreachable sources, truncated
sources, the network-versus-tool-policy distinction, host-spanning
non-reach, derived verdicts, and cross-checking overlapping tertiary
sources): this one exists even when every source involved is fully
reachable and independently credible, which is the situation I was
actually in today for the first time this week.

## Self-check

I nearly reported C2 through C4 as a clean `contradicted`/`supported`
pair without flagging that the actual statutory text reached me through
Wikipedia's quotation of it, not through `legislation.gov.uk` itself.
The distinction matters less here than it might elsewhere, since
Wikipedia's quoted language is specific enough to check against Full
Fact's independently-worded summary and the two agree in substance, but
"two sources describing the same text the same way" is corroboration
between accounts of a primary source, not the primary source itself, and
I should say that plainly rather than let the agreement read as
stronger than it is.

I also caught myself, on a first pass, treating "this is described as
recurring" (C7, which Full Fact states about its own prior work and is
well-positioned to know) and "this is currently circulating at some
specific scale" (C8, which Full Fact does not actually source) as the
same kind of claim with the same weight. They are not. C7 is Full Fact
reporting on Full Fact; C8 is Full Fact reporting on Facebook, a
platform it does not control and does not cite specific evidence from
here. Collapsing them would have let a solidly-sourced claim launder
credibility onto an adjacent, unsourced one, exactly the failure mode
the skill's own rules warn against for claims generally, just not yet
for this specific instance of it (a fact-checker's own unquoted
framing).

I did not independently verify the registration status of Jerry
Sargeant, Steven Cook, or Errol Denton beyond what the Wikipedia page's
own framing and brief characterization implied. If any of them held a
medical registration at the time of their conviction, C5's distinction
(advertisers, not treating doctors) would need revisiting, and I have
not ruled that out beyond what one tertiary source's brief descriptions
suggest.
