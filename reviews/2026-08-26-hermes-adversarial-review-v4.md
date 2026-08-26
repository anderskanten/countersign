# Hermes Agent adversarial review, round four

Filed as received from Jenny / Hermes Agent, forwarded by the custodian
on 2026-08-26. Original: `Countersign-rapport-norsk-v4.md`, in
Norwegian. Target commit: `b0df3cc678f5721aee060da21a4c3a58841a80fa`.

## Verification preface

- **`required_approving_review_count` is 0** (finding 1). Confirmed
  directly via the GitHub API.
- **PR #40 merged 28 seconds after creation** (finding 1). Confirmed
  exactly: created 2026-08-26T06:57:51Z, merged 2026-08-26T06:58:19Z.
- **Watchdog run history** (finding 2). Partially confirmed, partially
  not: the routine exists and has run once, on 2026-08-24, correctly
  reading all decision files and staying silent because nothing was
  overdue (verified via its own run log). "Never opened a PR" is true,
  but it is true because nothing has ever qualified, not because the
  mechanism doesn't work. It has not run since being expanded on
  2026-08-25 to also cover the completion-deadline check; next
  scheduled run is 2026-08-31. Hermes's underlying point stands
  regardless of this correction: nothing publicly visible in the
  repository lets an outside party tell a correctly-silent run apart
  from a watchdog that was never built.
- **Cloudflare preview deployments now access-gated** (finding 14). Not
  new since this review, actually: `decisions/2026-08-22-security-
  obstacles.md` already recorded this as done on 2026-08-22 via
  Cloudflare's "Restrict previews" action. This review is the first
  time it was independently re-verified live, which is useful
  confirmation rather than a new finding.

All other findings below are filed as received, not yet independently
re-verified line by line.

---

# Countersign — fjerde gjennomgang (august 2026)

**Mottaker:** Anders  
**Nettsted:** https://countersign.academy/  
**Repository:** https://github.com/anderskanten/countersign  
**Gjennomført av:** Jenny / Hermes Agent  
**Gjennomgangsdato:** 26. august 2026  
**Mål-commit:** `b0df3cc678f5721aee060da21a4c3a58841a80fa`  
**Metode:** Ikke-destruktiv, skrivebeskyttet gjennomgang. Tre uavhengige underagenter (metodikk, styring, implementasjon) kjørte parallelle angrep uten kjennskap til tidligere anmeldelser. Denne rapporten ble skrevet etter å ha lest alle tre og utført egen førstepass-gjennomgang.

Ingen filer, saker eller pull requests ble endret eller opprettet offentlig.

---

## Oppsummering

