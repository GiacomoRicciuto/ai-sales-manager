# ONBOARDING — Primi 7 giorni con la wiki

Una guida concreta per portare la wiki da "scheletro vuoto" a "operativa con dati reali" senza saltare passaggi.

Tempo stimato: **3-5 ore di lavoro effettivo dell'imprenditore**, distribuite su una settimana.

---

## Giorno 1 — Apri il vault e leggi lo schema (30 min)

1. Apri Obsidian → "Open folder as vault" → scegli `vault/`.
2. Imposta in Obsidian: Impostazioni → File e link → "Cartella allegati" = `raw/assets/`.
3. (Opzionale ma raccomandato) Installa i plugin Obsidian: **Dataview**, **Templater**, **Marp**.
4. Leggi `[[README]]` (questo è il punto di ingresso umano).
5. Leggi `[[CLAUDE]]` — soprattutto le sezioni 4 (Convenzioni), 5 (Workflow Ingestione), 6 (Workflow Interrogazione). Sono il contratto.
6. Sfoglia il `[[index]]` per vedere cosa c'è già caricato.

**Esito atteso**: hai un'idea chiara dell'architettura e sai dove leggere per ogni domanda.

---

## Giorno 2 — Fondazione azienda (45 min)

Compila i 4 file dentro `00-Foundation/azienda/`:

1. `[[00-Foundation/azienda/overview]]` — chi siete, numeri base, canali.
2. `[[00-Foundation/azienda/posizionamento]]` — USP, anti-ICP, claim.
3. `[[00-Foundation/azienda/tono-di-voce]]` — voce in 3 aggettivi, lessico preferito/vietato.
4. `[[00-Foundation/azienda/valori]]` — manifesto, principi, cosa rifiutate.

**Trucco**: se hai già un brand book, una sales page, una pitch deck — caricali in `raw/materiali/` e chiedi a Claude Code: *"leggi i materiali in `raw/materiali/` e proponimi una bozza dei 4 file `00-Foundation/azienda/*` da approvare prima di scriverli"*.

**Esito atteso**: ogni `/sales outreach`, `/sales prep`, `/sales proposal` ora ha contesto vendor.

---

## Giorno 3 — Offerte e ICP (60 min)

1. In `00-Foundation/offerte/` crea **almeno una scheda offerta** seguendo `[[00-Foundation/offerte/README]]`. Se hai 3-5 offerte, falle tutte: vale l'investimento.
2. In `00-Foundation/icp/` crea **almeno un ICP** seguendo `[[00-Foundation/icp/README]]`. Anche qui: se vendi a 2-3 segmenti distinti, fai una scheda per ognuno.

**Trucco**: se hai uno storico di clienti (anche solo 10-20 nomi vinti negli ultimi 2 anni), caricalo in `raw/crm-export/` e chiedi: *"analizza questi clienti vinti e proponi un ICP basato sui pattern reali"*. Poi raffinalo a mano.

**Esito atteso**: `/sales qualify` può ora misurare i prospect contro un ICP reale, e `/sales icp` può aggiornarlo nel tempo.

---

## Giorno 4 — Profili sales rep (30 min)

In `00-Foundation/sales-rep/`:

1. Crea il **tuo** profilo (`<tuo-nome>-<cognome>.md`) partendo da `[[00-Foundation/sales-rep/_template-rep]]`.
2. Se hai un team, crea una scheda per ogni rep. Anche solo le sezioni di base: stile, livello, account assegnati.

**Esito atteso**: le skill calibrano l'output sul singolo rep (junior vs senior, consultivo vs challenger).

---

## Giorno 5 — Carica materiali esistenti (45 min)

In `raw/materiali/` deposita tutto quello che hai già:
- Brochure, one-pager, case study
- Slide di pitch / vendita
- Listini, contratti template
- White paper, lead magnet, articoli del tuo blog

Niente di tutto questo va riscritto. Vivono in `raw/` e le skill li pescano al bisogno.

In `raw/coaching/` (se applicabile) carica eventuali sessioni di coaching registrate o trascritte.

**Esito atteso**: il "background knowledge" del vendor è loadabile.

---

## Giorno 6 — Primi account e prima ingestione (60-90 min)

Scegli **3-5 account** su cui stai lavorando attivamente (i più caldi). Per ognuno:

