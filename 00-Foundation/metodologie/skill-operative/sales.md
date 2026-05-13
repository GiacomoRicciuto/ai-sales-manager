---
type: skill-operativa
nome: sales
trigger: /sales <comando> <argomenti>
inputs: [comando, URL/azienda/descrizione, eventuali analisi pregresse in cartella]
outputs: [routing al sub-skill corretto, file MD prodotti dal sub-skill]
dipendenze: [tutte le 13 sub-skill, agenti del comando prospect, contesto Foundation]
---

# sales

## Cosa fa
Orchestratore principale dell'intero sistema commerciale. Riceve il comando `/sales <comando>` e indirizza l'esecuzione alla sub-skill specifica (`prospect`, `research`, `qualify`, `contacts`, `outreach`, `prep`, `proposal`, `followup`, `objections`, `competitors`, `icp`, `report`, `report-pdf`, `quick`). Detecta il tipo di azienda (SaaS, Agency, E-commerce, Enterprise, SMB, Startup) per calibrare l'analisi e applica gli standard di output (azione, personalizzazione, focalizzazione sul ricavo, citazione delle fonti, pronto all'uso).

## Quando si usa
- Apertura di una nuova trattativa o nuovo lead in ingresso
- Necessita di eseguire un'azione commerciale tracciabile e ripetibile
- Punto di ingresso unico per il sales rep che non vuole memorizzare i singoli comandi
- Avvio del comando flagship `/sales prospect <url>` che lancia 5 sub-agenti in parallelo
- Routing rapido tra fasi diverse del funnel sulla stessa azienda

## Procedura
1. Riceve il comando completo `/sales <comando> <argomenti>` dal sales rep.
2. Identifica il sub-skill corretto in base al comando (es. `prospect` → `[[skill-operative/sales-prospect]]`).
3. Per `prospect`: esegue Phase 1 di Discovery (fetch URL, detection tipo azienda, mappatura pagine, estrazione dati strutturati con `analyze_prospect.py`) e poi lancia in parallelo i 5 sub-agenti.
4. Per i comandi singoli: passa il controllo direttamente al sub-skill corrispondente.
5. Applica la metodologia di Prospect Score (Company Fit 25%, Contact Access 20%, Opportunity Quality 20%, Competitive Position 15%, Outreach Readiness 20%) per l'aggregazione finale.
6. Garantisce che ogni output rispetti i 5 standard: actionable, personalized, revenue-focused, evidence-based, ready-to-use.
7. Salva l'output finale come file MD nominato secondo convenzione (`PROSPECT-ANALYSIS.md`, `COMPANY-RESEARCH.md`, etc.).
8. Suggerisce comandi follow-up coerenti con l'output prodotto.

## Input richiesti dalla wiki
- `[[10-Account/...]]` — scheda account target con URL e contesto azienda
- `[[20-Persone/...]]` — eventuali persone già mappate sull'account
- `[[30-Trattative/...]]` — eventuale trattativa attiva sull'account
- `[[00-Foundation/offerte/...]]` — offerta o servizio che si sta vendendo
- `[[00-Foundation/icp/...]]` — Ideal Customer Profile per calibrare gli scoring
- `[[00-Foundation/sales-rep/...]]` — profilo del rep che esegue il comando
- `[[00-Foundation/azienda/...]]` — value proposition, case study, prezzi della propria azienda

## Output prodotto
- File specifico del sub-skill invocato (`PROSPECT-ANALYSIS.md`, `LEAD-QUALIFICATION.md`, etc.)
- Posizione: `50-Output/YYYY-MM-DD-<comando>-<account>.md`
- Sezioni: dipendono dal sub-skill (executive summary, snapshot, score breakdown, action plan)

## Collegamenti
- Sub-skill: `[[skill-operative/sales-prospect]]`, `[[skill-operative/sales-research]]`, `[[skill-operative/sales-qualify]]`, `[[skill-operative/sales-contacts]]`, `[[skill-operative/sales-competitors]]`, `[[skill-operative/sales-outreach]]`, `[[skill-operative/sales-prep]]`, `[[skill-operative/sales-objections]]`, `[[skill-operative/sales-proposal]]`, `[[skill-operative/sales-followup]]`, `[[skill-operative/sales-icp]]`, `[[skill-operative/sales-report]]`, `[[skill-operative/sales-report-pdf]]`
- Agenti: `[[skill-operative/agenti/sales-company]]`, `[[skill-operative/agenti/sales-contacts]]`, `[[skill-operative/agenti/sales-opportunity]]`, `[[skill-operative/agenti/sales-competitive]]`, `[[skill-operative/agenti/sales-strategy]]`
- Script: `[[skill-operative/script/analyze_prospect]]`, `[[skill-operative/script/lead_scorer]]`, `[[skill-operative/script/contact_finder]]`, `[[skill-operative/script/generate_pdf_report]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/challenger/dixon-challenger-customer]]`, `[[biblioteca-vendita/consultativa/rackham-spin-selling]]`, `[[biblioteca-vendita/consultativa/lahoutifard-meddic]]`, `[[biblioteca-vendita/sistemica/holmes-ultimate-sales-machine]]`

## Riferimento sorgente
`ai-sales-manager/sales/SKILL.md`
