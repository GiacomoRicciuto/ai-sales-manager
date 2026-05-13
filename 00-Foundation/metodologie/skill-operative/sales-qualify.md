---
type: skill-operativa
nome: sales-qualify
trigger: /sales qualify <url>
inputs: [URL azienda, eventuali analisi company/contacts/competitive pregresse]
outputs: [LEAD-QUALIFICATION.md con BANT + MEDDIC + Opportunity Quality Score 0-100]
dipendenze: [WebFetch, WebSearch, lead_scorer.py, agente sales-opportunity]
---

# sales-qualify

## Cosa fa
Motore di qualificazione lead che valuta il prospect contro due framework consolidati (BANT e MEDDIC) usando solo informazioni pubbliche. Estrae signal da 12 fonti (pricing, careers, jobs, blog, case studies, about, review sites, Glassdoor, LinkedIn, news, social, competitor mentions) e li classifica per confidence (High/Medium/Low/Inferred). Output finale: Opportunity Quality Score 0-100 con grade A/B/C/D e recommended approach. Invocabile standalone o come sub-agente `sales-opportunity` in `prospect`.

## Quando si usa
- Triage di un MQL prima di passarlo al SQL handoff
- Score di un lead inbound per decidere assegnazione al rep
- Validazione di un lead outbound prima dell'investimento di tempo
- Refresh trimestrale su account in pipeline per riprioritizzare
- Pre-meeting check per capire quanto è qualificato il prospect

## Procedura
1. **Phase 1 Data Collection:** fetch e analisi delle 12 fonti, signal extraction con confidence level.
2. **Phase 2 BANT Assessment** (ogni dimensione 0-25):
   - Budget: funding recente, enterprise tier, tech spend, hiring per role rilevanti
   - Authority: economic buyer identificato, org structure visibile, procurement signals
   - Need: pain point esplicito, job posting per role che risolve il problema, recensioni negative current solution
   - Timeline: RFP in corso, trigger event recente, budget cycle alignment
3. **Phase 3 MEDDIC Assessment:** Metrics, Economic Buyer, Decision Criteria, Decision Process, Identify Pain, Champion. Per ognuno: finding + evidence + confidence.
4. Calcolo MEDDIC Completeness = (elementi con Medium+ confidence / 6) * 100.
5. **Phase 4 Scoring:** `Opportunity Quality Score = BANT * 0.50 + MEDDIC_Completeness * 0.30 + Urgency_Modifier * 0.20`.
6. Assegnazione grade A (75-100 SQL) / B (50-74 MQL) / C (25-49 IQL) / D (0-24 Unqualified).
7. Compilazione di Buying Signals Summary e Red Flags Summary.
8. Recommended Approach differenziato per grade (executive direct, educational, nurture, awareness).
9. Output `LEAD-QUALIFICATION.md` + terminal scorecard.

## Input richiesti dalla wiki
- `[[10-Account/<azienda>]]` — scheda account
- `[[00-Foundation/icp/...]]` — ICP e scoring rubric di riferimento
- `[[00-Foundation/offerte/...]]` — offerta per valutare la rilevanza del pain
- Eventuale `[[50-Output/...-research-<account>]]` per evitare ricerche ridondanti

## Output prodotto
- `LEAD-QUALIFICATION.md` archiviato in `50-Output/YYYY-MM-DD-qualify-<account>.md`
- Sezioni: Qualification Snapshot, BANT Scorecard con analisi per dimensione, MEDDIC Assessment, Buying Signals Detected, Red Flags, Opportunity Quality Score breakdown, Recommended Approach, Next Steps

## Collegamenti
- Agenti: `[[skill-operative/agenti/sales-opportunity]]`
- Script: `[[skill-operative/script/lead_scorer]]`
- Skill correlate: `[[skill-operative/sales-prospect]]`, `[[skill-operative/sales-research]]`, `[[skill-operative/sales-contacts]]`, `[[skill-operative/sales-outreach]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/consultativa/lahoutifard-meddic]]`, `[[biblioteca-vendita/consultativa/rackham-spin-selling]]`, `[[biblioteca-vendita/consultativa/miller-heiman-strategic-selling]]`, `[[biblioteca-vendita/consultativa/sandler-cant-teach-a-kid]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-qualify/SKILL.md`
