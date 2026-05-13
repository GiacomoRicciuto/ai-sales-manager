---
type: foundation-index
sezione: sales-rep
status: TODO-imprenditore
---

# Profili Sales Rep

> **TODO imprenditore.** Una scheda per ogni rep del team (incluso te stesso se vendi). Le skill `sales-prep`, `sales-outreach`, `sales-followup` calibrano l'output sul **profilo** del rep: linguaggio, livello di scripting, leve preferite. Un brief per un junior sarà più scriptato; per un senior, più strategico.

## Convenzione di naming
`<nome>-<cognome>.md` in kebab-case — esempio: `giacomo-ricciuto.md`, `chiara-bianchi.md`.

Vedi `[[_template-rep]]` per la struttura completa.

## Cosa va in una scheda rep
1. **Frontmatter** — nome, ruolo, account assegnati, status
2. **Stile di vendita** — consultivo, challenger, relazionale, prezzo
3. **Punti di forza** — di cosa è bravo
4. **Gap formativi** — su cosa sta lavorando
5. **Account assegnati** — link a `[[10-Account/...]]`
6. **Note dal coaching** — link a `[[raw/coaching/...]]`
7. **Quota e performance** — quota mensile/trimestrale, attainment storico
8. **Preferenze operative** — orari migliori, canali preferiti, leve di chiusura

## Esempio frontmatter

```yaml
---
type: sales-rep
nome: Mario Rossi
ruolo: Senior AE
livello: senior | mid | junior
stile_vendita: consultivo | challenger | relazionale | transazionale
account_assegnati:
  - [[10-Account/acme-spa]]
  - [[10-Account/beta-srl]]
quota_eur_q: 250000
attainment_ytd: 110
status: attivo | onboarding | in-uscita
manager: [[giacomo-ricciuto]]
---
```

## Come le skill usano questo profilo

| Skill | Effetto del profilo rep |
|-------|------------------------|
| `sales-prep` | Junior → brief più scriptato con tracce di linguaggio; senior → brief strategico con leve di chiusura |
| `sales-outreach` | Adatta tono, lunghezza, livello di familiarità in apertura |
| `sales-followup` | Cadenza più aggressiva o più rilassata a seconda dello stile |
| `sales-objections` | Risposte autorizzate filtrate per livello |
| `sales-proposal` | Il rep assegnato firma; tono e profondità calibrati |

## Riferimenti
- `[[_template-rep]]` — scheda-tipo
- `[[../../00-Foundation/metodologie/skill-operative/sales-prep]]`
- `[[../../00-Foundation/metodologie/skill-operative/sales-outreach]]`
