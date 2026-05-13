---
type: foundation-index
sezione: scenari
status: TODO-imprenditore
---

# Scenari di vendita tipici

> **TODO imprenditore.** Uno scenario è un *pattern ricorrente di trattativa*: combinazione di tipo cliente, offerta venduta, durata ciclo, decision pattern. Documentare gli scenari aiuta le skill a riconoscere subito "questo deal assomiglia a X" e applicare il playbook giusto.

## Convenzione di naming
`scenario-<slug>.md` — esempio: `scenario-enterprise-rinnovo-annuale.md`, `scenario-smb-quick-close-30gg.md`, `scenario-multi-stakeholder-procurement.md`.

## Struttura attesa di ogni scheda scenario

```markdown
---
type: scenario
nome: Enterprise rinnovo annuale
slug: scenario-enterprise-rinnovo-annuale
durata_tipica_giorni: 60
valore_medio_eur: 80000
probabilita_close_storica: 75
---

# Enterprise rinnovo annuale

## Caratteristiche
- ICP: `[[../icp/icp-enterprise-mid-market]]`
- Offerta tipica: `[[../offerte/pacchetto-pro-12-mesi]]`
- Stakeholder coinvolti: 3-5 (CRO, CFO, IT, Procurement, Champion interno)
- Trigger: scadenza contratto, Q4 budget review

## Stage tipici
1. Discovery — ricontatto champion, verifica continuità ICP
2. Qualification — MEDDIC light (il deal storico è già qualificato)
3. Proposal — proposta con upsell modulare
4. Negotiation — sconto volume max -8%
5. Close — firma entro fine Q

## Obiezioni storiche
- `[[../obiezioni/obiezione-prezzo-troppo-alto]]` (frequenza alta)
- `[[../obiezioni/obiezione-roi-non-chiaro]]` (frequenza media)

## Metodologie da applicare
- `[[../../00-Foundation/metodologie/biblioteca-vendita/consultativa/lahoutifard-meddic]]` — qualifica
- `[[../../00-Foundation/metodologie/biblioteca-vendita/consultativa/miller-heiman-strategic-selling]]` — mappa stakeholder
- `[[../../00-Foundation/metodologie/biblioteca-vendita/sistemica/coleman-never-lose-customer-again]]` — retention

## Casi storici
- `[[30-Trattative/...]]`
- `[[30-Trattative/...]]`
```

## Riferimenti
- `[[../icp/README]]`
- `[[../offerte/README]]`
- `[[../../00-Foundation/metodologie/skill-operative/sales-prep]]`
