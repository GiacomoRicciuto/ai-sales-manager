---
type: layer-index
sezione: persone
---

# 20-Persone — Schede persone

> Una scheda per **ogni persona** rilevante per il business (buyer, champion, influencer, gatekeeper, ex-clienti). Una persona ha una sola scheda anche se passa da un'azienda a un'altra — l'azienda è un campo, la persona è l'entità primaria.

## Convenzione di naming
`<nome>-<cognome>.md` in kebab-case, traslitterando accenti e caratteri speciali.
- `mario-rossi.md`
- `lucia-bianchi.md`
- `jean-pierre-dupont.md`

In caso di omonimia, suffisso azienda: `mario-rossi-acme.md`.

## Frontmatter obbligatorio

```yaml
---
type: persona
nome: Mario Rossi
ruolo: CRO
azienda: [[../10-Account/acme-spa]]
autorita: decisore | influenzatore | utente | gatekeeper | champion | detractor
linkedin: https://linkedin.com/in/...
email: mario.rossi@acme.it    # opzionale, solo se condivisa esplicitamente
telefono:
status: attivo | dormiente | ex-cliente | non-ricontattare
lingue: [it, en]
fuso_orario: Europe/Rome
ultimo_touchpoint: 2026-05-12
---
```

## Struttura raccomandata del corpo

Vedi `[[_template-persona]]` per la scheda-tipo. Sezioni:
1. **Profilo professionale** — background, anni nel ruolo, percorso
2. **Autorità decisionale** — cosa decide davvero, vincoli (budget, gerarchia)
3. **Motivatori personali** — cosa lo muove (carriera, riconoscimento, sicurezza, missione)
4. **Stile di comunicazione** — formale/informale, sintetico/dettagliato, canale preferito
5. **Storia con noi** — quando l'abbiamo incontrato, in che contesti
6. **Interazioni** — link a `[[40-Interazioni/...]]` filtrate
7. **Tone matters** — frasi/argomenti che hanno funzionato, anti-pattern

## Regola di unicità
Una persona = una scheda. Se cambia azienda, aggiorna il campo `azienda:` e aggiungi una nota nella sezione "Storia con noi". NON duplicare.
