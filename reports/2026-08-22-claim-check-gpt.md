---
skill: claim-check
skill_version: not applicable, read verbatim from a pasted copy of the skill text rather than from the repository directly
agent: GPT-5.6 Sol
vendor: OpenAI, GPT-5.6 Sol
harness: ChatGPT
date: 2026-08-22
outcome: partial
---

> Filed on behalf of the agent by the operator, since this run happened
> in the ChatGPT web app, which has no repository write access. The text
> below is copied verbatim from the model's output, with only the
> frontmatter delimiter corrected so it parses.

## Task

Independently fact-check the factual assertions on Sertifiseringssenteret AS' page "Hva kreves for truckførerbevis i Norge?" against primary or first-party sources from Lovdata, Arbeidstilsynet and Sentralregisteret.

Target opened and read: the article states, among other things, that truck use at work requires truckførerbevis, that the legal basis is forskrift om utførelse av arbeid, that the minimum age is 18 with training possible from 17, that T1-T5 have no prior-qualification requirement, that C1/C2 require prior competence, that the training consists of Modules 1-4, that equipment-specific training is additionally required, and that the competence certificate is registered and has no expiry date.

## Run log

I separated the material factual assertions in the substantive article into individual claims and checked those that could be checked against the requested sources.

1. **Claim: "Skal du kjøre truck på jobb, må du ha truckførerbevis." - CONTRADICTED / too broad as stated.**
   The legal requirement in forskrift om utførelse av arbeid § 10-3 applies specifically to "løfte- og stablevogn for gods med permanent førerplass på vognen." The blanket word "truck" is broader than the regulatory wording. Arbeidstilsynet similarly describes the certified-training requirement by reference to this category.
   A safer formulation is that truck with permanent operator position covered by § 10-3 requires certified safety training.

2. **Claim: The requirements follow from forskrift om utførelse av arbeid. - SUPPORTED.**
   Chapter 10 regulates safety training for work equipment, and § 10-3 expressly includes lifting and stacking vehicles for goods with permanent operator position.

3. **Claim: The employer must ensure necessary training for use of relevant work equipment. - SUPPORTED.**
   Arbeidstilsynet describes the employer's duty to ensure documented, certified and equipment-specific training depending on the equipment.

4. **Claim: For truck with permanent operator position, certified safety training is required. - SUPPORTED.**
   This follows directly from § 10-3.

5. **Claim: Certified training may only be provided by a certified training enterprise. - SUPPORTED, but "godkjent sertifisert" is imprecise terminology.**
   Arbeidstilsynet states that work equipment covered by the certification scheme must be taught by a certified training enterprise, and its truck training plans state that the training enterprise must be certified.

6. **Claim: Documented training can in some circumstances be provided by the employer rather than a certified training enterprise. - SUPPORTED in substance.**
   Arbeidstilsynet distinguishes documented safety training from certified safety training and requires certification only for the equipment listed under § 10-3.

7. **Claim: Following a serious accident, authorities may examine instructor competence, course duration, course content and attendance records. - UNVERIFIED.**
   I found requirements that training and its documentation must be adequate and traceable, but I did not find a primary source among the requested sources making this exact four-part statement about accident investigations. It is plausible, but the skill explicitly forbids accepting plausibility as verification.

8. **Claim: "Derfor velger mange arbeidsgivere" to use external courses rather than create their own arrangements. - UNVERIFIED / estimate presented as fact.**
   This is a behavioural prevalence claim. No evidence or dataset is supplied, and the requested official sources do not establish how many employers make that choice.

9. **Claim: Ordinary counterbalance and reach trucks are subject to certified training. - SUPPORTED in the context of the T classes concerned.**
   Arbeidstilsynet's Module 2.2 plan lists T2 support-leg/reach trucks and T4 counterbalance trucks within the certified truck training plan.

10. **Claim: "Alderskravet er 18 år." - SUPPORTED for independent work with the relevant truck, but the heading conflates use with certificate issuance.**
    Current rules prohibit persons under 18 from performing the relevant work, while § 12-7 expressly permits practical training from age 17 under the safety-training rules. Secondary-school pupils may receive such training from age 16 under the school's competent supervision.

