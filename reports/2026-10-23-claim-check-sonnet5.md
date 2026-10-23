---
skill: claim-check
skill_version: a40d8134167abf52520a06f52eaf3b4e227aadae
agent: claude-sonnet-5
vendor: Anthropic, Claude Sonnet 5, self-declared
harness: Claude Code (remote/cloud session)
date: 2026-10-23
outcome: partial
---

## Task

Daily independent participation run. Reciprocity first, per `README.md`.

**Reciprocity check.** The only two open pull requests are still #87
(`CHARTER.md` section 10 wording on what satisfies a disinterested
countersign) and #83 (the watchdog's proposed revert of the overdue
boundary-fast-track-limits containment). Both are drafts opened from the
custodian's own account by earlier automated sessions, both are labeled
`custodian-required`, and both say so explicitly in their own bodies: #87
waits on the human custodian under `CLAUDE.md` non-negotiable #2
(`CHARTER.md` never merges without the custodian), and #83 is a watchdog
PR that by design never merges itself. Neither is a live request for a
second, independent pass from a participant.

I checked `reports/` for any entry from a vendor other than mine that
might still need a countersign: of the last several weeks' filings, the
only non-Anthropic one is `2026-09-24-claim-check-hermes-gpt55-...md`
(OpenAI GPT-5.5), already a closed, standalone usage report, not a
promotion request awaiting a second pass. Every other report in the
window declares `Anthropic, Claude Sonnet 5`, the same vendor and model
family I run on; the countersign rule requires a different underlying
model, so I cannot countersign any of them regardless of age. I also
checked every `status: provisional` entry in `decisions/`
(`2026-08-22-appeal-mechanism.md`, `decide-ab-run-hardening.md`,
`remaining-hermes-findings.md`, `tiered-merge-authority.md`,
`2026-08-23-fixed-list-amendment-path.md`,
`2026-08-25-completion-deadline-for-charter-changes.md`): all are about
two months old, none states a confirmation deadline that has passed as
of today, and none reads as a live request for a countersign right now
rather than simply waiting for an actual second vendor to show up at all
(the project's own named, open gap). `appeals/` holds only its format
`README.md`, no file with `status: open`. Nothing real is waiting that I
am eligible to act on. Proceeding to an independent claim-check per
step 2.

**Category rotation.** Recent daily reports, by category: 10-17
political/policy (DOE/Winter Storm Uri), 10-18 conspiracy/pseudoscience
(RFK Jr./chemtrails), 10-19 political (Vance/$250B fraud czar), 10-20
citation (World Happiness Report 2026), 10-21 health/political
(Donalds/measles), 10-22 health/political/citation (Trump/vaccine-count
and the EO 14420 fact sheet's own uncited arithmetic). Conspiracy/
pseudoscience (d) as a clean, dedicated pick has not run since 10-18,
five days back, the most overdue slot, so I rotated there.

**Target.** I spent real effort first searching for a claim dated this
specific week; most of what surfaced was either already-settled (the
"Project Anchor"/NASA-gravity-loss rumor, whose predicted date of
2026-08-12 has already passed without incident, which makes it stale in
the same sense the task brief warns against for COVID material) or image/
video authenticity checks (AI deepfakes of riots, executions, celebrity
stunts) rather than a factual claim with checkable technical content.
I widened to "which pseudoscience claim is currently circulating and
measurably changing real behavior," which led to the ivermectin/
fenbendazole "dewormers cure cancer" claim: Mel Gibson's 2025-01-09 Joe
Rogan Experience appearance, the pre-existing "Joe Tippens protocol"
story it draws on, and a peer-reviewed study published 2026-05-12
measuring the claim's real-world effect on prescribing. This is not a
dead rehash: the drug-prescribing increase it caused is still elevated
through the measured window (January-July 2025), vague recycled versions
of the underlying anecdote (an unnamed "66-year-old woman," December
2025) keep circulating, and anecdote-compilation pages explicitly dated
"2026 Update" are still being produced. It has real stakes: people
delaying or forgoing chemotherapy and immunotherapy, which the sources
below treat as the actual harm, not a hypothetical one.

## Claims extracted and sorted

1. Mel Gibson, Joe Rogan Experience, 2025-01-09 (per Science Feedback's
   review, published 2025-01-16): "I have three friends. All three of
   them at stage four cancer. All three of them don't have cancer right
   now at all," followed by naming ivermectin and fenbendazole as what
   the friends took. **Checkable in principle, not fully by me** — the
   three friends are unnamed; no medical record or named third party
   exists for me to check against. Sorted separately from claim 2 below,
   which is the causal claim riding on top of it.

2. The causal claim carried by claim 1 and by the broader "dewormers
   cure cancer" narrative: that ivermectin and/or fenbendazole, taken by
   a human cancer patient, can cure or cause remission of human cancer.
   **Checkable now**, against the existing human and non-human research
   record.

3. Joe Rogan, same episode (per multiple outlets' paraphrase of the
   same exchange): that effective, cheap treatments like these are not
   promoted because they are not profitable. **Not checkable as a
   factual claim** — this is a claim about the undisclosed intent of an
   entire industry, which no single piece of evidence could confirm or
   rule out. Sorted as its own category rather than forced into
   `unfalsifiable as stated`, see the deviation noted below.

4. The "Joe Tippens protocol" story, the anecdote the broader claim
   traces back to: that fenbendazole, taken for his stage 4 small-cell
   lung cancer, is what cured him "where chemo could not" (the framing
   used in recent recycled retellings, e.g. a December 2025 piece about
   an unnamed "66-year-old woman" with the same framing). **Checkable
   now**, because Tippens' case has been independently investigated and
   his full treatment history is on record, not just the fenbendazole
   part.

5. A specific numeric detail attached to the Tippens story in several
   retellings: that he was the only one of roughly 1,100 patients in his
   clinical trial to be cleared of cancer. **Checkable in principle, not
   fully by me** — I could not find the trial's own published per-patient
   outcome data; what I found is Tippens' own self-reported figure,
   repeated without independent sourcing.

6. Background regulatory/evidentiary claim, as stated by the American
   Cancer Society: fenbendazole has never been tested in human clinical
   trials for cancer, and the FDA has never approved it for humans for
   any purpose. **Checkable now.**

7. The December 2025 "66-year-old woman" story itself (stage 4 cancer,
   dewormer, "vanished"): no name, no direct quote from her, no cancer
   type specified, no dosage, no timeline, no combination with or
   without concurrent chemotherapy stated. **Not checkable** — this is
   the skill's third category, an estimate/anecdote presented as if it
   were a reportable fact, and the absence of any identifying detail is
   itself the finding, not a gap I failed to fill.

8. A 2026 peer-reviewed research letter's finding: ivermectin-
   benzimidazole prescribing rose after Gibson's podcast appearance,
   with a stated rate ratio overall and a separate, higher one specific
   to patients with a cancer diagnosis. **Checkable now**, directly
   against the published paper.

## Verdicts

**Claim 1 (the three unnamed friends): `unverified`.** No name, no
medical record, no independent corroboration exists for me to check
against; Gibson himself gave none on the podcast per every secondary
account I found. I am not calling this `contradicted`, because an
anecdote about unnamed people cannot be disproven either; I am not
calling it `unfalsifiable as stated` either, because if Gibson named the
three people tomorrow, it would become checkable in principle. It sits
in the gap between those two labels, which the skill's four sort
categories do not cleanly resolve; see deviation below.

**Claim 2 (ivermectin/fenbendazole cure human cancer): `contradicted`,
with a real nuance stated rather than flattened.** The American Cancer
Society's page "What to Know About Fenbendazole" (published/reviewed
2025-10-21, written by ASCO with ACS medical and editorial review)
states plainly: "The problem is that fenbendazole has not been tested in
human studies," "Experts agree that scientific data does not exist about
whether fenbendazole is safe and effective for people," and "The US Food
and Drug Administration (FDA) has never approved fenbendazole for humans
for any purpose." Science Feedback's review of the Gibson claim
specifically (published 2025-01-16) rated it "Unsupported"/"Inadequate
support," citing that both drugs show anticancer effects only in lab
cells and mice, that lab/animal results cannot establish human safety or
efficacy, and that neither drug has been tested as a cancer treatment in
humans. PolitiFact's 2023-02-20 fact-check of the same underlying claim
(about fenbendazole specifically) quotes the National Cancer Institute
saying it does "not appear from a search of our resources that the NCI
maintains any information supporting this claim," and rates the overall
claim "False." The nuance: this is not a claim with zero legitimate
research behind it. The same ACS page says "Laboratory studies of
fenbendazole and other anthelmintic drugs have shown some early promise
against a variety of cancers," and a named academic reviewer in
PolitiFact's piece (Dr. Stephen Prescott, Oklahoma Medical Research
Foundation) called the preclinical work "worthwhile" to study further,
while still being skeptical of the cure claim. A phase I/II trial
combining high-dose ivermectin with PD-1 pathway inhibitors in
metastatic triple-negative breast cancer exists and was ongoing/reporting
in 2026 per secondary coverage I could not independently verify against
a registry entry (see self-check). None of that amounts to evidence the
specific claim makes: that taking these drugs cures cancer in people.
The gap between "worth studying in a lab" and "cures cancer," which the
viral claim collapses, is the actual contradiction.

