---
type: layer-index
sezione: output-skill
---

# 50-Output — Artefatti generati dalle skill

> Ogni esecuzione di una skill commerciale produce un artefatto: brief di preparazione, sequenza follow-up, proposta, playbook obiezioni, analisi competitiva, report di pipeline. **Tutti questi artefatti vanno archiviati qui**, oltre che restituiti in chat. Un output non archiviato è capitale di conoscenza perso.

## Convenzione di naming
`YYYY-MM-DD-<skill-slug>-<oggetto>.md` — la data è quella di esecuzione della skill.

Esempi:
- `2026-05-12-prep-acme-spa.md`
- `2026-05-13-outreach-beta-srl.md`
- `2026-05-14-proposal-gamma-rinnovo-2026.md`
- `2026-05-15-objection-playbook-prezzo-acme.md`
- `2026-05-16-competitive-intel-delta.md`
- `2026-05-30-pipeline-report.md`

I PDF (es. da `sales-report-pdf`) seguono lo stesso pattern: `YYYY-MM-DD-pipeline-report.pdf`.

## Frontmatter obbligatorio

```yaml
---
type: output-skill
skill: sales-prep | sales-outreach | sales-proposal | sales-objections | sales-competitors | sales-report | ...
data: 2026-05-12
account: [[../10-Account/acme-spa]]
trattativa: [[../30-Trattative/acme-rinnovo-2026]]
persone_destinatarie:
  - [[../20-Persone/mario-rossi]]
sales_rep: [[../00-Foundation/sales-rep/giacomo-ricciuto]]
input_usati:
  - [[../40-Interazioni/2026-05-10-meeting-acme-discovery]]
  - [[../40-Interazioni/2026-05-08-email-mario-budget]]
  - [[../00-Foundation/icp/icp-enterprise-mid-market]]
metodologie_applicate:
  - [[../00-Foundation/metodologie/biblioteca-vendita/consultativa/rackham-spin-selling]]
  - [[../00-Foundation/metodologie/biblioteca-vendita/negoziazione/voss-never-split]]
versione: 1
---
```

## Versionamento
Se un output viene rigenerato (es. il prospect cambia le condizioni e la proposta va riscritta), creare un nuovo file con `versione: 2` invece di sovrascrivere. Linkare la versione precedente in una sezione "Storico versioni".

## Sotto-cartelle (opzionali, se il volume cresce)
Se il volume di output supera ~200 file, valutare sotto-cartelle per skill: `50-Output/prep/`, `50-Output/proposal/`, etc. Per ora mantenere flat.

## Link bidirezionale
Ogni output DEVE essere linkato:
- Dalla trattativa (`30-Trattative/...`) nella sezione "Output skill prodotti"
- Dall'account (`10-Account/...`)
- Da `[[../index]]` nella sezione output