1. Crea una scheda in `10-Account/<slug>.md` partendo da `[[10-Account/_template-azienda]]`. Compila almeno il frontmatter — il corpo si auto-popola con l'ingestione.
2. Se conosci persone specifiche, crea le schede in `20-Persone/`.
3. Se ci sono trattative aperte, crea le schede in `30-Trattative/`.
4. Carica le trascrizioni meeting recenti (Fathom, Fireflies) di questi account in `raw/meetings/`.
5. Da Claude Code: *"ingerisci `raw/meetings/<file>` e aggiorna le schede collegate"*.

Osserva cosa fa l'LLM: leggi le pagine aggiornate, controlla che il frontmatter sia corretto, segui i link.

**Esito atteso**: hai 3-5 account "vivi" nella wiki, con storia recente e prossimi step chiari.

---

## Giorno 7 — Prima skill e primo health-check (45 min)

1. Scegli un account con un meeting imminente.
2. Da Claude Code: `/sales prep <slug-account>`. Leggi il brief in `50-Output/`.
3. Vai al meeting con il brief. Annota cosa ha funzionato, cosa no.
4. Dopo il meeting: carica la nuova trascrizione → ingerisci → osserva l'aggiornamento delle pagine.
5. Lancia un health-check: *"fai un lint della wiki, dimmi cosa manca, dove ci sono contraddizioni, quali deal sono in stallo"*.

**Esito atteso**: hai chiuso il primo ciclo completo Ingestione → Interrogazione → Lint. Da qui in poi è ripetizione.

---

## Come capire se la wiki è "sana"

Dopo 2-3 settimane di uso reale, una wiki sana ha:

- ✓ Almeno 10 account con schede compilate e storia di interazioni
- ✓ Ogni account caldo ha almeno 3 touchpoint linkati
- ✓ Ogni trattativa aperta ha un `prossimo_step` con data futura
- ✓ La graph view mostra cluster (azienda + persone + trattative + interazioni connesse), non puntini isolati
- ✓ Il `log.md` ha voci frequenti (almeno 2-3/settimana)
- ✓ Il `50-Output/` cresce: stai effettivamente usando le skill

Una wiki **malata**:
- ✗ Account orfani (zero persone, zero interazioni)
- ✗ Trattative ferme nello stesso stage da 30+ giorni senza nuove interazioni
- ✗ Tante schede TODO compilate a metà
- ✗ `log.md` con poche voci → vuol dire che non stai ingerendo abbastanza

Il lint te lo segnala. Lancialo ogni settimana.

---

## Errori da evitare

1. **Scrivere a mano nelle pagine wiki**. NO. L'LLM scrive, tu leggi. Se vuoi annotare qualcosa, crea una `nota` in `40-Interazioni/`.
2. **Dimenticarti di ingerire le trascrizioni vecchie**. Se non sono in `raw/`, non esistono per l'LLM.
3. **Saltare la fondazione**. Senza azienda + offerta + ICP compilati, le skill producono output generici → output generici sono peggio di nessun output.
4. **Modificare file in `raw/`**. Sono immutabili. Se devi correggere una trascrizione, crea una `nota` che annota la correzione.
5. **Non versionare**. `git init` su `vault/` (o sull'intera `llm-wiki-sales/`) e commit regolari. Sei un passo dal rollback ogni volta che serve.

---

## Cosa fare quando…

| Situazione | Comando da dare all'LLM |
|------------|-------------------------|
| Ho una nuova trascrizione Fathom | "Ingerisci `raw/meetings/<file>`" |
| Devo prepararmi a una call domani | "/sales prep `<slug-account>`" |
| Ho ricevuto un'obiezione strana | "/sales objections `<descrizione>` per `<slug-account>`" |
| Devo scrivere una proposta | "/sales proposal `<slug-trattativa>`" |
| Voglio sapere lo stato pipeline | "/sales report" |
| Voglio fare check di salute wiki | "Lint della wiki" |
| Un deal contraddice qualcosa di vecchio | L'LLM lo segnala in automatico — leggi il blocco `> [!warning]` nella scheda account |

---

## Riferimenti

- `[[CLAUDE]]` — schema operativo (la bibbia di sessione)
- `[[index]]` — catalogo navigabile
- `[[00-Foundation/metodologie/skill-operative/README]]` — registro delle 14 skill
- `[[00-Foundation/metodologie/biblioteca-vendita/README]]` — 44 schede-libro
- `[[00-Foundation/metodologie/meta/llm-wiki-pattern]]` — bibbia primaria del pattern
