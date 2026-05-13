---
type: layer-index
sezione: account
---

# 10-Account — Schede aziende

> Una scheda per **ogni azienda-cliente** (prospect, attivo, churned). Le skill di prospect/research/qualify/prep/proposal aggiornano queste schede a ogni touchpoint. L'imprenditore non scrive: legge, segue i link, controlla la graph view.

## Convenzione di naming
`<slug-azienda>.md` in kebab-case. Esempi:
- `acme-spa.md`
- `beta-srl.md`
- `gamma-industries.md`

Niente prefisso numerico, niente date. La data di creazione resta nel frontmatter o nel `log.md`.

## Frontmatter obbligatorio

```yaml
---
type: account
nome: ACME Spa
sito: https://acme.it
settore: manifatturiero
dimensione: 50-200          # range dipendenti
fatturato_mln: 30           # M€, opzionale
geografia: Italia
icp_fit: alto | medio | basso
icp_match: [[../00-Foundation/icp/icp-enterprise-mid-market]]
owner: [[../00-Foundation/sales-rep/giacomo-ricciuto]]
status: prospect | attivo | cliente | churned | disqualified
fonte_lead: outbound | referral | inbound | evento
ultimo_touchpoint: 2026-05-12
prossima_azione: 2026-05-19 — call di scoping
trattative_attive:
  - [[../30-Trattative/acme-rinnovo-2026]]
persone_chiave:
  - [[../20-Persone/mario-rossi]]
  - [[../20-Persone/lucia-bianchi]]
---
```

## Struttura raccomandata del corpo

Vedi `[[_template-azienda]]` per la scheda-tipo. Sezioni:
1. **Overview** — chi sono, cosa fanno, dimensione, mercati
2. **Decision pattern** — chi decide, chi influenza, ciclo budget
3. **Pain points osservati** — quanto emerso dalle interazioni
4. **Tech stack / contesto operativo** (se rilevante)
5. **Competitor / fornitori attuali**
6. **Persone chiave** — link a `[[20-Persone/...]]`
7. **Trattative** — link a `[[30-Trattative/...]]`
8. **Interazioni** — storia cronologica con link `[[40-Interazioni/...]]`
9. **Output skill prodotti** — link a `[[50-Output/...]]`
10. **Contraddizioni / segnali rossi**

## Regola di immutabilità
La scheda account è **mutabile**: l'LLM la aggiorna a ogni nuovo touchpoint. Ma **mai** sovrascrivere silenziosamente un claim contraddetto — annotare in cima alla pagina un blocco `> [!warning] Contraddizione YYYY-MM-DD: ...` con link alle fonti in conflitto.
