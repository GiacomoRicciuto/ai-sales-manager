---
type: skill-operativa
nome: sales-prep
trigger: /sales prep <url>
inputs: [URL azienda, nomi attendees, data e ora meeting, scopo meeting]
outputs: [MEETING-PREP.md con cheat sheet, talking point, discovery question, obiezioni attese, agenda]
dipendenze: [WebFetch, WebSearch, template meeting-prep.md]
---

# sales-prep

## Cosa fa
Genera un brief di preparazione meeting completo e tattico. Combina company research, attendee intelligence, competitive context e preparazione tattica in un singolo documento actionable. Sezione cardine: il Cheat Sheet con le 5 cose più importanti + opening line + key question + trap to avoid. Include 5-7 talking point personalizzati, 10 discovery question ordinate (rapport → impact → future state), 5 obiezioni attese con Feel-Felt-Found response, success metrics, competitive landmines, next step da proporre con script.

## Quando si usa
- Pre-discovery call su prospect freddo
- Pre-demo con committee esteso (3+ stakeholder)
- Pre-negotiation con economic buyer
- Pre-pitch a clienti enterprise
- Refresh prep su meeting recurring (QBR, follow-up)

## Procedura
1. **Step 1.1 Company Research:** fetch homepage, about, product, blog, careers, case studies + WebSearch su news, funding, LinkedIn activity.
2. **Step 1.2 Attendee Research:** se i nomi sono forniti, per ognuno LinkedIn profile, recent posts, conference talks, articoli pubblicati. Costruisce profilo con communication style, priorità, rapport anchor, how to win them over. Se nomi assenti, infera likely attendees dal meeting type.
3. **Step 1.3 Competitive Landscape:** detection current tools, your advantages, topics to avoid.
4. **Step 1.4 Industry Context:** 2-3 trend rilevanti, regulatory change, market shift.
5. **Step 2 Brief Build:** sezione 1 = Cheat Sheet (top 5 + opening + must-ask + trap). Sezione 2 = Company Snapshot. Sezione 3 = Attendee Profiles. Sezione 4 = Business Situation. Sezione 5 = Competitive Context.
6. Sezione 6 = 5-7 Talking Point specifici (no generic icebreaker), ognuno con context + leads to.
7. Sezione 7 = 10 Discovery Question ordinate: 1-2 rapport → 3-4 current → 5-6 pain → 7-8 impact → 9-10 future + decision process. Ogni domanda con purpose, expected response, follow-up, listen-for.
8. Sezione 8 = 5 obiezioni attese con Feel-Felt-Found framework e proof point.
9. Sezione 9 = Success Metrics (minimum/target/stretch). Sezione 10 = Competitive Landmines. Sezione 11 = 3 Next Step pre-scriptati (bold/standard/minimum) con timing.
10. **Step 3 Agenda:** template strutturato 30 o 60 minuti pronto da copiare.
11. Output `MEETING-PREP.md`.

## Input richiesti dalla wiki
- `[[10-Account/<azienda>]]` — scheda account
- `[[20-Persone/...]]` — schede attendees con personalization anchor già raccolti
- `[[30-Trattative/...]]` — trattativa attiva con stage, deal size, history
- `[[00-Foundation/azienda/...]]` — case study e proof point
- `[[00-Foundation/sales-rep/...]]` — stile comunicativo del rep
- Eventuali analisi pregresse `PROSPECT-ANALYSIS.md`, `LEAD-QUALIFICATION.md`, `COMPETITIVE-INTEL.md`, `DECISION-MAKERS.md`

## Output prodotto
- `MEETING-PREP.md` archiviato in `50-Output/YYYY-MM-DD-prep-<account>.md`
- Sezioni: Cheat Sheet, Company Snapshot, Attendee Profiles, Business Situation, Competitive Context, 5-7 Talking Points, 10 Discovery Questions, 5 Objections to Expect, Success Metrics, Competitive Landmines, Next Steps to Propose, Suggested Agenda

## Collegamenti
- Template: `[[skill-operative/template/meeting-prep]]`
- Skill correlate: `[[skill-operative/sales-prospect]]`, `[[skill-operative/sales-research]]`, `[[skill-operative/sales-contacts]]`, `[[skill-operative/sales-objections]]`, `[[skill-operative/sales-followup]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/consultativa/rackham-spin-selling]]`, `[[biblioteca-vendita/challenger/dixon-challenger-sale]]`, `[[biblioteca-vendita/negoziazione/voss-never-split]]`, `[[biblioteca-vendita/consultativa/sandler-cant-teach-a-kid]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-prep/SKILL.md`
