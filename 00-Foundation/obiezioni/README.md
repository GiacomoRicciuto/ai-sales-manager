---
type: foundation-index
sezione: obiezioni
status: TODO-imprenditore
---

# Playbook obiezioni — Cross-deal

> **TODO imprenditore.** Qui vivono le obiezioni **ricorrenti** che si ripetono su più trattative. Le obiezioni specifiche di un singolo deal stanno dentro la pagina di quella trattativa. La skill `sales-objections` legge qui per produrre il playbook contestualizzato; la skill di lint cataloga obiezioni nuove emerse dai meeting.

## Convenzione di naming
Una scheda per obiezione: `obiezione-<slug>.md` — esempio: `obiezione-prezzo-troppo-alto.md`, `obiezione-non-e-il-momento.md`, `obiezione-abbiamo-gia-fornitore.md`.

## Struttura attesa di ogni scheda obiezione

```markdown
---
type: obiezione
nome: "Prezzo troppo alto rispetto al concorrente"
categoria: prezzo | tempo | autorita | bisogno | fiducia | concorrente | rischio
stadio_emerge: discovery | qualification | proposal | negotiation
frequenza: alta | media | bassa
metodologie: [[../../00-Foundation/metodologie/biblioteca-vendita/negoziazione/voss-never-split]]
---

# "Prezzo troppo alto rispetto al concorrente"

## Cosa stanno davvero dicendo
*(L'obiezione di superficie vs. la causa profonda. Cialdini, Voss e Sandler insegnano a non rispondere alla superficie.)*

## Domande di esplorazione (non risposte premature)
- Domanda 1
- Domanda 2

## Risposte autorizzate
*(Versioni approvate dall'imprenditore. Differenziate per rep junior vs senior.)*

### Versione breve (junior)
TODO

### Versione strategica (senior)
TODO

## Proof points da agganciare
- Case study `[[10-Account/...]]`
- Numero / ROI dimostrabile

## Quando disqualificare invece di rispondere
*(Se la causa profonda è anti-ICP, non insistere.)*

## Storico — deal dove è emersa
*(Auto-popolato dalle interazioni che linkano questa obiezione.)*

- `[[40-Interazioni/2026-05-12-meeting-acme-discovery]]`
```

## Categorie operative (canonico)
- **Prezzo** — troppo caro, non ho budget
- **Tempo** — non è il momento, troppo lungo da implementare
- **Autorità** — devo parlare con il mio capo / board
- **Bisogno** — non vedo il problema, ce la caviamo con quello che abbiamo
- **Fiducia** — non vi conosciamo, non avete referenze nel nostro settore
- **Concorrente** — abbiamo già un fornitore, abbiamo valutato altri
- **Rischio** — implementazione troppo invasiva, contratto troppo lungo

## Riferimenti — metodologie chiave
- `[[../../00-Foundation/metodologie/biblioteca-vendita/negoziazione/voss-never-split]]` — labeling, mirroring, no
- `[[../../00-Foundation/metodologie/biblioteca-vendita/negoziazione/ury-getting-past-no]]` — strategia breakthrough
- `[[../../00-Foundation/metodologie/biblioteca-vendita/psico/cialdini-influence]]` — principi di influenza
- `[[../../00-Foundation/metodologie/biblioteca-vendita/consultativa/sandler-cant-teach-a-kid]]` — pain funnel
- `[[../../00-Foundation/metodologie/skill-operative/sales-objections]]` — skill che genera playbook su misura
- `[[../../00-Foundation/metodologie/skill-operative/template/objection-playbook]]` — template skill
