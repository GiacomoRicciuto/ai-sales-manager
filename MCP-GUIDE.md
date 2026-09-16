---
type: meta-documento
ruolo: guida-operativa-mcp
lettura: obbligatoria-prima-di-agire
---

# Guida operativa: vault + MCP

Questa è la guida che devi avere in testa **prima** di rispondere a qualunque richiesta dell'utente che riguardi il lavoro commerciale. Va letta a inizio sessione, una sola volta, insieme a `CLAUDE.md`. Non descrive ogni dettaglio del vault — descrive come pensare e cosa fare quando arrivi davanti a una domanda.

## Il principio: il vault prima di tutto

L'utente di questo sistema non vuole risposte che vengono dalla tua memoria di training. Vuole risposte che vengono dalla sua wiki — perché è lì che vivono i dati reali della sua azienda, dei suoi lead, delle sue trattative, e le metodologie che ha scelto di adottare. Quando ricevi una richiesta, la tua prima azione è sempre la stessa: capire dove nel vault sta la conoscenza che serve, leggerla, e poi rispondere a partire da quella. Anche quando la domanda sembra generica, anche quando "lo sapresti rispondere da solo": se il vault può rispondere, deve farlo lui. La tua memoria interna serve solo a colmare i vuoti che il vault non copre, mai a sostituirlo.

Questo significa che non prendi mai decisioni operative — preparare un meeting, scrivere un follow-up, qualificare un lead, proporre un'offerta — senza aver prima letto le pagine rilevanti del vault. Se non sai dove guardare, lo capisci con una `obsidian_search_notes` in modalità testuale; se non sai cosa esiste, fai un `obsidian_list_notes` sulla cartella che sospetti contenga la risposta. Non improvvisare. Non inventare contenuti per le schede dell'imprenditore (`00-Foundation/azienda/`, `offerte/`, `icp/`, `sales-rep/`): se sono vuote, lo segnali e chiedi di compilarle.

## Quando la richiesta dell'utente è vaga

Spesso l'utente non ti dirà "esegui la skill `sales-prep`". Ti dirà "preparami la call di domani con il cliente", oppure "che gli rispondo a questa obiezione", oppure "scrivimi un'email per riagganciare ACME". Il tuo lavoro è tradurre quell'intento, anche detto male, nel percorso skill giusto del vault. Il pattern è sempre lo stesso: identifichi il verbo principale ("preparare", "rispondere", "riagganciare", "qualificare", "proporre"), lo mappi alla skill operativa più vicina in `00-Foundation/metodologie/skill-operative/`, leggi la scheda della skill per capire cosa serve in input, e poi recuperi quelle informazioni dal vault. Solo dopo, scrivi la risposta.

Per orientarti, una mappatura ragionevole tra intenti comuni e percorsi skill:

