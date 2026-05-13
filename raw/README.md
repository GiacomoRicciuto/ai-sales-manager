---
type: raw-index
sezione: fonti-grezze
---

# raw/ — Fonti grezze

> **Regola d'oro: questo è il layer immutabile.** L'LLM legge da qui ma non modifica mai. È la source of truth. Tutto il resto del vault (entità, output, indice) deriva da queste fonti.

## Cosa va qui

| Sotto-cartella | Contenuto | Formato preferito |
|---------------|-----------|-------------------|
| `meetings/` | Trascrizioni di call e meeting (Fathom, Fireflies, Otter, Zoom AI) | `.md` con frontmatter |
| `email/` | Thread email convertiti in markdown | `.md` con frontmatter |
| `crm-export/` | Export dal CRM (HubSpot, Salesforce, Pipedrive) | `.csv`, `.json`, `.md` |
| `coaching/` | Sessioni di coaching interno rep-manager | `.md`, eventualmente con file audio in `assets/` |
| `materiali/` | Slide, brochure, contratti template, listini, case study esterni | `.pdf`, `.md`, `.pptx` |
| `assets/` | Immagini, allegati, screenshot, audio | binari |

## Cosa NON va qui
- Pagine generate dall'LLM (vanno in `10-Account/`, `20-Persone/`, `30-Trattative/`, `40-Interazioni/`, `50-Output/`)
- Note interne del rep scritte come riflessione (vanno come `nota` in `40-Interazioni/`)
- Bozze di copy (vanno in `50-Output/` con versionamento)

## Convenzione di naming
`YYYY-MM-DD-<sorgente>-<account-o-soggetto>.md`

Esempi:
- `meetings/2026-05-12-fathom-acme-discovery.md`
- `email/2026-05-13-thread-mario-rossi-proposta.md`
- `crm-export/2026-04-30-hubspot-pipeline-Q2.csv`
- `coaching/2026-05-10-giacomo-mariastella-mocking-objections.md`
- `materiali/2026-01-15-case-study-acme-energy.pdf`

## Frontmatter consigliato (su file .md)

```yaml
---
type: raw-source
sorgente: fathom | fireflies | otter | gmail | manual | hubspot | salesforce | other
data: 2026-05-12
account_collegato: [[../10-Account/acme-spa]]   # se identificato
persone_collegate:
  - [[../20-Persone/mario-rossi]]
trattativa_collegata: [[../30-Trattative/acme-rinnovo-2026]]
ingerito: false                                 # true dopo che la skill di ingestione l'ha processato
interazione_derivata: [[../40-Interazioni/2026-05-12-meeting-acme-discovery]]
---
```

## Flusso operativo

1. Una nuova fonte viene depositata in `raw/<sotto-cartella>/` (manualmente o via automazione: Fathom webhook, BCC email, drop file).
2. L'imprenditore (o un automatismo) dice all'LLM: "ingerisci questa nuova fonte".
3. L'LLM legge il file, lo analizza, crea/aggiorna le pagine wiki collegate (vedi workflow di Ingestione in `[[../CLAUDE]]`).
4. L'LLM aggiorna il frontmatter del file raw: `ingerito: true`, `interazione_derivata: [[...]]`.
5. La fonte raw resta lì per sempre, immutabile. Le pagine derivate possono evolvere ma puntano sempre indietro alla sorgente.

## Automazione (consigliata, non obbligatoria)

Le integrazioni più redditizie:
- **Fathom/Fireflies → `raw/meetings/`** via webhook o sync periodico
- **Gmail → `raw/email/`** via inoltro BCC a un endpoint che converte in `.md` con frontmatter
- **HubSpot/Salesforce → `raw/crm-export/`** export periodico (settimanale) per riconciliazione

Senza automazione, la qualità della wiki dipende dalla disciplina manuale di chi alimenta `raw/`.
