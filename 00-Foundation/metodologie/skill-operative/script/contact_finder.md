---
type: script
nome: contact_finder.py
linguaggio: python
chiamato-da: [[skill-operative/sales-contacts]]
---

# contact_finder.py

## Scopo
Estrae leadership e team information da pagine web aziendali (team, about, leadership, people). Classifica ogni persona trovata per seniority (C-Suite / VP / Director / Manager / IC), department (Engineering, Sales, Marketing, Product, Operations, Finance, HR, Legal, Customer Success) e buying role (Economic Buyer, Technical Buyer, User Buyer, Champion, Blocker).

## Input attesi
- `--url <url>` (required): URL del sito aziendale
- `--output json` (default): formato output
- Path scansionati automaticamente: `/about`, `/team`, `/leadership`, `/our-team`, `/people`, `/about-us`, `/company/team`, `/company/leadership`, `/staff`

## Output prodotto
- JSON con lista contatti: `{name, title, seniority, department, buying_role, source_url}`
- Eventuali link LinkedIn estratti dalla bio
- Email pattern detection se disponibile

## Quando si invoca
- Dentro `[[skill-operative/sales-contacts]]` come step deterministico iniziale di estrazione, prima della LinkedIn research manuale
- Anche standalone per arricchimento veloce di una scheda account
- Utile in workflow di hand-off per pre-popolare le schede in `[[20-Persone/...]]`

## Path sorgente
`ai-sales-manager/scripts/contact_finder.py`
