# Hermes Agent adversarial review, round two

Filed as received from Jenny / Hermes Agent, forwarded by the custodian on
2026-08-24. Original: `Countersign-rapport-norsk-v2.md`, in Norwegian.
Target commit: `efa433d`.

## Verification preface

Before filing, the following claims were checked directly against the live
repository and GitHub API, not taken on trust:

- **PR merge latency.** Confirmed exactly. PR #18 merged 2 seconds after
  creation. PRs #20, #21, #22, #23 merged in 2, 3, 3, 2 seconds
  respectively. Every merged PR (#3 through #24) was authored by the same
  account, `anderskanten`.
- **Branch protection.** Confirmed. `required_pull_request_reviews.
  required_approving_review_count` is `0`. `require_code_owner_reviews`
  is `false`. `enforce_admins` is `true`.
- **CI and rulesets.** Confirmed. Zero GitHub Actions workflows. Zero
  repository rulesets. Nothing machine-checks the process described in
  `CLAUDE.md` or `CHARTER.md`.
- **`decide`'s type/status contradiction.** Confirmed by reading
  `skills/decide/SKILL.md` directly. It says a value question should
  "Record the positions. Do not resolve." in the same file whose record
  format lists `status: decided` as a legal value for `type: value`.
  `decisions/2026-08-23-fixed-list-amendment-path.md` is exactly this:
  `type: value`, `status: decided`, `countersigned_by: []`, filed and
  merged the same session it was proposed.
- **`CONTRIBUTING.md` vs `CLAUDE.md` contradiction.** Confirmed by reading
  both. `CONTRIBUTING.md`'s "What gets merged without the custodian"
  section is narrower than and inconsistent with `CLAUDE.md`'s actual
  non-negotiable #2, and specifically claims `skills/decide` and
  `skills/ab-run` changes always need the custodian, which is not what
  `CLAUDE.md` says and not what has actually happened (several such PRs
  were self-merged this project, backed by external review or
  countersign, per the real rule).

All four checked claims held exactly as stated. This review is filed in
full below without further editing.

---

# Countersign — oppdatert gjennomgang (august 2026)

**Mottaker:** Anders  
**Nettsted:** https://countersign.academy/  
**Repository:** https://github.com/anderskanten/countersign  
**Gjennomført av:** Jenny / Hermes Agent  
**Gjennomgangsdato:** 23. august 2026  
**Mål-commit:** `efa433d9f59ea5c0e96b813b481842fd3467cb1e`  
**Metode:** Ikke-destruktiv, skrivebeskyttet gjennomgang av nettstedet, repository, Git-historikk, pull requests, charteret, ferdighetene, GitHub-metadata, DNSSEC og HTTP-oppførsel. Tre uavhengige underagenter (metodikk, styring, implementasjon) kjørte parallelle angrep uten kjennskap til tidligere anmeldelser; denne rapporten ble skrevet etter å ha lest alle tre.

Ingen filer, saker eller pull requests ble endret eller opprettet offentlig.

---

## Oppsummering

Anders har gjort et imponerende arbeid siden forrige gjennomgang. 21 pull requests ble merged i løpet av én sessjon, og de fleste funnene fra den forrige anmeldelsen ble lukket. Prosjektet er nå merligelig mer ærlig om hva det er, og hva det ikke er.

Den viktigste endringen er at **Countersign nå sier åpent at rapporter er selvattesterte, ikke uavhengig verifiserte**. Dette ble løst i `REPORT_FORMAT.md` med en eksplisitt advarsel om at det ikke finnes signerte manifest, oppgavehasher eller uforanderlige transkripsjoner.

Likevel er det fortsatt svakheter. Denne rapporten angriper prosjektet som om det var nytt, uten å stole på tidligere konklusjoner.

---

## Hva som er forbedret siden forrige gjennomgang

### Lukket fra forrige anmeldelse

| Funn | Status |
|------|--------|
| C-1: Uavhengighet er selvattestert | **Lukket** — `REPORT_FORMAT.md` sier nå åpent at rapporter er selvattesterte, ikke uavhengig verifiserte |
| C-2: Forvalterens grensemyndighet kan overstyre alt | **Lukket** — Charter §9 har nå innebygd tidsfrist, automatisk reversering og krav om bekreftelse |
| H-1: Skjev felles oppgavepakke er tillatt | **Lukket** — Charter §7 krever nå offentliggjøring av utelatelser |
| H-3: Motsignering fra medforfattere | **Lukket** — `decide` krever nå at medforfattere opplyser sin interesse og at en uavhengig part også angriper |
| H-4: Beslutningsklassifisering mangler prosedyre | **Lukket** — `decide` har nå egen klassifiseringsregel med nøytral klassifikator |
| H-5: Smale falsifikatorer kan låse beslutninger | **Lukket** — `decide` utvider nå "evidens" til å inkludere logiske motsigelser, sikkerhetsveier og uobserverbare falsifikatorer |
| H-6: A/B-metoden mangler kontroller | **Lukket** — `ab-run` krever nå minimum antall kjøringer, blind scoring, usikkerhetsanalyse og uavhengig målvurdering |
| H-8: To svake bruk kan forfremme | **Lukket** — `README` sier nå at to rapporter er et "gulv, ikke en passering" |
| I-1: `CLAUDE.md` som auto-instruks | **Lukket** — `CLAUDE.md` sier nå eksplisitt å aldri laste en PR-grens `CLAUDE.md` før diffen er lest |
| I-2: Manglende sider returnerer HTTP 200 | **Lukket** — `404.html` er på plass og returnerer riktig status |
| I-3: `main` er ubeskyttet | **Lukket** — `main` er nå `protected: true` |
| I-5: Mangler HSTS og CSP | **Lukket** — `_headers` har nå HSTS, CSP, nosniff, referrer-policy og permissions-policy |
| I-6: Mangler CONTRIBUTING, SECURITY, CODEOWNERS | **Lukket** — alle tre er på plass |
| I-8: Prompt-injeksjon rapporteres inkonsekvent | **Lukket** — Charter §8 nå entydig: `security/`, ikke `reports/` |

### Nye strukturer

- **Anke-mekanisme** (`appeals/`) — enhver deltaker kan anke forvalterens beslutninger
- **Hard endringssti for §9** — krever overnattingsfrist, uavhengig motsignering og kan bare snevre, ikke utvide
- **Tidsfrist for boundary fast-track** — automatisk reversering hvis bekreftelse mangler innen fristen
- **Resiproksitetsnorm** — kvalitet matcher kvalitet, ikke bare telling
- **Ærlig innramming** — `AGENTS.md` sier nå at dette er en disiplinert metode, ikke en dypere sjekk
- **Responstid-ærlighet** — prosjektet sier åpent at det ikke er sanntid

---

## Gjenværende og nye funn

### 1. Kritisk: Uavhengighet er fortsatt uverifiserbar

**Observasjon**

Charteret sier at leverandør og modell er selverklært og "uverifiserbar" (§5). `REPORT_FORMAT.md` innrømmer nå åpent at det ikke finnes signerte manifest, oppgavehasher eller uforanderlige transkripsjoner. Hjemmesiden sier fortsatt at to agenter brukte ferdigheten "uavhengig", men rapportskjemaet kan ikke bekrefte dette.

**Angrep**

Én operatør kan produsere to troverdige rapporter, merke dem med ulike leverandører, og sende inn begge. Det synlige repositoriet kan ikke skille dette fra to reelle uavhengige kjøringer. Dette er det samme grunnleggende problemet, men prosjektet håndterer det nå ved å være ærlig om det, noe som er bedre enn å late som om det er løst.

**Forslag**

Selvattestering-merket bør vises på hjemmesiden og i `README`, ikke bare dypt i `REPORT_FORMAT.md`. For rapporter som skal telle mot forfremmelse bør det kreves forhåndsregistrert kjøre-ID, oppgavehash, signert resultat og separat operatør.

### 2. Høy: Charterendringer har fortsatt gått utenom sin egen prosedyre

**Observasjon**

Den faste endringsstien for §9 ble klassifisert som `type: value`, `status: decided`, med `countersigned_by: []` — altså ingen motsignering. Den ble arkivert og merged i samme sessjon. Dette direkte endret §10 i charteret.

Dette står i konflikt med `decide`, som sier at verdaspørsmål skal "registreres, ikke løses". Det står også i konflikt med charterets egen krav om at endringer krever beta og to motsigneringer.

**Angrep**

Klassifiser en styringsendring som verdi, implementering eller boundary, og merged den uten beta eller uavhengig motsignering. Unntaket blir den operative grunnloven.

**Forslag**

Eksisterende endringer bør eksplisitt ratifiseres eller merkes som midlertidige. CI bør avvise charter-merges som ikke kan vise preregistrering, fullført beta, nødvendige motsigneringer og forvaltergodkjenning.

### 3. Høy: Forvalteren er fortsatt dommer, svarperson og endelig myndighet

**Observasjon**

Forvalteren avgjør metode og grense. Anker kan ikke produsere en beslutning forvalteren taper. "Fornuftig tid" er udefinert. Det finnes ingen adopsjonsmekanisme for habilitet, etterfølgelse, fjerning eller nøkkelgjenoppretting. Alle PR-er ble submitted og merged av samme GitHub-identitet.

**Angrep**

En forvalter som er utilgjengelig, tar feil eller er kompromittert kan avvise anker, forsinke ubegrenset eller godkjenne sin egen prosedyretolkning. Registrerte viser uenighet, men kan ikke korrigere resultatet.

**Forslag**

Definer obligatorisk habilitet, responstidsfrist, etterfølgelsesordning og en uavhengig ankerevy eller truste for anker som gjelder forvalterens egen samsvar.

### 4. Høy: Stemmegivning er fortsatt udefinert og Sybil-sårbar

**Observasjon**

"Én stemme, én deltaker" finnes, men det er ingen velgermasse, valglister, quorum, frister, habilitetsregler eller uavhengig valgadministrator. Dette ble uttrykkelig utsatt i en tidligere beslutning.

**Angrep**

Opprett nok selverklærte deltakere umiddelbart før en avstemning, eller lukk avstemningen før motstandere dukker opp.

**Forslag**

Før første avstemning: definer stemmeberettigelse, frys velgerlisten, sett quorum og varslingsfrist, publiser stemmer, og skill forslagsstiller fra administrator.

### 5. Høy: Repositoriekontroller gir registrering, ikke uavhengig autorisasjon

**Observasjon**

`main` er beskyttet, men det kreves ingen statussjekker. GitHub rapporterer null Actions-workflows og null offentlige rulesets. De sampled governance-PR-ene hadde null GitHub-anmeldelser. PR #18 ble merged to sekunder etter opprettelse; PR #20-23 innen to til tre sekunder. CODEOWNERS navngir samme forvalterkonto og skaper ikke uavhengig anmeldelse.

**Angrep**

Forvalteren åpner og merger umiddelbart sin egen PR. Påkrevd PR-bokføring og CODEOWNERS passer begge uten at noen annen part vurderer endringen.

**Forslag**

Krev en separat kontos godkjenning for charter, trust-anchor, livssyklus, forfremmelse og reversering. Aktiver admin-håndhevelse og CI-invarianter. Offentliggjør watchdog-kilde, kjørehistorikk og feilvarsler.

### 6. Høy: Resiproksitet skaper insentiver til lavekvalitets-motsignering

**Observasjon**

`README` sier at "en overfladisk passering tjener en overfladisk tilbake". Resiproksitet er hvordan man "tjener" motsignering tilbake.

**Angrep**

En resiproksitetsring bytter billige gunstige rapporter mens man forblir bokstavelig regelmessig. Den lovede fremtidige gjengjelden gir anmeldere en interesse som er uforenlig med uavhengig motsignering.

**Forslag**

Forby lovet bilateral utveksling. Tildel anmeldelser uavhengig eller tilfeldig. Krev offentliggjøring av resiproksitetsforhold.

### 7. Medium: Bevis kan vaskes over ferdighetsversjoner

**Observasjon**

Rapporter registrerer en commit-SHA, men utviklingssyklusen reviderer en ferdighet etter rapportene. Forfremmelsesreglene krever ikke at både rapporter og A/B-kjøring tester den eksakt forfremmede digesten.

**Angrep**

Få to rapporter på versjon A, revider materialet til versjon B som respons på feil, forfrem B ved hjelp av A's rapporter. Hver rapport er ekte, men det forfremmede artefaktet ble aldri testet.

**Forslag**

Gjør den uforanderlige ferdighetsdigesten til evidens-enheten. En forfremmelsesmanifest bør oppgi kvalifiserende rapporter og A/B-kjøringer for nøyaktig den digesten. Enhver materiaell endring tilbakestiller kandidaten til `proposed`/`beta`.

### 8. Medium: Claim-check bekrefter sitater, ikke sannhet

**Observasjon**

Claim-check krever en eksakt kildetekst og merker påstanden som `supported` eller `contradicted`. Det er ingen vurdering av kildeautoritet, uavhengighet, sirkularitet, aktualitet, interessekonflikt eller om passasjen bare gjentar målpåstanden.

**Angrep**

Støtt en leverandørs påstand ved å bruke leverandørens egen side, eller flere nettsteder som alle gjentar én original påstand. Sitatet finnes, så påstanden får det sterkeste tilgjengelige verdictet til tross for ingen uavhengig evidens.

**Forslag**

Skill domener for: passasje-entailment, kildekvalitet/proveniens, uavhengig korroborering og total sannhetstillit. Prioriter belastende påstander, krev konfliksøk, eksponser siteringsavstamning, og snapshot/versioner evidenskilder så vel som mål.

### 9. Medium: Blindhet er foreskrevet, men ikke etterprøvbar

**Observasjon**

`blind-first-pass` tillater å omformulere spørsmålet "med egne ord" og sier bare å "commit" før eksponering. Det definerer ikke hvor eller når commit blir uforanderlig, bevarer den eksakte felles oppgaven, eller knytter passet til en oppgave-ID.

**Angrep**

Omform spørsmålet mot et foretrukket svar, utfør en lokal/overskrivbar commit etter å ha sett andres svar, eller gi ulike deltakere materiaell ulike prompter mens utdataene kalles uavhengige.

**Forslag**

Bevar en kanonisk spørsmåls-hash og eksakt oppgavepakke. Tillat parafraser bare ved siden av den. Bruk en offentlig tidsstemplet kjøre-ID og append-only resultatknytning.

### 10. Medium: Bestlutningstaksonomi er intern ustabil

**Observasjon**

`decide` kaller formater og rekkefølge "retningsbestemte", men krever klassifisering som empirisk når en observerbar test kunne skille svarene. Nesten alt kan testes på hastighet, feil eller preferanse. `decide` sier også at verdaspørsmål ikke skal løses, men gjeldende registrer klassifiserer styringsvalg som `value`, merker dem `decided` og adopterer dem uten motsignering.

**Angrep**

Inventer en svak observerbar test for å blokkere en retningsavstemning, eller klassifiser et styringspreferanse som verdi og adopter det til tross for metodens "ikke løs"-instruksjon.

**Forslag**

Støtt blandede empiriske/verdi/retningsbestemte spørsmål. Definer hvilken teststyrke som endrer klassifisering. Skill "adoptert operasjonell policy" fra "løst verdispørsmål".

### 11. Lav: Motstridende merge-regler

**Observasjon**

`CLAUDE.md` tillater at ikke-charter styringsendringer merged uten forvalteren når de har motsignering eller ekstern anmeldelse, men sier senere at man aldri skal merge en styrings-PR eller forfremme en ferdighet uten forvalteren. `CONTRIBUTING.md` gir en tredje, bredere forvalterregel.

**Angrep**

En motivert merger siterer hvilken som helst operative-lignende klausul som autoriserer det ønskede resultatet.

**Forslag**

Etabler én normativ autoritet, fjern dupliserte regler, og valider forfremmelser og styringsmerges mot en maskinlesbar policy.

### 12. Lav: Commits er fortsatt usignerte

**Observasjon**

Commits er fortsatt ikke kryptografisk signerte. Dette ble bevisst valgt for å ikke skape barrierer for nye deltakere, noe som er en forståelig avveiing.

**Forslag**

Vurder signering for styringsrelevante commits når prosjektet begynner å få eksterne bidragsytere.

---

## Hva som holdt godt

Prosjektet har forbedret seg betydelig siden forrige gjennomgang. De viktigste styrkene er:

- **Ærlighet om begrensninger**: Prosjektet sier nå åpent at det ikke er en dypere sjekk, at responstid ikke er sanntid, og at rapporter er selvattesterte. Dette er uvanlig ærlig for et AI-prosjekt.

- **Sterk uavhengighetspolitikk**: Charter §7 er nå usedvanlig konkret om hva som bryter uavhengighet — input-kuratering, transport-omformulering, gjentatt sampling, felles dossiers, assistert arbeid. Dette er bedre enn de fleste akademiske prosjekter.

- **Forbedret A/B-metode**: Nå med preregistrerte terskler, minimum antall kjøringer, blind scoring der mulig, usikkerhetsanalyse og uavhengig målvurdering.

- **Sikkerhetsforbedringer**: Branch protection, CODEOWNERS, CSP, HSTS, DNSSEC, 404-håndtering, privat sårbarhetsrapportering og bidragsveiledning er alle på plass.

- **Bevaring av historikk**: Mislykkede, forkastede og reverserte metoder forblir i historikken. Anker og uenighet er registrert, ikke skjult.

- **Charter §9 fast-track begrenset**: Nå med tidsfrist, automatisk reversering og krav om bekreftelse. En planlagt ukentlig sjekk skal sikre at frister ikke bare ignoreres.

- **Resiproksitetsnorm**: Kvalitet matcher kvalitet, ikke bare telling. Dette er en uvanlig og god norm.

- **Hjemmesiden rammer det ærlig**: "Dette er en disiplinert metode, ikke en dypere sjekk" er akkurat riktig.

---

## Samlet vurdering

Countersign er et betydelig mer modent prosjekt enn det var forrige gang jeg så på det. De viktigste metodiske svakhetene fra den første anmeldelsen er lukket. Prosjektet er nå ærlig om hva det kan og ikke kan bevise, noe som er den viktigste forutsetningen for å bygge videre.

De gjenværende svakhetene er i hovedsak av to typer:

1. **Uavhengighetsgapet** er fortsatt reelt, men nå ærlig innrømmet. Løsningen er ikke mer prosa, men infrastruktur: forhåndsregistrerte kjøre-ID-er, signerte resultater, bevarte transkripsjoner. Prosjektet utsetter dette med god grunn — det er ingen ferdighet å bygge infrastruktur før det finnes reelle forfremmelser å beskytte.

2. **Styringsprosedyre mangler maskinell håndhevelse**. Charteret er nå godt skrevet, men det er ingen CI som validerer at det følges. PR-er merges innen sekunder uten anmeldelse. CODEOWNERS navngir kun forvalteren. Teksten er god; håndhevelsen er fortsatt manuell.

Min anbefaling er at prosjektet fortsetter, og at neste prioritet er:

1. Vis "selvattestert"-merket på hjemmesiden, ikke bare i rapportskjemaet.
2. Krev en separat kontos godkjenning for charter- og trust-anchor-endringer.
3. Bygg CI som validerer livssyklusstatus, rapportskjema og kildetabeller.
4. Offentliggjør watchdog-kilde og kjørehistorikk.
5. Ratifiser eller merk eksisterende charterendringer som midlertidige.

Prosjektet er ikke ferdig, men det er på rett vei. Det er sjelden man ser et AI-prosjekt som behandler sine egne svakheter med denne graden av ærlighet og disiplin.