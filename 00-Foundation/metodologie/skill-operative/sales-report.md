---
type: skill-operativa
nome: sales-report
trigger: /sales report
inputs: [tutti i file PROSPECT-ANALYSIS.md, COMPANY-RESEARCH.md, etc. nella working directory]
outputs: [SALES-REPORT.md con pipeline dashboard, score distribution, top prospects, action items, weekly focus]
dipendenze: [Glob per scan, parsing dei file di analisi precedenti]
---

# sales-report

## Cosa fa
Sales operations analyst che compila singole prospect analysis in un report di pipeline unificato, executive-ready. Scansiona la directory corrente, estrae score, grade, stage, pain point, decision maker, next action e deal value da tutti i file di analisi pregressi, li sintetizza in una pipeline view coerente e produce un documento che risponde a: "Dove sta la pipeline e cosa faccio oggi?". Data-driven, onesto (no inflating), action-oriented.

## Quando si usa
- Sales kickoff settimanale (Monday morning)
- Forecasting di fine mese/trimestre
- Pipeline review prima di QBR
- Hand-off di pipeline a nuovo rep
- Health check periodico (mensile) sullo stato del pipeline

## Procedura
1. **Step 1 Scan:** Glob ricorsivo su `**/PROSPECT-ANALYSIS.md`, `**/COMPANY-RESEARCH.md`, `**/LEAD-QUALIFICATION.md`, `**/DECISION-MAKERS.md`, `**/OUTREACH-SEQUENCE.md` + pattern alternativi `*-prospect-analysis.md`.
2. **Step 2 Handle Empty Pipeline:** se nessun file, output "Pipeline Empty" con getting started e workflow example.
3. **Step 3 Extract Data per Prospect:** company name, URL, Overall Score, Grade, 5 component scores, key pain point, decision makers, next action, outreach status, est. deal value, pipeline stage.
4. **Step 4 Classify Pipeline Stages:** New / Researched / Qualified / Contacted / Meeting / Proposal / Negotiation / Closed Won / Closed Lost in base ai file indicator.
5. **Step 5 Compile Report 8 sezioni:**
   - Executive Summary 3-5 paragrafi (totals, distribution, top opportunity, biggest risk, one-line recommendation)
   - Pipeline Dashboard (tabella TUTTI i prospect ordinata per score)
   - Score Distribution (counts per grade + commentary)
   - Top 5 Prospects dettagliati (component scores, contacts, pain, approach, risk)
   - Action Items (Immediate this week / Short-term 2 weeks / Pipeline Building)
   - Outreach Status (tabella sequence created/needed)
   - Pipeline Health Metrics (total, avg score, A-grade %, coverage, std deviation, health rating)
   - Weekly Focus (top 3 prospects con piano giornaliero Mon-Fri)
6. Sort by score sempre. Numeri come integer, percentuali con 1 decimale.
7. Output `SALES-REPORT.md` di 250-350 righe + verbal summary all'utente.

## Input richiesti dalla wiki
- Tutti i file in `50-Output/` (PROSPECT-ANALYSIS, COMPANY-RESEARCH, LEAD-QUALIFICATION, DECISION-MAKERS, OUTREACH-SEQUENCE)
- `[[00-Foundation/sales-rep/...]]` — per personalizzare il weekly focus al rep
- `[[30-Trattative/...]]` — stato CRM per stage classification

## Output prodotto
- `SALES-REPORT.md` archiviato in `50-Output/YYYY-MM-DD-sales-report.md`
- Sezioni: Executive Summary, Pipeline Dashboard, Score Distribution, Top Prospects, Action Items, Outreach Status, Pipeline Health, Weekly Focus, Methodology

## Collegamenti
- Skill correlate: `[[skill-operative/sales-prospect]]`, `[[skill-operative/sales-report-pdf]]`, `[[skill-operative/sales-followup]]`, `[[skill-operative/sales-icp]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/sistemica/holmes-ultimate-sales-machine]]`, `[[biblioteca-vendita/consultativa/miller-heiman-strategic-selling]]`, `[[biblioteca-vendita/consultativa/lahoutifard-meddic]]`, `[[biblioteca-vendita/sistemica/roberge-sales-acceleration-formula]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-report/SKILL.md`
