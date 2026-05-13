---
type: schema
ruolo: configurazione-llm
lingua: it
ultima-revisione: 2026-05-12
---

# CLAUDE.md — Schema del vault commerciale

> Questo file è il **contratto operativo** tra l'LLM (Claude Code, Claude Desktop via Obsidian MCP, agenti) e la wiki. Va letto in apertura di ogni sessione e rispettato come specifica.

> **Pre-lettura obbligatoria insieme a questo file:** [[MCP-GUIDE]] — guida operativa al vault e ai 14 tool MCP, con mappatura intenti-vaghi → skill e workflow base. Senza averla letta non agire: rischi di rispondere da memoria invece che dal vault, o di sbagliare i tool MCP nei loro caveat noti.

---

## 1. Mission

Questo vault è una **knowledge base commerciale persistente** istanziata secondo il pattern descritto in `[[llm-wiki-pattern]]` (bibbia primaria, italiana) e `[[llm-wiki-original]]` (bibbia secondaria, originale in inglese). Si frappone tra le fonti grezze del team commerciale (trascrizioni Fathom/Fireflies, thread email, export CRM, sessioni di coaching, materiali) e l'imprenditore/team che pone domande e lancia skill operative. La wiki **compila la conoscenza una volta sola e la mantiene corrente**: cross-reference fra account, persone, trattative, interazioni; coerenza nel tono di voce; integrazione tra metodologie di vendita teoriche (`[[biblioteca-vendita/README]]`) e skill tattiche del progetto `ai-sales-manager` (`[[skill-operative/README]]`).

L'LLM scrive e mantiene la wiki. L'umano cura le fonti, esplora, e pone le domande. Lingua: italiano (anglicismi standard di settore — lead, deal, pipeline, stage, follow-up, ICP, frontmatter — conservati).

## 2. Architettura — tre layer

1. **Fonti grezze** (`raw/`): immutabili. L'LLM legge ma non modifica mai. Trascrizioni, email, export CRM, materiali, coaching.
2. **Wiki** (`00-Foundation/`, `10-Account/`, `20-Persone/`, `30-Trattative/`, `40-Interazioni/`, `50-Output/`): markdown generato dall'LLM. L'LLM possiede questo layer interamente.
3. **Schema** (questo file `CLAUDE.md`): configura il comportamento dell'LLM. Co-evolve nel tempo con l'imprenditore.

## 3. Mappa cartelle

```
vault/
├── CLAUDE.md                # questo schema
├── README.md                # intro umana
├── ONBOARDING.md            # guida pratica per l'imprenditore
├── index.md                 # catalogo navigabile (content-oriented)
├── log.md                   # registro cronologico append-only
│
├── 00-Foundation/           # conoscenza che cambia raramente
│   ├── azienda/             # chi siamo, positioning, tono, valori
│   ├── offerte/             # prodotti, pacchetti, pricing
│   ├── icp/                 # Ideal Customer Profile
│   ├── funnel/              # funnel marketing, materiali
│   ├── obiezioni/           # playbook obiezioni cross-deal
│   ├── scenari/             # scenari di vendita tipici
│   ├── sales-rep/           # profili rep del team
│   └── metodologie/
│       ├── skill-operative/ # 14 skill sales-* + 5 agenti + 4 script + 6 template
│       ├── biblioteca-vendita/ # 44 schede-libro per famiglia
│       └── meta/            # bibbie del pattern wiki
│
├── 10-Account/              # una scheda per azienda-cliente
├── 20-Persone/              # una scheda per persona
├── 30-Trattative/           # una scheda per deal
├── 40-Interazioni/          # un file per touchpoint (append-only)
├── 50-Output/               # artefatti generati dalle skill
│
└── raw/                     # fonti grezze immutabili
    ├── meetings/            # trascrizioni
    ├── email/               # thread email in .md
    ├── crm-export/          # CSV/JSON/MD
    ├── coaching/            # sessioni coaching
    ├── materiali/           # slide, brochure, contratti
    └── assets/              # immagini, allegati
```

