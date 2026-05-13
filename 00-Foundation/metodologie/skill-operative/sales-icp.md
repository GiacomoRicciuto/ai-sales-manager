---
type: skill-operativa
nome: sales-icp
trigger: /sales icp <description>
inputs: [descrizione business/prodotto/servizio dell'utente]
outputs: [IDEAL-CUSTOMER-PROFILE.md su 6 dimensioni + negative ICP + scoring rubric + personas + playbook]
dipendenze: [WebSearch per validazione market sizing e competitors]
---

# sales-icp

## Cosa fa
Costruisce un Ideal Customer Profile completo e operativo a partire dalla descrizione del business dell'utente. Produce un documento di 300-400 righe che copre 6 dimensioni (firmographic, technographic, behavioral, pain point, budget, channel), il negative ICP (chi NON vendere), una rubric di scoring 100 punti, 2-3 buyer personas dettagliate e un prospecting playbook con query reali. L'ICP diventa la base di calibrazione per tutti gli altri comandi `/sales` (in particolare `prospect`).

## Quando si usa
- Onboarding di un nuovo cliente/azienda che non ha mai formalizzato il proprio ICP
- Revisione trimestrale dell'ICP dopo cambio prodotto, prezzo o mercato
- Post-mortem dopo 3+ deal persi sullo stesso obiezione o competitor
- Preparazione di una campagna outbound prima del lancio
- Riposizionamento dopo ingresso/uscita di un major competitor

## Procedura
1. **Step 1 Parse:** estrai dalla descrizione cosa fa il prodotto, deal size, differenziatori, vertical, stage.
2. Una sola domanda di chiarimento ammessa se descrizione <10 parole.
3. **Step 2 Research Phase:** 5 WebSearch su market size, competitor landscape, industry trends, buyer behavior, pricing benchmarks.
4. **Step 3 Build framework 6 dimensioni:** firmographic, technographic, behavioral, pain point mapping, budget qualification, channel preferences. Ogni dimensione: criteri specifici, range numerici, tools nominati, job title concreti.
5. **Step 4 Negative ICP:** minimo 8-10 criteri di disqualification con red flag e ragione.
6. **Step 5 Scoring rubric:** 6 categorie ponderate (firmographic 25, technographic 15, pain 20, budget 20, contact 10, timing 10). Per ogni categoria definire 0%/25%/50%/75%/100%. Grade bands A+/A/B/C/D + checklist 60 secondi.
7. **Step 6 Personas:** 2-3 personas con archetype, day-in-the-life, KPI, pain in their language, info diet, top 3-5 obiezioni, messaging che risuona, what turns them off.
8. **Step 7 Prospecting playbook:** dove trovarli, search strategies con query reali, signal monitoring, prioritization, enrichment checklist, warm path, timing tactics, outreach templates per persona.
9. Output `IDEAL-CUSTOMER-PROFILE.md` + sezione ICP Maintenance Guide.

## Input richiesti dalla wiki
- `[[00-Foundation/azienda/...]]` — descrizione del business proprio
- `[[00-Foundation/offerte/...]]` — offerta principale e prezzi
- `[[00-Foundation/funnel/...]]` — funnel attuale per validare assunzioni
- Eventuali case study e win/loss precedenti in `raw/`

## Output prodotto
- `IDEAL-CUSTOMER-PROFILE.md` archiviato in `50-Output/YYYY-MM-DD-icp-<dominio>.md` (o direttamente in `00-Foundation/icp/<nome>.md` se l'ICP è canonico)
- Sezioni: ICP Summary, 6 dimensioni con tabelle, Negative ICP, Scoring Rubric, Buyer Personas, Prospecting Playbook, Competitive Context, ICP Maintenance Guide

## Collegamenti
- Skill correlate: `[[skill-operative/sales-prospect]]`, `[[skill-operative/sales-research]]`, `[[skill-operative/sales-qualify]]`, `[[skill-operative/sales-outreach]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/challenger/dixon-challenger-customer]]`, `[[biblioteca-vendita/sistemica/holmes-ultimate-sales-machine]]`, `[[biblioteca-vendita/direct-response/schwartz-breakthrough-advertising]]`, `[[biblioteca-vendita/consultativa/sandler-cant-teach-a-kid]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-icp/SKILL.md`
