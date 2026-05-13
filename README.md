# Wiki commerciale — vault Obsidian

Questa è una **knowledge base commerciale persistente** mantenuta da un LLM. Non sostituisce un CRM: lo affianca con qualcosa che il CRM non sa fare — una memoria narrativa, interconnessa e auto-aggiornante della tua attività commerciale.

## Cos'è

Tre layer:

1. **`raw/`** — le fonti grezze (trascrizioni Fathom, thread email, export CRM, materiali, sessioni di coaching). Immutabili. L'LLM legge, non scrive.
2. **Wiki** (`00-Foundation/`, `10-Account/`, `20-Persone/`, `30-Trattative/`, `40-Interazioni/`, `50-Output/`) — le pagine markdown che l'LLM costruisce e mantiene. Una scheda per ogni azienda, persona, deal, touchpoint. Tutte interconnesse via `[[wiki-link]]`.
3. **Schema** (`CLAUDE.md`) — il contratto operativo che dice all'LLM come comportarsi. È il file di configurazione chiave.

## Come si usa

Hai tre modi per interagire col vault:

### Da Obsidian (lettura, esplorazione, graph view)
Apri questa cartella `vault/` come vault Obsidian. Naviga le pagine seguendo i link, usa la graph view per vedere come si connettono account, persone, trattative. Non scrivi mai direttamente — leggi.

### Da Claude Code (terminale)
Apri Claude Code nella root del progetto (`llm-wiki-sales/`, non solo `vault/`). Hai a disposizione:
- **Ingestione**: deposita una fonte in `raw/`, dì "ingerisci questa". L'LLM crea/aggiorna le pagine collegate.
- **Skill operative**: `/sales prep <account>`, `/sales outreach <prospect>`, `/sales proposal <client>`, `/sales objections <topic>`, ecc. Vedi `[[00-Foundation/metodologie/skill-operative/README]]`.
- **Interrogazione libera**: "qual è lo stato del deal ACME?", "fai un report di pipeline", "trova le obiezioni ricorrenti sul prezzo".
- **Lint**: "fai un health-check della wiki".

### Da Claude Desktop (via Obsidian MCP)
Configura il server MCP di Obsidian. Da Claude Desktop puoi porre domande contro la wiki anche da mobile o quando non sei davanti al terminale.

## Struttura

```
vault/
├── CLAUDE.md            # schema operativo per l'LLM
├── README.md            # (questo file)
├── ONBOARDING.md        # guida pratica primi 7 giorni
├── index.md             # catalogo navigabile
├── log.md               # registro cronologico
│
├── 00-Foundation/       # azienda, offerte, ICP, obiezioni, sales-rep, metodologie
├── 10-Account/          # una scheda per cliente/prospect
├── 20-Persone/          # una scheda per buyer/champion/influencer
├── 30-Trattative/       # una scheda per deal
├── 40-Interazioni/      # una pagina per touchpoint (append-only)
├── 50-Output/           # artefatti generati dalle skill
└── raw/                 # fonti grezze (immutabili)
```

## Cosa c'è già

Il vault è stato bootstrappato con:
- **14 skill operative** sales-* del progetto `ai-sales-manager` (orchestratore + 13 specialiste)
- **5 agenti** subagent paralleli per `sales-prospect`
- **4 schede script** Python utility
- **6 template** di output (cold/warm/referral outreach, meeting prep, objection playbook, proposal)
- **44 schede-libro** della biblioteca della vendita organizzate in 10 famiglie (atlante, challenger, classica, consultativa, darkside, direct-response, etica, negoziazione, psico, sistemica)
- **Bibbie del pattern** archiviate in `00-Foundation/metodologie/meta/`
- **Scheletri** per azienda, offerte, ICP, funnel, obiezioni, scenari, sales-rep — **da compilare dall'imprenditore**

## Cosa manca (lo aggiungi tu)

Prima di lanciare la prima skill operativa:
1. Compila `00-Foundation/azienda/` — chi sei, USP, tono, valori
2. Crea almeno una scheda offerta in `00-Foundation/offerte/`
3. Crea almeno un ICP in `00-Foundation/icp/`
4. Crea il tuo profilo rep in `00-Foundation/sales-rep/<tuo-nome>.md`
5. Carica i tuoi primi materiali esistenti in `raw/`

Vedi `[[ONBOARDING]]` per la guida step-by-step.

## Filosofia

Tu sei il responsabile di:
- Curare le fonti (cosa entra in `raw/`)
- Esplorare e leggere
- Porre le domande giuste prima di una call, durante una trattativa, in una review di pipeline

L'LLM è responsabile di tutto il resto: scrivere, aggiornare, cross-referenziare, segnalare contraddizioni, mantenere coerenza, archiviare gli output.

## Versionamento
Questo vault è un repo git di file markdown. Hai storia delle versioni, branching, e auditabilità gratis. Considera di farne un repo git separato (o sotto-modulo) per backuppare la conoscenza commerciale.

## Riferimenti
- `[[CLAUDE]]` — schema operativo (LEGGERE PRIMA DI INTERAGIRE)
- `[[ONBOARDING]]` — guida primi 7 giorni
- `[[index]]` — catalogo
- `[[00-Foundation/metodologie/meta/llm-wiki-pattern]]` — bibbia del pattern (versione italiana sales)