## 4. Convenzioni — applicarle ovunque

### 4.1 Lingua

Tutte le pagine sono in **italiano**. Conservare anglicismi di settore (lead, deal, pipeline, stage, touchpoint, follow-up, ICP, BANT, MEDDIC, frontmatter, churn, ARR, USP, pitch, discovery, qualification, proposal, negotiation, closed-won/lost).

### 4.2 Naming

| Tipo | Pattern | Esempio |
|------|---------|---------|
| Pagine fondazione | `kebab-case` | `sales-prep.md`, `cialdini-influence.md` |
| Account | `kebab-case` slug azienda | `acme-spa.md` |
| Persone | `kebab-case` nome-cognome | `mario-rossi.md` |
| Trattative | `kebab-case` slug-deal | `acme-rinnovo-2026.md` |
| Interazioni | `YYYY-MM-DD-tipo-slug` | `2026-05-12-meeting-acme-discovery.md` |
| Output skill | `YYYY-MM-DD-skill-slug` | `2026-05-12-prep-acme.md` |

### 4.3 Frontmatter YAML — obbligatorio su ogni pagina entità

**Account** (`10-Account/*.md`)
```yaml
---
type: account
nome: ACME Spa
sito: https://acme.it
settore: manifatturiero
dimensione: 50-200
icp_fit: alto | medio | basso
owner: [[sales-rep/giacomo-ricciuto]]
status: prospect | attivo | cliente | churned
ultimo_touchpoint: 2026-05-12
prossima_azione: 2026-05-19
---
```

**Persona** (`20-Persone/*.md`)
```yaml
---
type: persona
nome: Mario Rossi
ruolo: CRO
azienda: [[10-Account/acme-spa]]
autorita: decisore | influenzatore | utente | gatekeeper
linkedin: https://linkedin.com/in/...
---
```

**Trattativa** (`30-Trattative/*.md`)
```yaml
---
type: trattativa
nome: ACME — Rinnovo enterprise 2026
account: [[10-Account/acme-spa]]
owner: [[sales-rep/giacomo-ricciuto]]
stage: discovery | qualification | proposal | negotiation | closed-won | closed-lost
valore_eur: 45000
probabilita: 60
prossimo_step: 2026-05-19 — call di scoping
metodologia_attiva: [[biblioteca-vendita/consultativa/lahoutifard-meddic]]
---
```

**Interazione** (`40-Interazioni/*.md`)
```yaml
---
type: interazione
formato: meeting | email | call | coaching | nota
data: 2026-05-12
account: [[10-Account/acme-spa]]
persone: [[20-Persone/mario-rossi]]
trattativa: [[30-Trattative/acme-rinnovo-2026]]
sales_rep: [[sales-rep/giacomo-ricciuto]]
fonte_raw: [[raw/meetings/2026-05-12-fathom-acme.md]]
---
```

### 4.4 Link

- Sempre `[[wiki-link]]` di Obsidian per riferimenti interni. **Mai** path relativi né URL per navigazione interna.
- Linkare aggressivamente:
  - Una scheda account DEVE linkare tutte le persone, trattative, interazioni collegate.
  - Una scheda interazione DEVE linkare azienda + persone + trattativa + fonte raw.
  - Una scheda libro della biblioteca DEVE linkare almeno una skill operativa rilevante (e viceversa).

### 4.5 Tono

Conciso, operativo. Niente emoji. Niente preamboli ("Ecco la scheda…"). Niente disclaimer. Lo stile del vault è di un sales operator italiano esperto: diretto, evidence-based, no fronzoli.

## 5. Workflow — Ingestione

Quando l'imprenditore (o un sistema automatico) deposita una nuova fonte in `raw/`:

