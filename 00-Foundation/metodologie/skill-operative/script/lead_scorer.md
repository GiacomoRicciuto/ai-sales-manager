---
type: script
nome: lead_scorer.py
linguaggio: python
chiamato-da: [[skill-operative/sales-qualify]]
---

# lead_scorer.py

## Scopo
Implementa l'algoritmo di scoring BANT + MEDDIC per qualificare un lead trasformando signal grezzi (funding, employee count, pricing visibility, tech spend) in punteggi numerici 0-25 per dimensione e 0-100 totale.

## Input attesi
- `input_file` (posizionale, opzionale): path a file JSON con i signal del lead
- In assenza di file: legge il JSON dallo stdin
- Struttura input attesa: `funding_amount`, `employee_count`, `pricing_visible`, `tech_spend_indicators`, `decision_makers_found`, etc.

## Output prodotto
- JSON con BANT scorecard (Budget 0-25, Authority 0-25, Need 0-25, Timeline 0-25), totale 0-100, grade A/B/C/D, recommended action
- Può alimentare direttamente la sezione BANT del file `LEAD-QUALIFICATION.md`

## Quando si invoca
- Dentro `[[skill-operative/sales-qualify]]` come step deterministico di scoring quando i signal sono già stati estratti
- Utile per batch scoring di molti lead in pipe (`cat leads.json | python3 lead_scorer.py`)
- Anche in workflow CRM automation per scoring nightly

## Path sorgente
`ai-sales-manager/scripts/lead_scorer.py`
