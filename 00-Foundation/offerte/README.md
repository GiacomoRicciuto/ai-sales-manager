---
type: foundation-index
sezione: offerte
status: TODO-imprenditore
---

# Offerte — Catalogo

> **TODO imprenditore.** In questa cartella crea **una scheda per ogni offerta/prodotto/pacchetto** vendibile. Le skill `sales-proposal`, `sales-outreach`, `sales-qualify` leggono qui per costruire pitch e proposte personalizzate.

## Convenzione di naming
`<slug-offerta>.md` — esempio: `consulenza-strategica.md`, `pacchetto-pro-12-mesi.md`.

## Struttura attesa di ogni scheda offerta

```markdown
---
type: offerta
nome: Consulenza Strategica Trimestrale
slug: consulenza-strategica-trim
prezzo_base_eur: 12000
unita: trimestre
status: attiva | sospesa | legacy
target_icp: [[../icp/icp-enterprise-mid-market]]
---

# Consulenza Strategica Trimestrale

## Cosa include
- Bullet 1
- Bullet 2

## Outcome promesso
Una frase. Cosa porta a casa il cliente in 90 giorni.

## A chi NON è destinata
Anti-ICP per questa offerta specifica.

## Pricing
- Listino: 12.000 €
- Sconto massimo autorizzato: 10%
- Termini di pagamento: 30/60 giorni
- Upsell tipici: [[pacchetto-pro-12-mesi]]

## Proof points / case study
- Cliente X: risultato Y in Z mesi.

## Obiezioni ricorrenti
- Prezzo → vedi `[[../obiezioni/README]]`
- Tempistiche → ...

## Materiali
- Brochure: `[[raw/materiali/brochure-consulenza-2026.pdf]]`
- One-pager: `[[raw/materiali/one-pager-consulenza.md]]`
```

## Esempio compilato fittizio
*(Compilare con materiali reali. Le skill si appoggiano alle offerte attive.)*

TODO — popolare almeno 1 offerta prima di usare `/sales proposal`.

## Riferimenti
- `[[../azienda/posizionamento]]` — USP
- `[[../icp/README]]` — chi compra cosa
- `[[../../00-Foundation/metodologie/skill-operative/sales-proposal]]` — skill che usa queste schede