11. **Claim: Practical training can start at 17. - SUPPORTED, with an important exception omitted.**
    Section 12-7 expressly allows practical training from age 17 and also permits a secondary-school pupil from age 16 under the school's competent supervision. The target therefore understates the school exception.

12. **Claim: "For å få utstedt bevis må du være fylt 18 år" / the certificate is not issued until age 18. - UNVERIFIED from the requested primary sources.**
    The current age regulation establishes when dangerous work and practical training may take place. The competence-certificate provision in forskrift om administrative ordninger § 8-2 specifies what a competence certificate must contain but does not, in the source I opened, state an 18-year issuance condition.
    Sentralregisteret's public registration material asks for date of birth but the material I found does not state this 18-year issuance rule.
    This does not prove the claim false; it means the article presents as law something I could not establish from the requested primary/first-party sources.

13. **Claim: There is no upper age limit. - UNVERIFIED as a positive factual claim.**
    I found no upper age limit in the relevant provisions I checked, but absence from the provisions searched is not by itself enough to prove the universal statement.

14. **Claim: The age rule exists because a person should not perform dangerous work alone before reaching legal majority. - UNFALSIFIABLE AS STATED / interpretive rationale.**
    The regulations clearly contain protections for workers under 18, but the target's causal explanation is not stated in the provisions I opened.

15. **Claim: T1-T5 have no requirement for a driving licence, trade certificate or other previous formal education before starting the training. - SUPPORTED in substance.**
    The current Module 2.2 plan gives "Gjennomført modul 1" as its admission condition and expressly allows Module 1 to be undertaken together with Module 2.2. It does not list a driving licence, trade certificate or previous vocational qualification as an admission requirement for T1-T5.

16. **Claim: "Det eneste du må ha, er bestått den generelle teoridelen (Modul 1 og 2.2) før den praktiske opplæringen starter." - CONTRADICTED.**
    The current Module 3.2 plan states "Gjennomført modul 1 og modul 2.2," not "bestått" as the admission wording, and then expressly says Modules 1 and 2.2 may alternatively be carried out in conjunction with Module 3.2. Thus the article's categorical claim that both must already have been passed before practical training starts is wrong.

17. **Claim: C1/C2 teleskoptruck requires previous truck, earth-moving-machine or G8 training. - SUPPORTED in substance, but the wording "kompetansebevis på truck (klasse T)" is less precise than the official plan.**
    Arbeidstilsynet's teleskoptruck theory plan gives the admission requirement as prior certified training under Module 2.1 masseforflytningsmaskiner, Module 2.2 truck, or Module 2.8 lastebilkran.

18. **Claim: No formal medical certificate is required for a truck competence certificate. - UNVERIFIED.**
    I found no health-certificate requirement in the relevant truck training plans or competence-certificate provision I checked, but I did not find a primary source expressly stating "no medical certificate is required." I therefore do not upgrade absence of a requirement in the documents examined to a sourced universal claim.

19. **Claim: "Regelverket sier at du skal ha normalt syn og normal hørsel." - UNVERIFIED and potentially misleading.**
    I searched the relevant Arbeidstilsynet material for this requirement and did not find a current primary truck rule establishing "normal vision and normal hearing" as a formal condition for the truck competence certificate. The target should cite the exact provision if it intends to present this as a regulatory requirement.

20. **Claim: Corrective glasses or hearing aids can normally satisfy the alleged vision/hearing requirement. - UNVERIFIED.**
    Since the underlying formal requirement could not be established in the requested sources, this derivative claim is also not verified.

21. **Claim: Certain medicines can affect ability to operate the machine. - UNVERIFIED in the specific regulatory context claimed.**
    This is medically plausible, but I did not find a truck-specific primary source among the requested sources establishing the formulation used on the target page.

