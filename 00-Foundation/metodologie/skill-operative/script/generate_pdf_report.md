---
type: script
nome: generate_pdf_report.py
linguaggio: python
chiamato-da: [[skill-operative/sales-report-pdf]]
---

# generate_pdf_report.py

## Scopo
Genera un PDF professionale multi-pagina del Sales Pipeline Report a partire da un file JSON strutturato. Include score gauge circolare, bar chart per score distribution, prospect cards, pipeline summary table, action plan prioritizzato. Usa `reportlab` con palette navy/blue/amber/green/red color-coded per grade.

## Input attesi
- `json_data_file` (posizionale, required): path al file JSON generato da `sales-report-pdf` (es. `_pdf_input.json`) con tutta la struttura dati di pipeline
- `output_pdf_file` (posizionale, opzionale): path del PDF di output (default: nome auto-generato `SALES-REPORT-YYYY-MM-DD.pdf`)
- Senza argomenti: genera un sample report demo per testing

## Output prodotto
- PDF Letter portrait (landscape per tabelle wide), 4-8 pagine, font Helvetica, margins 0.75"
- Sezioni: Cover (Pipeline Score gauge + health rating + quick stats), Score Breakdown (bar chart), Prospect Comparison Table, Top Prospects Detail (per ognuno radar/bar chart + dettagli), Action Plan, Methodology

## Quando si invoca
- Dentro `[[skill-operative/sales-report-pdf]]` come step finale di generazione PDF
- Richiede `reportlab` installato (`pip install reportlab`)
- Richiede che esista `SALES-REPORT.md` da cui sono stati estratti i dati JSON
- File `_pdf_input.json` rimosso su successo, mantenuto su failure per debug

## Path sorgente
`ai-sales-manager/scripts/generate_pdf_report.py`