| L'utente dice qualcosa come… | Tu vai su questa skill |
|---|---|
| "preparami la call / il meeting / l'incontro con X" | `sales-prep` |
| "chi è questa azienda / cosa fa / dimmi tutto su Y" | `sales-research` |
| "vale la pena questo lead / ha senso seguirlo" | `sales-qualify` |
| "chi devo contattare in X / chi è il decisore" | `sales-contacts` |
| "rispondi a questa obiezione / mi ha detto che..." | `sales-objections` |
| "scrivimi il follow-up / ricontatta / riaggancia" | `sales-followup` |
| "fammi una proposta / preparami il preventivo" | `sales-proposal` |
| "che differenza c'è con il competitor Z / perché noi" | `sales-competitors` |
| "scrivi cold outreach / primo contatto / messaggio LinkedIn" | `sales-outreach` |
| "com'è messa la pipeline / report del trimestre" | `sales-report` (e `sales-report-pdf` se serve PDF) |
| "definisci il mio ICP / chi è il cliente ideale" | `sales-icp` |
| "analizza questo prospect tutto / fammi il dossier completo" | `sales-prospect` (è l'orchestratrice, chiama le altre) |

Quando l'intento è ambiguo tra due skill, scegli quella più specifica. Quando proprio non riesci a decidere, leggi sia `sales-prospect.md` sia `CLAUDE.md` e parti dall'orchestratrice.

## Il workflow base, sempre uguale

Ogni risposta operativa segue lo stesso ritmo. Capisci l'intento e la skill. Leggi la scheda della skill — la trovi in `00-Foundation/metodologie/skill-operative/<nome-skill>.md` — perché lì c'è scritto cosa serve in input, quale output produrre, e con quale dottrina della biblioteca-vendita allinearti. Estrai dal vault le entità rilevanti: la scheda azienda in `10-Account/`, le persone in `20-Persone/`, la trattativa in `30-Trattative/`, e lo storico interazioni in `40-Interazioni/` se la cosa ha un passato. Se la skill richiama una metodologia (per esempio `sales-objections` rinvia spesso a `vendita-negoziazione-voss-never-split` o a `vendita-consultativa-sandler-cant-teach-a-kid`), apri anche quella scheda. Produci l'output. Lo archivi in `50-Output/` con nome `YYYY-MM-DD-<slug-skill>-<slug-target>.md`, gli metti un frontmatter coerente con le convenzioni di `CLAUDE.md`, e lo linki dalla scheda azienda o dalla trattativa più rilevante. Infine appendi una riga in `log.md`. Solo a questo punto restituisci la risposta all'utente — e gli citi i file che hai prodotto e quelli che hai aggiornato, così può aprirli in Obsidian.

Quando la richiesta è "leggi e dimmi" invece che "produci qualcosa", saltati l'archiviazione: leggere non genera un artefatto da conservare. Ma una sintesi non triviale (analisi competitiva, comparativa tra account, dossier di approfondimento su un lead) sì — quella diventa una pagina nuova nel vault, perché ha valore di accumulo.

## Gli strumenti MCP che hai a disposizione

Hai 14 strumenti, raggruppati per funzione. Non serve impararli a memoria, ma serve sapere quando usare quale. La regola intuitiva: se devi capire la struttura usa `list`, se devi leggere usa `get`, se devi trovare usa `search`, se devi creare usa `write`, se devi modificare in modo chirurgico usa `patch` o `replace`, se devi toccare il frontmatter o i tag usa i due tool dedicati.

**Per esplorare e leggere.** `obsidian_list_notes` ti fa vedere cosa c'è in una cartella senza aprire i file — utile per orientarti quando arrivi su un'area che non conosci, o per controllare se un account/persona/trattativa esiste già prima di crearli. `obsidian_get_note` legge una singola nota; supporta quattro proiezioni: `content` (solo il corpo markdown), `full` (corpo + frontmatter + tag + metadata + opzionalmente i link uscenti), `document-map` (la mappa delle heading e dei block reference, indispensabile prima di qualunque patch chirurgico), e `section` (un singolo blocco identificato per heading). `obsidian_search_notes` cerca attraverso tutto il vault: in modalità `text` per stringhe libere con contesto attorno alle occorrenze, in `dataview` per query strutturate sul frontmatter (richiede plugin Dataview installato), in `jsonlogic` come alternativa quando vuoi una query strutturata senza dipendenze. `obsidian_list_tags` ti dà l'inventario dei tag usati — in questo vault i tag sono poco usati, l'organizzazione si basa su `type:` nel frontmatter e sulla struttura cartelle, ma il tool esiste e a volte serve.

**Per scrivere e modificare.** `obsidian_write_note` crea un file nuovo, oppure lo sovrascrive se passi esplicitamente `overwrite: true`; di default rifiuta di clobberare qualcosa che esiste già, ed è una protezione che vuoi tenerti. `obsidian_append_to_note` aggiunge contenuto alla fine di una nota (o all'interno di una sezione, se gliela specifichi); se la nota non esiste, viene creata col contenuto che le passi. `obsidian_patch_note` è il bisturi: fa append/prepend/replace su un target preciso — un heading, un block reference, o un campo del frontmatter. Prima di chiamarlo, leggi sempre il `document-map` per scoprire i target esatti, perché il PATCH è letterale e fallisce silenziosamente se sbagli di una virgola. `obsidian_replace_in_note` fa find-and-replace globale nel corpo di una nota, con opzioni di regex, case sensitivity, whole word e replace-all — usalo quando il patch chirurgico non ti basta. `obsidian_manage_frontmatter` lavora atomicamente su un singolo campo YAML (get/set/delete) — è il modo pulito di aggiornare `stage`, `valore_eur`, `ultimo_touchpoint`, eccetera, senza riscrivere l'intera nota. `obsidian_manage_tags` aggiunge o rimuove tag riconciliando le due rappresentazioni (array in frontmatter e `#tag` inline). `obsidian_delete_note` cancella, con conferma umana richiesta dal client.

**Per interagire con l'app.** `obsidian_open_in_ui` apre una nota nell'interfaccia di Obsidian dell'utente — utile dopo che hai prodotto un output, così l'utente lo vede comparire. `obsidian_execute_command` e `obsidian_list_commands` sono opt-in (richiedono `OBSIDIAN_ENABLE_COMMANDS=true` lato server) e in questo setup non sono attivi: ignorali.

## Tabella riassuntiva dei 14 tool

| Tool | Usalo quando | Note |
|---|---|---|
| `obsidian_list_notes` | devi orientarti in una cartella o verificare l'esistenza di una scheda | depth default 2, max 20; cap di 1000 entry |
| `obsidian_get_note` | devi leggere una nota specifica | 4 formati: `content`, `full`, `document-map`, `section` |
| `obsidian_search_notes` | devi trovare qualcosa che non sai dove sta | 3 modalità: `text`, `dataview` (richiede plugin), `jsonlogic` |
| `obsidian_list_tags` | vuoi vedere la tassonomia dei tag | in questo vault poco usato |
| `obsidian_write_note` | crei una nota nuova | rifiuta overwrite di default — è una protezione, tienila |
| `obsidian_append_to_note` | aggiungi a fine file o a una sezione esistente | se file non esiste, lo crea col contenuto |
| `obsidian_patch_note` | modifica chirurgica su heading, block, o frontmatter | **leggi `document-map` prima**; sintassi `Parent::Child` per heading nidificati |
| `obsidian_replace_in_note` | find-and-replace nel corpo della nota | supporta regex, case, whole-word, replace-all |
| `obsidian_manage_frontmatter` | get/set/delete atomico su un campo YAML | per stringhe passa JSON pulito, non quoting esterno extra |
| `obsidian_manage_tags` | aggiungi/rimuovi tag | gestisce sia frontmatter `tags:` sia `#tag` inline |
| `obsidian_delete_note` | cancellazione definitiva | il client può chiedere conferma — è desiderato |
| `obsidian_open_in_ui` | mostrare all'utente un file che hai appena creato/modificato | apre nell'app Obsidian |
| `obsidian_list_commands` | (disabilitato in questo setup) | richiede `OBSIDIAN_ENABLE_COMMANDS=true` |
| `obsidian_execute_command` | (disabilitato in questo setup) | richiede `OBSIDIAN_ENABLE_COMMANDS=true` |

## Caveat appresi (memorizzali, non li riscoprire)

Tre comportamenti del sistema che è bene tenere a mente perché non sono ovvi e ti fanno perdere tempo se li sbagli.

Il primo riguarda `obsidian_patch_note`: quando il target è un heading, devi usare la sintassi `Parent::Child` anche per heading di secondo livello sotto un singolo H1. Il livello-1 implicito conta. La via sicura è sempre fare prima `obsidian_get_note format=document-map` e copiare letteralmente la stringa che ti viene restituita.

Il secondo riguarda `obsidian_manage_frontmatter` quando setti una stringa: passa il valore come stringa JSON pulita (`"completato"`), non come stringa con quoting esterno aggiuntivo (`'"completato"'`), altrimenti il file finisce con virgolette annidate.

Il terzo riguarda `obsidian_patch_note` con `operation=append` su un block reference: non c'è separatore automatico tra il contenuto esistente e quello che aggiungi. Se vuoi un newline prima, includilo esplicitamente all'inizio della stringa che passi.

## Chiusura

Ogni volta che agisci su questo vault, lasci una traccia. La traccia è ciò che rende la wiki utile la volta dopo. Quando ingerisci, archivi un'interazione e aggiorni le entità collegate. Quando rispondi a una query complessa, filtri il risultato in `50-Output/` e logghi. Quando l'utente ti dà istruzioni nuove sul modo di lavorare, le porti — quando sensato — in `CLAUDE.md` o qui dentro, così la sessione dopo non riparte da zero. Il vault è vivo solo se ogni passaggio aggiunge qualcosa; se l'output sparisce nella chat, il sistema regredisce alla RAG che non vogliamo. Questo è il punto della wiki, e questo è il tuo lavoro qui dentro.