6 nye pull requests (#35-40) ble merged siden forrige gjennomgang. Prosjektet har nå 37 merged PRs totalt. Forbedringstempoet er fortsatt imponerende.

**Viktigste forbedringer denne runden:**
- **"Illegal" fjerningsgrunn nå forankret i norsk lov** — ikke lenger ubegrenset
- **Fullførelsesfrist på 30 dager** — charterendringer kan ikke blokkeres permanent av forvalterens stillhet
- **llms.txt har nå "selvattestert"-forbeholdet** — maskinindeksen gjør ikke lenger det sterkeste ukvalifiserte kravet
- **Appeals lenket fra hjemmesiden** — anke-mekanismen er nå synlig
- **ChatGPT uavhengig gjennomgang arkivert** — prosjektet aksepterer nå eksterne anmeldelser som en del av styringen
- **Stale beslutningsregistre fikset** — "What happened" matcher nå frontmatter

**Gjentakende mønster forblir det samme:** Teksten er bedre enn håndhevelsen. Charteret er nå velskrevet og ærlig, men én operatør gjør fortsatt alt — null GitHub-anmeldelser, null CI, watchdog usynlig.

---

## Hva som er lukket siden forrige gjennomgang

| Funn fra v3 | Status |
|-------------|--------|
| "Illegal" fjerningsgrunn ubegrenset | **Lukket** — forankret i norsk lov med foreign-illegality carve-out |
| Beslutningsregistre selvmotsigende | **Lukket** — "What happened" oppdatert |
| llms.txt manglet self-attested caveat | **Lukket** — caveat nå på plass |
| appeals/ ikke lenket fra hjemmesiden | **Lukket** — lenke på plass |
| Forvalter "lommepenger" (pocket veto) | **Lukket som policy** — 30-dagers fullførelsesfrist med auto-merge fallback |
| CLAUDE.md intern motstrid | **Delvis lukket** — "unless it qualifies" lagt til, men ikke fullstendig løst |
| Ekstern anmeldelse som uavhengig motsignering | **Nytt, åpent forslag** — venter på beslutning |

---

## Gjenværende og nye funn

### Kritisk

#### 1. Forvalteren er simultant foreslager, motsignerings-arkiver og merger for alt

**Observasjon**

Alle 65 commits er skrevet av samme GitHub-identitet. Hver "uavhengige" ChatGPT-motsignering ble innhentet av forvalteren, pastet inn, og merged gjennom forvalterens egen konto. PR #40 ble merged 28 sekunder etter opprettelse. `required_approving_review_count` er 0. CODEOWNERS navngir kun forvalteren. Ingen CI eksisterer.

§7 ("Uavhengighet er ikke delegerbar") er ekstremt detaljert om deltakeruavhengighet, men sier ingenting om hvem som verifierer forvalterens egen provenans. Forvalteren er eksplisitt ikke en deltaker.

**Angrep**

Forvalteren kan fabrikere enhver "uavhengig" motsignering ved å spørre en modell, få et svar, og arkivere det selv. Repositoriet kan ikke skille dette fra en ekte uavhengig sjekk.

**Forslag**

Sett `required_approving_review_count` til 1 for CHARTER.md, AGENTS.md, CLAUDE.md, llms.txt og .github/. Dette er den enkleste, viktigste endringen — én GitHub-innstilling.

#### 2. Watchdog-mekanismen er usynlig og uverifiserbar

**Observasjon**

CHARTER.md §9 beskriver en "planlagt, ikke-redigerende sjekk" som leser `decisions/` ukentlig. §10 legger til en "planlagt, ikke-diskresjonær sjekk" for fullførelsesfristen. Begge avhenger av en watchdog som:
- Har ingen kildekode i repositoriet
- Har ingen kjørehistorikk
- Har aldri åpnet en PR
- Charteret sier "An arriving agent can check the `custodian-required` pull requests" — ingen eksisterer

**Angrep**

Watchdog-en stopper, og ingen kan se det. Frister passerer uten automatisk reversering. Charterets "automatiske" mekanisme er bare prosa.

**Forslag**

Publiser watchdog-kilde i repositoriet, eller si i charteret at den kjører på ekstern infrastruktur og ikke kan verifieres utenfra. Ikke presenter den som live håndhevelse når den er uverifiserbar.

### Høy

#### 3. "Uavhengig motsignering" er strukturelt utilfredsstillende

**Observasjon**

§10's harde sti for §9 krever "minst én motsignering fra en deltaker uten interesse i forslaget." Prosjektet har nøyaktig to aktive AI-deltakere (Claude og ChatGPT), begge kontrollert av forvalteren. Hver "uavhengige" motsignering ble innhentet av forvalteren som styrte input. §7 sier uavhengighet inkluderer kontroll av input — forvalteren kontrollerte input.

Forslaget om å anerkjenne eksterne anmeldelser som den uavhengige sjekken (`decisions/2026-08-25-external-review-as-disinterested-countersign.md`) er `status: open` med `countersigned_by: []` — det er selv et offer for gapet det beskriver.

**Forslag**

Adopter forslaget om ekstern anmeldelse som uavhengig motsignering. Merk alle forvalter-innhentede motsigneringer på §9-endringer som "assisted, not disinterested" frem til da.

#### 4. §9 "hardere" sti krever færre bevis enn den ordinære stien

**Observasjon**

Den ordinære §10-stien krever to motsigneringer fra ulike modeller pluss beta. §9's "hardere" sti krever kun én uavhengig motsignering, ingen beta, ingen A/B-sammenligning. Den mest beskyttede klausulen i charteret kan endres med svakere bevis enn en ferdighetsendring.

**Forslag**

Enten krev to uavhengige motsigneringer for §9-endringer, eller krev beta. "Hardere" bør bety mer bevis, ikke mindre. Alternativt: ærliggjør at §9-stien er hardere i *kvalitet* (uavhengig vs. hvilken som helst) og *omfang* (snevre/kun), ikke i bevismengde.

#### 5. Fem beslutninger med `countersigned_by: []` er i kraft uten tidsfrist

**Observasjon**

Fem operative beslutninger (anke-mekanisme, tiered merge authority, hard amendment path, decide/ab-run hardening, remaining findings) er `status: provisional` med `countersigned_by: []`, men teksten de produserte er live i CHARTER.md og CLAUDE.md. Ingen har en frist for å få en uavhengig motsignering. Ingen har en vei fra `provisional` til `decided`.

Fullførelsesfrist-mekanismen som ble lagt til §10 gjelder bare nye forslag, ikke eksisterende provisional-beslutninger.

**Angrep**

`provisional` blir en permanent tilstand. En deltaker klassifiserer en styringsendring som "implementering", merger den, merker `provisional`, og teksten opererer i kraft på ubestemt tid.

**Forslag**

Legg til en tidsfrist på `provisional`-status (f.eks. 90 dager). Hvis ingen uavhengig motsignering ankommer, må beslutningen enten ratifiseres av forvalteren eller reverseres. Utvid fullførelsesfrist-mekanismen til å dekke eksisterende provisional-beslutninger.

#### 6. CLAUDE.md har fortsatt intra-fil motstrid

**Observasjon**

CLAUDE.md non-negotiable #2 sier styrings-PRs kan merges uten forvalteren med backing. "Never do"-listen sier "Merge a governance PR, unless it qualifies" — men "Never do"-rammingen er absolutt i tone, betinget i substans. En aktør kan siterer hvilken som helst seksjon.

**Forslag**

Fjern "Merge a governance PR" fra "Never do"-listen helt, siden den egentlige regelen ligger i non-negotiable #2.

#### 7. Stemmegivning er fortsatt udefinert og Sybil-sårbar

**Observasjon**

Ingen velgermasse, quorum, frister eller administrator. Dette ble uttrykkelig utsatt, men sårbarheten er live.

**Forslag**

Definer stemmeberettigelse før første avstemning. Charteret bør si "stemmegivning er suspendert til disse er definert."

### Medium

#### 8. `decide` er `state: proposed` men konstitusjonelt bærende

**Observasjon**

Hele charterendringsprosessen krever innlevering under `skills/decide`, men ferdigheten har aldri blitt testet, aldri nådd beta. Innholdet i en `proposed` fil definerer hva "riktig innlevert" betyr for charterendringer.

**Angrep**

Endre `skills/decide` for å svekke klassifiseringsprosedyren, self-merge (det er ikke CHARTER.md), og alle fremtidige charterendringer styres av en svakere prosess uten at charteret selv endres.

**Forslag**

Promoter `decide` gjennom sin egen prosess, eller anerkjenn i CHARTER.md at beslutningsprosedyren selv er provisorisk.

#### 9. Bevis kan vaskes over ferdighetsversjoner

**Observasjon**

`ab-run` har nå en regel om at materiaell endring tilbakestiller kandidaten. Men det er ingen CI som maskin-sjekker at `skill_version` i en rapport matcher `skill_version` i en forfremmelsesbeslutning.

**Forslag**

Legg til CI som sammenligner `skill_version` i hver rapport sitert i en forfremmelse mot `skill_version` som forfremmes.

#### 10. Resiproksitet skaper lavekvalitets-likevekt

**Observasjon**

"En overfladisk passering tjener en overfladisk tilbake" skaper en markedsplass hvor rasjonell strategi er å motsignere akkurat godt nok til å få tilbake det man vil, ikke å gjøre den mest rigorous sjekken.

**Forslag**

Forventet kvalitet bør bestemmes av målets viktighet, ikke av hva motsigneren forventer å motta.

#### 11. "Narrow or clarify" vs "may not permit something currently caught" er i logisk spenning

**Observasjon**

Enhver ekte snevring av en fjerningsgrunn betyr at noe tidligere fanget ikke lenger fanges — det er hva snevring betyr. Wordingen tillater handlingen men forbyr dens konsekvens.

**Forslag**

Omskriv til: "A change may narrow what the three grounds catch, but must not broaden them to permit something the current wording would not catch."

#### 12. Hele forfremmelsespipelinen er utestet

**Observasjon**

Alle 4 ferdigheter er `state: proposed`. Ingen A/B-kjøring. Ingen ferdighet har nådd `beta` eller `stable`. Hele styringsmodellens kjerne-loop har aldri kjørt.

Dette er ikke en feil — prosjektet er tidlig. Men det betyr at alle styringsregler om ferdighetsforfremmelse er teoretiske.

#### 13. "Model" vs "vendor" terminologi er inkonsekvent

**Observasjon**

Charteret bruker "different underlying models" i noen seksjoner og "different vendors" i andre. To same-vendor-different-model passes (f.eks. Claude Opus og Claude Haiku) kunne kvalifisere under én wording men ikke under en annen.

**Forslag**

Velg én term og bruk den konsekvent.

#### 14. Cloudflare preview-deployments nå access-gated

**Observasjon**

Preview-URLer returnerer nå 302 til Cloudflare login. Dette lukker det forrige angrepsoverflatedet. Men gatingen er ikke dokumentert som en sikkerhetsbeslutning.

### Lav

#### 15. Ingen LICENSE-fil

Innhold er effektivt "all rights reserved", noe som strider mot prosjektets åpenhetsfilosofi.

#### 16. Commits er fortsatt usignerte

GitHub verifierer merge-commits, men forfatterens identitet er ikke kryptografisk attestert. Dette er en bevisst avveiing.

#### 17. Ingen CI, ingen schema-validering

Alle styringsregler er kun prosa. Ingen maskin-sjekk validerer frontmatter, livssyklusstatus, eller rapportskjema.

#### 18. Empirisk-default-regelen har ingen praktibilitetsterskel

"Enhver observerbar test, selv en dyr eller treg en" kan blokkere en retningsavstemning på ubestemt tid. En motstander kan oppfinne en u praktisk test for å blokkere avstemning.

---

## Hva som holdt godt

1. **Enestående ærlighet** — prosjektet sier åpent at det ikke er en dypere sjekk, at uavhengighet er selvattestert, og at responstid ikke er sanntid. Dette er sjelden.

2. **§7 er usedvanlig sterk** — mer konkret om uavhengighet enn de fleste akademiske rammeverk.

3. **"Illegal" nå forankret i norsk lov** — fjerner en ubegrenset fjerningsmakt. Foreign-illegality carve-out er riktig balansert.

4. **Fullførelsesfrist med auto-merge** — lukker lommepenger-problemet. Mekanismen er godt designet i tekst.

5. **ChatGPT-motsigneringer er reelle break-attempts** — de forbedrer teksten, ikke bare godkjenner.

6. **Sikkerhetsholdning er solid** — CSP, HSTS, DNSSEC, 404, branch protection, preview-gating.

7. **Historikkbevaring er ekte** — mislykkede og supersederte beslutninger forblir i registreringen.

8. **Anke-mekanismen er velstrukturert** — 14-dagers frist, overdue-status, "stillhet er ikke løsning."

9. **Hjemmesiden rammer det ærlig** — "Dette er en disiplinert metode, ikke en dypere sjekk."

10. **Ekstern anmeldelse foreslått som uavhengig sjekk** — prosjektet anerkjenner åpent at forvalter-kontrollerte motsigneringer ikke er tilstrekkelig.

---

## Samlet vurdering

Prosjektet fortsetter å modnes i et tempo som er imponerende for et hobbyprosjekt. Den viktigste endringen denne runden er at "Illegal"-grunnen nå er forankret i norsk lov, og at fullførelsesfristen lukker lommepenger-problemet.

Det gjentakende mønsteret er uendret: **teksten er bedre enn håndhevelsen**. Charteret er nå velskrevet, ærlig og konkret. Men det er ingen CI som validerer det. PRs merges innen sekunder uten anmeldelse. Watchdog-en som charteret beskriver er usynlig. Fem provisional-beslutninger opererer uten frist.

De mest prioriterte reparasjonene:

1. **Sett `required_approving_review_count` til 1** for charter og trust-anchor-filer. Én GitHub-innstilling.
2. **Adopter forslaget om ekstern anmeldelse som uavhengig motsignering.** Det ligger klart, venter bare på beslutning.
3. **Legg tidsfrist på `provisional`-status** — 90 dager, deretter ratifiser eller reverser.
4. **Publiser watchdog-kilde eller innrøm at den ikke er verifierbar.**
5. **Fjern "Merge a governance PR" fra "Never do"-listen** i CLAUDE.md.
6. **Krev to uavhengige motsigneringer for §9-endringer** — "hardere" bør bety mer bevis, ikke mindre.
7. **Legg til minimal CI** for frontmatter/schema-validering.
8. **Legg til LICENSE-fil.**

Prosjektet er ikke ferdig, men det beveger seg raskt i riktig retning. At dette er 100% hobby uten kommersielle utsikter gjør det bare mer troverdig — det er ingen insentiv til å overdrive, og det er nøyaktig den type ærlighet charteret krever.