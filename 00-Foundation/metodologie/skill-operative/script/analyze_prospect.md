---
type: script
nome: analyze_prospect.py
linguaggio: python
chiamato-da: [[skill-operative/sales-prospect]]
---

# analyze_prospect.py

## Scopo
Effettua il fetch della homepage di un'azienda e ne estrae dati strutturati (meta-dati, headings, link, script, JSON-LD, contatti, social profile, tech signals) per alimentare l'analisi di `/sales prospect`.

## Input attesi
- `--url <url>` (required): URL del sito aziendale da analizzare
- `--output json` (default): formato output
- `--timeout <secondi>` (default 10): timeout della richiesta HTTP

## Output prodotto
- JSON strutturato su stdout con: company metadata, technology stack detection, social media profile link, contact information pattern, SEO and traffic signal
- Consumato dall'orchestratore `sales-prospect` come parte del Discovery Briefing passato ai 5 sub-agenti

## Quando si invoca
- Phase 1.5 di `[[skill-operative/sales-prospect]]` come step di structured data extraction
- Anche standalone se serve solo il parsing strutturato di un sito senza l'intera pipeline
- Se fallisce, l'orchestratore prosegue con WebFetch manuale e logga l'errore

## Path sorgente
`ai-sales-manager/scripts/analyze_prospect.py`
