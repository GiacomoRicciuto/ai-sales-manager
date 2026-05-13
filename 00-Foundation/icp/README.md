---
type: foundation-index
sezione: icp
status: TODO-imprenditore
---

# ICP — Ideal Customer Profile

> **TODO imprenditore.** Crea **una scheda per ogni segmento ICP** che vendi. Il vendor può avere 1 ICP unico o 2-3 segmenti distinti (es. enterprise vs SMB). La skill `sales-icp` aggiorna queste schede a partire dai closed-won; le skill `sales-prospect`, `sales-qualify`, `sales-outreach` filtrano contro queste schede.

## Convenzione di naming
`icp-<slug-segmento>.md` — esempio: `icp-enterprise-mid-market.md`, `icp-smb-saas.md`.

## Struttura attesa di ogni scheda ICP

```markdown
---
type: icp
nome: ICP Enterprise Mid-Market
slug: icp-enterprise-mid-market
status: attivo | in-test | retired
ultima-revisione: 2026-05-12
---

# ICP Enterprise Mid-Market

## Firmografici
- Settore: manifatturiero, energia, healthcare
- Dipendenti: 200-2000
- Fatturato: 50M-500M €
- Geografia: Italia, DACH
- Forma giuridica: Spa, GmbH, SE

## Tecnografici (se applicabile)
- Stack: SAP, Salesforce, on-prem
- Maturità digitale: media-alta
- Compliance: ISO27001, GDPR

## Trigger di buying intent
- Cambio CFO / CRO negli ultimi 6 mesi
- Round di funding o acquisizione
- Espansione internazionale
- Migrazione tecnologica annunciata

## Decision pattern
- Decisore: CRO / Head of Sales / COO
- Influencer: RevOps, IT, Finance
- Tempi di chiusura: 3-9 mesi
- Cicli di budget: settembre, gennaio

## Pain points dominanti
- Pain 1 — sintomo / radice / costo annuo non risolto
- Pain 2 — ...

## Anti-ICP (chi escludere)
- Aziende <50 dipendenti
- Settori regolamentati senza budget consulenza esterna
- Founder-led senza COO

## Offerte applicabili
- `[[../offerte/consulenza-strategica]]`
- `[[../offerte/pacchetto-pro-12-mesi]]`

## Casi vinti rappresentativi
- `[[10-Account/cliente-rappresentativo-1]]`
- `[[10-Account/cliente-rappresentativo-2]]`
```

## Riferimenti
- `[[../../00-Foundation/metodologie/skill-operative/sales-icp]]` — skill che mantiene queste schede
- `[[../../00-Foundation/metodologie/biblioteca-vendita/sistemica/ross-predictable-revenue]]` — ICP come fondamento dell'outbound
- `[[../../00-Foundation/metodologie/biblioteca-vendita/etica/godin-this-is-marketing]]` — "smallest viable market"