1. **Leggi la fonte integralmente** (la trascrizione, l'email, l'export).
2. **Identifica le entità menzionate**: aziende, persone, trattative. Per ognuna verifica se esiste già la scheda corrispondente in `10-Account/`, `20-Persone/`, `30-Trattative/`. Usa `index.md` come catalogo.
3. **Discuti con l'umano i passaggi chiave** (cosa ha detto il prospect, commitment presi, obiezioni emerse, next step concordato). Una singola fonte può toccare 10-15 pagine.
4. **Crea la pagina-interazione** in `40-Interazioni/YYYY-MM-DD-tipo-slug.md` con frontmatter completo e link a fonte raw.
5. **Aggiorna le entità collegate**:
   - Scheda account: aggiorna `ultimo_touchpoint`, `prossima_azione`, status se cambiato.
   - Scheda persona: conferma/raffina ruolo, autorità, motivatori personali.
   - Scheda trattativa: aggiorna `stage`, `valore_eur`, `probabilita`, `prossimo_step`. Segnala se un claim contraddice qualcosa già scritto.
6. **Segnala contraddizioni**: se la nuova fonte contraddice un claim precedente, NON sovrascrivere silenziosamente — annota nella pagina dell'entità una nota tipo `> [!warning] Contraddizione 2026-05-12: in [[2026-05-12-meeting-acme-discovery]] il budget dichiarato è 50k, mentre in [[2026-04-20-email-mario-budget]] era 30k.`
7. **Aggiorna `index.md`** con i nuovi link e i metadati cambiati.
8. **Appendi una voce a `log.md`** nel formato `## [YYYY-MM-DD] ingest | <fonte> — <slug>`.

## 6. Workflow — Interrogazione

Quando l'imprenditore pone una domanda o invoca una skill commerciale:

1. **Leggi `index.md`** per individuare le pagine rilevanti.
2. **Carica il contesto necessario** dalla wiki:
   - Schede entità coinvolte (account, persone, trattativa).
   - Ultimo storico interazioni (`40-Interazioni/` filtrate per quella trattativa).
   - Fondazione applicabile: scheda azienda dell'imprenditore, offerta, ICP, profilo rep assegnato.
   - Skill operativa pertinente (`00-Foundation/metodologie/skill-operative/`).
   - Metodologie di vendita rilevanti (`biblioteca-vendita/`) — minimo una per query strategica.
3. **Produci l'output situato**: niente template generici, tutto deve essere contestualizzato al lead specifico, al rep specifico, allo stage specifico.
4. **Archivia l'output in `50-Output/`** se è un artefatto riusabile (brief di preparazione, sequenza follow-up, proposta, script obiezioni, analisi competitiva). Nominalo `YYYY-MM-DD-<skill>-<slug>.md`. Linkalo da `index.md` e dalla trattativa relativa.
5. **Appendi a `log.md`** la voce `## [YYYY-MM-DD] query | <skill o domanda> — <output>`.

### Mapping skill operative → input richiesti dalla wiki

| Skill | Carica obbligatoriamente |
|-------|--------------------------|
| `/sales prospect` | scheda account (se esiste), ICP, scheda azienda, profilo rep |
| `/sales research` | scheda account corrente o vuota; ICP per filtro |
| `/sales qualify` | scheda account + persone + interazioni recenti |
| `/sales contacts` | scheda account + persone già mappate |
| `/sales prep` | scheda account + persone + ultima trattativa + ultime 3 interazioni + obiezioni storiche + scheda offerta + profilo rep |
| `/sales outreach` | scheda account + persona destinataria + ICP + scheda offerta + tono-di-voce |
| `/sales objections` | obiezioni storiche del deal/account + playbook fondazione + libri pertinenti (Voss, Sandler, Cialdini) |
| `/sales proposal` | trattativa + qualifica + competitive intel + offerta + tono-di-voce |
| `/sales followup` | ultime interazioni + commitment presi + trattativa attiva |
| `/sales report` | tutte le trattative attive con frontmatter pipeline |
| `/sales competitors` | scheda account + competitive intel storica |
| `/sales icp` | scheda azienda + offerta + storico clienti firmati (closed-won) |

