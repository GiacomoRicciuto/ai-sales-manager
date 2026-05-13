---
type: layer-index
sezione: trattative
---

# 30-Trattative — Schede deal

> Una scheda per **ogni trattativa** (deal). Un account può avere più trattative aperte in parallelo (es. rinnovo + upsell). Una trattativa ha sempre **un account** e **un owner**.

## Convenzione di naming
`<slug-deal>.md` — combinazione `<slug-account>-<focus>-<anno>`:
- `acme-rinnovo-2026.md`
- `beta-srl-new-logo-q2.md`
- `gamma-upsell-modulo-x.md`

## Frontmatter obbligatorio

```yaml
---
type: trattativa
nome: ACME — Rinnovo enterprise 2026
account: [[../10-Account/acme-spa]]
owner: [[../00-Foundation/sales-rep/giacomo-ricciuto]]
stage: discovery | qualification | proposal | negotiation | closed-won | closed-lost
valore_eur: 45000
probabilita: 60               # 0-100
data_creazione: 2026-02-15
prossimo_step: 2026-05-19 — call di scoping
prossima_data: 2026-05-19
stakeholder:
  - [[../20-Persone/mario-rossi]]    # decisore
  - [[../20-Persone/lucia-bianchi]]  # champion
metodologia_attiva: [[../00-Foundation/metodologie/biblioteca-vendita/consultativa/lahoutifard-meddic]]
scenario: [[../00-Foundation/scenari/scenario-enterprise-rinnovo-annuale]]
offerta: [[../00-Foundation/offerte/pacchetto-pro-12-mesi]]
fonte_lead: outbound | referral | inbound | evento
data_chiusura_target: 2026-07-31
motivo_perso:                 # solo se closed-lost
---
```

## Struttura raccomandata del corpo

Vedi `[[_template-trattativa]]`. Sezioni:
1. **Sintesi 3 righe** — cosa si vende, a chi, in che stage
2. **Qualifica** — BANT / MEDDIC compilato
3. **Mappa stakeholder** — chi sostiene, chi blocca, chi è neutro
4. **Pain & valore** — il problema in parole del cliente + valore quantificato
5. **Storia (timeline)** — link cronologici alle interazioni
6. **Obiezioni emerse** — link a `[[00-Foundation/obiezioni/...]]`
7. **Competitor su questo deal**
8. **Next step concordato** — data, owner, output atteso
9. **Risk register** — cosa potrebbe far perdere il deal
10. **Output skill prodotti** — `[[50-Output/...]]`

## Regole pipeline

- Una trattativa con `stage:` non aggiornato da N giorni e `prossima_data:` nel passato = **in stallo**. La skill di lint la flagga.
- Quando passa a `closed-won` / `closed-lost`: NON cancellare. Aggiorna `motivo_perso` o `motivo_vinto` e mantieni la pagina come fonte storica per win/loss analysis.