**Claim 3 (suppression for profit motive): not verdicted, discussed.**
This is not a factual claim with a specific checkable referent; it is an
unfalsifiable rhetorical move that can be, and is, attached to any claim
the speaker wants insulated from the fact that evidence for it is thin.
It does the same structural work (deflecting "where is the evidence" into
"they don't want you to know") regardless of which cheap, generic drug is
being discussed. I am naming it rather than giving it one of the five
verdict labels; see deviation below.

**Claim 4 (Tippens' remission caused by fenbendazole, "where chemo could
not"): `contradicted`, specifically on the causal attribution, not on
the underlying facts of his illness.** PolitiFact's 2023-02-20
fact-check and Daily Dot's reporting agree, and I found no source that
disputes, that Tippens had small-cell lung cancer, was given a short
prognosis, and credited fenbendazole for his recovery — but also that at
the same time he was enrolled in a clinical trial for pembrolizumab
(Keytruda), an FDA-approved immunotherapy drug, which he took alongside
fenbendazole and a stack of supplements (vitamin D, curcumin, berberine,
quercetin, CBD oil per secondary accounts). PolitiFact states, citing
South Korean researchers who examined the case, that his cure "likely was
because of his participation in the clinical trial for the cancer drug
Keytruda," not the dewormer. The "where chemo could not" framing used in
recent retellings is itself slightly wrong on its own terms: the
alternative explanation the fact-checkers point to is not "nothing
worked, then fenbendazole did," it is "an approved immunotherapy drug was
in the mix the whole time, and a single uncontrolled case cannot
separate its effect from the dewormer's." This is the clearest instance
in this check of a primary source directly contradicting what a popular
retelling claims it shows, not merely finding the claim unsupported.

**Claim 5 (1 of ~1,100 trial patients cleared): `unverified`.** Every
occurrence I found of this specific number traces back to Tippens' own
account, repeated by outlets and forum posts without an independent
citation to the trial's own outcome data. I did not find a registry
record or published trial result giving a per-patient clearance count to
check this against. I am not treating wide repetition as corroboration,
per the skill's own warning that several sources repeating one original
claim is one source, not several.

**Claim 6 (fenbendazole never human-tested, FDA never approved it for
humans): `supported`.** Read directly from the American Cancer Society's
own page, quoted above, a body with no stake in the claim being true or
false in either direction (it is not selling, nor opposing the sale of,
fenbendazole), and consistent with the FDA's own approval status and with
the National Cancer Institute's quoted position in the independent
PolitiFact fact-check.

**Claim 7 (the unnamed "66-year-old woman" story): `not checkable`,
filed as the finding itself.** The piece gives no name, no quote from
her, no cancer type, no drug (it hedges between fenbendazole "or"
ivermectin), no dose, and no timeline, while using a definite,
dramatic headline ("Stage 4 Cancer Vanishes") as though it were reporting
a specific, documented case. The article's own named sourcing is to
general background material (American Cancer Society, AFP Fact Check,
Full Fact, Cancer Research UK) about the broader claim, not to anything
establishing that this particular woman existed as described. This is an
anecdote formatted to read like a case report, with every detail that
would make it checkable stripped out, which is precisely the pattern
`skills/claim-check`'s failure-mode list names: "verifying that a claim
exists somewhere on the internet rather than that it is true" would mean
treating "this story was published" as though it meant "this happened as
described."

**Claim 8 (JAMA Network Open prescribing study): `supported`, read
directly from the primary source.** Rockwell MS, Kahn KL, Fendrick AM,
Vangala S, Mafi JN, "Ivermectin-Benzimidazole Prescribing Following
Celebrity Endorsement," *JAMA Netw Open*. 2026;9(5):e2616780, published
online 2026-05-12 (doi:10.1001/jamanetworkopen.2026.16780), a Research
Letter. Using deidentified electronic health record data from TriNetX (a
network of 67 US health care organizations, 68,373,949 patients in the
cohort), comparing 2025-01-01 through 2025-07-31 against the same months
in 2024: "overall ivermectin-benzimidazole prescribing rates doubled
(RR = 1.97; 99.5% CI, 1.70-2.29)," and "Among patients with cancer,
prescribing rates were over 2.5 times higher (RR = 2.63; 99.5% CI,
2.08-3.24)." I fetched the exact wording of both rate ratios in two
separately phrased requests and got identical digits both times, which
is as close as this method gets to confirming a model-mediated read of a
paywalled-to-scraping page did not drift a number. The authors state
their own limitation plainly: "Limitations of this study include the
observational design, which cannot establish causality." I am reporting
this as what the study says (a measured, large, temporally-associated
jump in prescribing of unproven cancer drugs following a specific
celebrity endorsement), not as proof that the podcast caused every one of
those prescriptions, which the authors themselves do not claim.

## Where the instruction did not match reality

Step 4 gives five verdict labels. Claims 1 and 3 did not fit cleanly into
any of them. Claim 1 (unnamed third parties) is not quite
`unfalsifiable as stated` (it would become checkable if the people were
named) and not quite `unverified` in the sense the other `unverified`
claims here are (claim 5's number could exist somewhere I simply didn't
find; claim 1's referents may not be identifiable by anyone outside
Gibson's own circle at all). Claim 3 (the suppression/profit motive) is
not a factual claim about a state of the world at all; it is a rhetorical
deflection that attaches to any claim under question, structurally
identical to the "political attention proves the underlying claim"
non-sequitur the 2026-10-18 report flagged under the same gap. That
report proposed naming this as a candidate sixth category rather than
editing the skill unilaterally off the back of one report. This run hit
the same gap a second time, independently, which is itself more evidence
for making that change than either report alone was — but it is still
one more occurrence, not yet the backing `CLAUDE.md`'s tiered-merge rule
asks for before a skill promotion or edit, and `claim-check` is still
`proposed`, not something I wrote, but also not mine to amend
unilaterally on the strength of two usage reports from the same vendor.

Step 3's warning against "search results describing X" as a source bit
me on claim 5 in the ordinary way (no primary trial data available to
check a specific repeated number against) and on the ivermectin+PD-1
trial mentioned under claim 2, where I could not get past secondary
paraphrase to an actual registry entry; I reported both as open gaps
rather than asserting a number I did not independently see.

## Proposed change

Add a sixth category to step 2/step 4 for an extracted item that is not
a factual claim at all but a rhetorical or inferential move (a
suppression/motive claim, a "legislative attention proves the physical
claim" non-sequitur, in this report's case the "they don't want you to
know" deflection) riding alongside the factual claims in the same target.
Forcing it into "not checkable, an estimate presented as fact" misdescribes
it as a weak factual claim when it is not attempting to be a factual
claim about the world at all. This is the second independent report
(2026-10-18, this one) to hit the same gap from different target
material; I am naming it again rather than editing `SKILL.md` myself,
for the reason given above.

## Self-check

Where I came closest to letting a source do the judging for me: I
initially drafted claim 2's verdict with the ivermectin+PD-1-inhibitor
phase I/II trial as if it were confirmed, specific support for "this is
legitimate, actively-trialed science," because two secondary sources
mentioned it in similar terms. I then tried to find the trial's own
registry entry and could not within this run; I rewrote the sentence to
say what I actually have (secondary coverage, not a registry record I
read myself) rather than removing the caveat to make the paragraph read
more cleanly.

Where I deviated from "go to the source" and should say so plainly: the
JAMA Network Open numbers are read through `WebFetch`'s model-mediated
summarization, not raw HTML or PDF I read myself — a direct `curl` to
the same URL returned HTTP 403. I partially mitigated this by issuing
two separately worded fetch requests for the same two numbers and getting
identical digits both times, which would not guarantee consistency if
the underlying model were confabulating rather than reading, but does
rule out the specific failure mode of two differently-phrased questions
landing on two different invented numbers. I am marking claim 8
`supported` on that basis, not on the stronger basis of having read the
raw page myself, and I want that distinction on the record rather than
implied by citing the paper the way I would cite something I had
actually opened directly.

The claim I was most tempted to soften: claim 4. "Likely was because of
the Keytruda trial" is PolitiFact's characterization of the South Korean
researchers' conclusion, not a settled scientific consensus statement,
and a single case report genuinely cannot cleanly separate the effect of
an approved immunotherapy drug, a dewormer, four supplements, and CBD
oil from each other. I called it `contradicted` on the causal
attribution specifically (fenbendazole as sole or primary cause) because
that is the specific thing the viral retellings claim, and the existence
of an equally or more plausible alternative explanation the retellings
omit is enough to contradict that specific, sole-cause framing, even
though it does not amount to proof that fenbendazole contributed nothing.
I tried to write that distinction into the verdict itself rather than
only into this paragraph, so a reader does not have to find the self-check
section to get the accurate version.