## 7. Workflow — Lint (revisione periodica)

Su richiesta esplicita (`/lint`, "fai un health-check"), l'LLM scansiona la wiki cercando:

- **Contraddizioni** tra pagine (es. budget dichiarato diverso in due interazioni della stessa trattativa).
- **Claim obsoleti** superati da touchpoint più recenti ma non aggiornati nella scheda entità.
- **Lead orfani**: account senza persone collegate, persone senza account, trattative senza interazioni.
- **Persone fantasma**: menzionate in interazioni o trattative senza scheda propria in `20-Persone/`.
- **Account fantasma**: citati ma privi di scheda in `10-Account/`.
- **Follow-up scaduti**: trattative con `prossimo_step` data nel passato e nessuna nuova interazione.
- **Deal in stallo**: stessa `stage` da più di N giorni senza nuove interazioni (N configurabile — default 21).
- **Missing cross-reference**: entità citate in testo ma non linkate `[[…]]`.
- **Gap informativi colmabili** con ricerca web (LinkedIn, sito aziendale, news, segnali di buying intent).

Produce un report in `50-Output/YYYY-MM-DD-lint.md` con problemi categorizzati e azioni suggerite.

## 8. Regole di output — sempre

- Ogni artefatto skill-generato va **sia** restituito in chat **sia** archiviato in `50-Output/` con frontmatter `type: output-skill`, `skill: <nome>`, `data:`, `account:`, `trattativa:`.
- Un output non archiviato è una perdita di capitale di conoscenza.
- I report PDF generati da `sales-report-pdf` vanno in `50-Output/` con il nome originale ma datati.

## 9. Skill operative — registro

L'orchestratore `[[skill-operative/sales]]` instrada i comandi `/sales <subcommand>` alle 13 skill specialistiche. Vedi `[[skill-operative/README]]` per il dettaglio. Ogni skill è documentata con: trigger, input richiesti, output prodotto, dipendenze, collegamenti alla biblioteca-vendita.

## 10. Biblioteca della vendita — quando usarla

Le 44 schede-libro in `00-Foundation/metodologie/biblioteca-vendita/` sono **conoscenza strategica**: spiegano *perché* certe mosse funzionano. Le skill operative sono **conoscenza tattica**: spiegano *come* fare la mossa. Combinare sempre tatticа + strategia:

- Per `/sales prep` di una discovery → carica anche `[[consultativa/rackham-spin-selling]]` per la struttura delle domande.
- Per `/sales objections` su prezzo → carica anche `[[negoziazione/voss-never-split]]` e `[[psico/cialdini-influence]]`.
- Per `/sales proposal` enterprise → carica anche `[[consultativa/lahoutifard-meddic]]` per qualifica e `[[consultativa/miller-heiman-strategic-selling]]` per mappa stakeholder.

Vedi `[[biblioteca-vendita/README]]` per la matrice completa libro × stage del funnel.

## 11. Cosa NON fare mai

- ❌ Modificare i file in `raw/` — sono immutabili.
- ❌ Sovrascrivere silenziosamente un claim contraddetto: sempre annotare con warning.
- ❌ Produrre output generici: niente template, niente "ecco un esempio di email cold". Tutto contestualizzato.
- ❌ Dimenticare di archiviare in `50-Output/`.
- ❌ Dimenticare di appendere a `log.md`.
- ❌ Usare emoji nelle pagine wiki.
- ❌ Scrivere in inglese contenuti nuovi (le bibbie EN in `meta/` restano in EN come archivio storico).
- ❌ Inventare dati per riempire frontmatter mancanti: lasciare campi vuoti o `TODO` finché l'umano non fornisce.

## 12. Riferimenti

- Bibbia primaria del pattern: `[[llm-wiki-pattern]]`
- Bibbia secondaria (originale EN): `[[llm-wiki-original]]`
- Indice navigabile: `[[index]]`
- Log cronologico: `[[log]]`
- Onboarding per l'imprenditore: `[[ONBOARDING]]`