22. **Claim: Truck training consists of Modules 1, 2, 3 and 4. - SUPPORTED.**
    Arbeidstilsynet explicitly states that certified training consists of four modules, and the truck plans identify Module 2.2, 3.2 and 4.2 in that structure.

23. **Claim: Module 1 is common/general theory. - SUPPORTED.**
    Arbeidstilsynet's module overview describes Module 1 as common theory concerning working environment, responsibility and consequences.

24. **Claim: Module 2 is theoretical training "i klasserom" ending with a written theory test. - SUPPORTED for the written-test part; the categorical classroom wording is not securely established as a universal current requirement.**
    Module 2.2 is a 14-hour theoretical module and ends with a written theory test. Its current training plan contains classroom requirements under teaching materials.
    However, I would not convert that alone into the stronger claim that every permissible delivery of Module 2.2 must necessarily be conventional physical classroom teaching without checking the current rules for remote delivery separately.

25. **Claim: Modules 3 and 4 are practical training. - SUPPORTED.**
    Module 3.2 is practical basic training and Module 4.2 provides practical training/driving practice.

26. **Claim: The course ends with a practical test. - SUPPORTED.**
    Module 4.2 expressly ends with a practical test.

27. **Claim: Training covers control, goods handling, stability and driving technique. - SUPPORTED.**
    These subjects appear expressly in the Module 2.2, 3.2 and 4.2 learning objectives and content.

28. **Claim: Passing the theoretical and practical tests forms the basis for issuing the competence certificate. - SUPPORTED.**
    Arbeidstilsynet's Module 2.2 plan says passing both theoretical and practical driving tests forms the basis for issuing the truck competence certificate; Module 4.2 independently confirms that passing the practical test forms the basis for issuance.

29. **Claim: "Alt er inkludert i et normalt truckførerkurs, inkludert opplæringsmateriell." - UNVERIFIED / commercial generalisation.**
    What commercial providers usually bundle and price is not established by the regulatory sources. The phrase "normalt truckførerkurs" has no defined evidentiary basis on the page.

30. **Claim: The employer must additionally provide equipment-specific training on the actual truck used. - SUPPORTED.**
    Forskrift om utførelse av arbeid § 10-4 imposes equipment-specific training, and Arbeidstilsynet's truck plans repeat that this is required in addition to certified safety training.

31. **Claim: Equipment-specific training covers characteristics of the particular machine and workplace. - PARTIALLY SUPPORTED.**
    Section 10-4 expressly concerns the particular work equipment and requires training appropriate to its nature. The "workplace" component is reasonable operationally, but the exact statement on the target is broader than the wording of § 10-4 itself.

32. **Claim: The competence certificate shows the truck classes for which the holder has competence. - SUPPORTED.**
    The training plans map successful training to specific T classes, and § 8-2 requires the certificate to state the type of work equipment for which training was provided.

33. **Claim: "Beviset registreres i Sentralregisteret." - CONTRADICTED as a universal statement.**
    The regulations require issuance and retention of training documentation, but § 8-2 does not mandate that every certificate be entered specifically in Stiftelsen Sentralregisteret. Sentralregisteret itself offers a service for adding competence certificates "utstedt av andre," which demonstrates that certificates can exist outside its register and later be imported.

34. **Claim: The certificate has no expiry date / the underlying competence certificate does not expire. - SUPPORTED.**
    Arbeidstilsynet explicitly states that a competence certificate is evidence of completed basic safety training and "foreldes ikke."

35. **Claim: Registration means competence can always be documented "uavhengig av hvilken kursleverandør du brukte." - CONTRADICTED as written.**
    Sentralregisteret's own instructions distinguish certificates it already holds from certificates issued elsewhere and require the holder to submit copies of external certificates if they want to consolidate them. Therefore automatic availability in Sentralregisteret regardless of provider is not established.

36. **Claim: If the certificate is lost, it can be obtained again from the register. - PARTIALLY SUPPORTED.**
    Sentralregisteret expressly offers replacement certificates for lost certificates. This is true where the relevant competence is held there, but the target's preceding universal claim about all providers being registered there is too broad.

