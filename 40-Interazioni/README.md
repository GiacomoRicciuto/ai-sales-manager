---
type: layer-index
sezione: interazioni
---

# 40-Interazioni — Touchpoint

> Una pagina **per ogni touchpoint** con un account: meeting, email significativa, call telefonica, sessione di coaching, nota osservativa. Append-only: si crea ma non si modifica. Quando arriva una nuova informazione su un touchpoint esistente, si crea un nuovo file di tipo `nota` che la corregge, lasciando traccia del cambiamento.

## Convenzione di naming
`YYYY-MM-DD-tipo-slug.md` — la data è quella del touchpoint, non della creazione del file.

Esempi:
- `2026-05-12-meeting-acme-discovery.md`
- `2026-05-13-email-mario-rossi-proposta.md`
- `2026-05-14-call-acme-followup.md`
- `2026-05-15-coaching-giacomo-acme-post-meeting.md`
- `2026-05-16-nota-acme-segnale-buying.md`

In caso di più touchpoint nello stesso giorno con lo stesso account, aggiungere suffisso ordinale: `-01`, `-02`.

## Tipi di interazione

| Tipo | Quando usarlo | Fonte raw tipica |
|------|---------------|------------------|
| `meeting` | Video/in-presenza con il prospect | `raw/meetings/...fathom.md` |
| `email` | Email significativa (non noise) | `raw/email/...md` |
| `call` | Telefonica out-of-meeting | trascrizione o nota rapida |
| `coaching` | Sessione interna rep-manager | `raw/coaching/...md` |
| `nota` | Osservazione del rep senza touchpoint esterno | scrittura diretta |

## Frontmatter obbligatorio

```yaml
---
type: interazione
formato: meeting | email | call | coaching | nota
data: 2026-05-12
durata_min:                       # opzionale, per meeting/call
account: [[../10-Account/acme-spa]]
persone:
  - [[../20-Persone/mario-rossi]]
  - [[../20-Persone/lucia-bianchi]]
trattativa: [[../30-Trattative/acme-rinnovo-2026]]
sales_rep: [[../00-Foundation/sales-rep/giacomo-ricciuto]]
fonte_raw: [[../raw/meetings/2026-05-12-fathom-acme.md]]
sentiment: positivo | neutro | negativo
next_step_concordato:
---
```

## Struttura del corpo

Vedi `[[_template-interazione]]`. Sezioni:
1. **Riassunto in 3-5 righe** (lead)
2. **Topic discussi** (bullet)
3. **Commitment presi** (chi promette cosa entro quando)
4. **Obiezioni emerse** (link a `[[00-Foundation/obiezioni/...]]`)
5. **Segnali di buying intent / risk**
6. **Quote testuali rilevanti** (estratte dalla fonte raw)
7. **Next step concordato**

## Regola di immutabilità (eccezione)
Le interazioni sono **append-only**. NON modificarle dopo la creazione. Se serve correggere/integrare, creare una nuova pagina `nota` che linka quella originale.
