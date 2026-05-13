---
type: skill-operativa
nome: sales-report-pdf
trigger: /sales report-pdf
inputs: [SALES-REPORT.md generato da /sales report, file prospect singoli per arricchimento]
outputs: [SALES-REPORT-YYYY-MM-DD.pdf professionale con cover gauge, bar chart, prospect table, action plan]
dipendenze: [Python 3, reportlab, generate_pdf_report.py, SALES-REPORT.md preesistente]
---

# sales-report-pdf

## Cosa fa
Genera una versione PDF professionale, visivamente curata del report di pipeline. PDF designed per sharing con sales leadership, investitori, team member che vogliono un documento portatile invece di un markdown. Include cover gauge con Overall Pipeline Score circolare, bar chart per score distribution color-coded, tabella prospect comparison alternate rows, dettaglio top prospect con radar/bar chart per component score, action plan prioritized, methodology page. 4-8 pagine, formato Letter, palette professionale (navy/blue/amber/green/red).

## Quando si usa
- Pipeline review con board o leadership
- Update mensile per investitori/founder
- Hand-off pipeline tra rep o tra team
- Documentazione di archivio fine mese/trimestre
- Sharing esterno con consulenti o partner commerciali

## Procedura
1. **Step 1 Verify Prerequisites:** verifica esistenza `SALES-REPORT.md` nella working directory. Se manca → istruzioni a runnare prima `/sales report`. Stop.
2. **Step 2 Check reportlab:** `python3 -c "import reportlab; print(reportlab.Version)"`. Se mancante → propone `pip install reportlab`.
3. **Step 3 Parse Report Data:** estrai Pipeline Overview (date, totals, avg score, health), Prospect Data Array (per ogni: name, url, score, grade, stage, next action, est value, 5 component scores, pain, contact, risk), Top Prospects dettagliati, Action Items prioritized, Pipeline Health Metrics, Score Distribution.
4. **Step 4 Build JSON Input File:** scrivi `_pdf_input.json` con tutta la struttura dati (title, date, overall_pipeline_score, health_rating, prospects[], top_prospects[], action_items[], pipeline_health{}, score_distribution{}, weekly_focus[], methodology{}).
5. **Step 5 Locate Script:** trova `scripts/generate_pdf_report.py` (project root → cwd → parent).
6. **Step 6 Generate PDF:** esegui `.venv/bin/python scripts/generate_pdf_report.py _pdf_input.json "SALES-REPORT-$(date +%Y-%m-%d).pdf"`.
7. PDF sezioni: Cover Page (gauge circolare + health rating + quick stats), Score Breakdown (horizontal bar chart color-coded), Prospect Comparison Table (alternate rows, grade colored, sorted desc), Top Prospects Detail (radar/bar chart per top 5), Action Plan (numbered grouped by timeframe), Methodology.
8. **Step 7 Clean Up:** verifica PDF creato, dimensione file, page count. Rimuovi `_pdf_input.json` su successo, keep su failure per debug.
9. Report all'utente: file name, location, size, pages, summary.

## Input richiesti dalla wiki
- `SALES-REPORT.md` prodotto da `[[skill-operative/sales-report]]`
- Tutti i file `PROSPECT-ANALYSIS.md` e correlati in `50-Output/` per arricchimento
- Eventuali `[[00-Foundation/azienda/...]]` per branding/header

## Output prodotto
- `SALES-REPORT-YYYY-MM-DD.pdf` archiviato in `50-Output/`
- 4-8 pagine Letter portrait (landscape per tabelle wide), font Helvetica, margins 0.75"

## Collegamenti
- Script: `[[skill-operative/script/generate_pdf_report]]`
- Skill correlate: `[[skill-operative/sales-report]]`, `[[skill-operative/sales-prospect]]`, `[[skill-operative/sales-followup]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/sistemica/holmes-ultimate-sales-machine]]`, `[[biblioteca-vendita/sistemica/roberge-sales-acceleration-formula]]`, `[[biblioteca-vendita/consultativa/miller-heiman-strategic-selling]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-report-pdf/SKILL.md`