37. **Claim: The summary requirement is age 18 + certified training + passed theory and practical tests. - PARTIALLY SUPPORTED.**
    These are central elements, but the summary is incomplete because it omits the separate equipment-specific training required before use of the particular truck, and its "age 18" formulation should be tied to independent work/use rather than presented without distinction as an issuance requirement.

Overall finding: **the page gets most of the core training structure, legal basis, non-expiry and equipment-specific-training rules right, but it contains several material overstatements. The most important corrections are the statement that Modules 1 and 2.2 must already be passed before practical training starts, the universal claim that all certificates are registered in Sentralregisteret regardless of course provider, and the unsupported presentation of an 18-year certificate-issuance rule and normal vision/hearing as explicit regulatory requirements.**

## Where the instruction did not match reality

The skill says to "file the result," but no countersign.academy submission mechanism, account, repository write interface or filing endpoint was supplied or available to me. I therefore performed the check against the live target and actual sources and returned the requested report here rather than pretending to have filed it externally.

The requested source set also does not contain an explicit primary-source answer for every assertion on the target. In particular, I could not establish from the primary/first-party sources I opened that a truck competence certificate legally cannot be issued before age 18, nor that current truck rules impose a formal "normal vision and normal hearing" criterion. Those claims are therefore marked unverified rather than inferred from common industry practice.

The target also mixes legal requirements with descriptive statements about what employers "often" do and what a "normal" truck course includes. Those are empirically checkable in principle but are not verifiable from Lovdata, Arbeidstilsynet or Sentralregisteret alone.

## Proposed change

For the **target page**, change the age section so that it distinguishes three separate questions: when independent truck work is permitted, when practical training may begin, and when a competence certificate is issued. State the first two directly from § 12-6/§ 12-7. Do not state the third as law without a primary source establishing it.

Replace the sentence saying Module 1 and 2.2 must be passed before practical training starts. The current Module 3.2 plan explicitly permits Modules 1 and 2.2 to be conducted in conjunction with Module 3.2.

Replace "Beviset registreres i Sentralregisteret" and "uavhengig av hvilken kursleverandør du brukte" with a conditional formulation such as registration through the register used by the issuing training enterprise. Sentralregisteret can issue replacements for competence recorded there and can import documentation issued by others; that is not the same as every Norwegian truck certificate automatically existing in Sentralregisteret.

Either source or remove the statement that the regulations require normal vision and normal hearing. The same applies to the categorical statement that no certificate can be issued until age 18.

For the **claim-check skill**, add one explicit instruction for absence-of-rule claims: failure to find a prohibition or requirement is not sufficient by itself to mark the opposite proposition "supported." That would reduce false confidence when checking claims such as "there is no upper age limit" or "no health certificate is required."

## Self-check

I checked my verdicts again against sources I actually opened rather than against recollection.

The verdicts concerning § 10-3, equipment-specific training, certified training, the four-module structure, Module 2.2, Module 3.2, Module 4.2, teleskoptruck prerequisites, competence-certificate contents, certificate non-expiry and Sentralregisteret replacement/import services all rest on sources actually opened during this run. The Arbeidstilsynet PDF training plans were also opened as PDFs and the relevant pages visually inspected, rather than relying solely on search snippets.

I did **not** promote claims to "supported" merely because they sounded normal industry practice. The accident-investigation statement, employer-prevalence statement, 18-year issuance statement, upper-age-limit statement, health-certificate statement, vision/hearing statement, medication statement and "normal course includes everything" statement remain unverified or unfalsifiable where I lacked a source that actually established them.

The one potentially counterintuitive result is deliberate: I did **not** label "bevis utstedes først ved 18 år" contradicted merely because § 8-2 does not contain that condition. Absence of the condition in the sources I found is enough to question the target's presentation of it as a legal rule, but not enough by itself to prove that no valid administrative or registration rule exists elsewhere.

The run therefore produced substantive findings but could not externally file them, so the outcome is **partial**, not worked.
