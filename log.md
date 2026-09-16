---
type: log
formato: append-only
---

# log.md — Registro cronologico

> Append-only. Ogni evento di ingestione, query, lint, output di skill viene appeso qui con prefisso datato. Formato dei titoli: `## [YYYY-MM-DD] <tipo> | <descrizione breve>`. Parsabile con `grep "^## \[" log.md | tail -N`.

Tipi canonici di evento:
- `genesis` — bootstrap del vault
- `ingest` — ingestione di una fonte da `raw/`
- `query` — risposta a una domanda libera
- `skill` — esecuzione di una skill `/sales <…>`
- `lint` — health-check periodico
- `manual` — modifica manuale documentata

---

## [2026-05-12] genesis | Bootstrap iniziale del vault

**Operatore**: LLM (Claude Code) su istruzione del prompt `prompt-bootstrap.md`.

**Sorgenti ingerite (architettura, non dati operativi)**:
- Manuale pattern primario: `llm-wiki-sales-team.md` (bibbia italiana sales-specialized)
- Manuale pattern secondario: `llm-wiki.md` (bibbia originale inglese)
- Orchestratore skill: `ai-sales-manager/sales/SKILL.md` (1)
- Skill operative `sales-*`: 13 sotto-skill specialiste
- Agenti subagent: 5 (sales-company, sales-contacts, sales-competitive, sales-opportunity, sales-strategy)
- Script Python: 4 (analyze_prospect, lead_scorer, contact_finder, generate_pdf_report) — schede funzionali, codice NON copiato
- Template skill: 6 (meeting-prep, outreach-cold/warm/referral, objection-playbook, proposal-template) — contenuto copiato integralmente
- Biblioteca della vendita: 44 schede-libro `vendita-*` da `Ripeti_work/.claude/skills/` organizzate in 10 famiglie

**Strutture create**:
- Scheletro completo cartelle (vedi `[[CLAUDE]]` §3 per la mappa)
- `[[CLAUDE]]` — schema operativo del vault
- `[[README]]` — intro umana
- `[[ONBOARDING]]` — guida primi 7 giorni
- `[[index]]` — catalogo navigabile
- `[[log]]` — (questo file)
- Bibbie archiviate in `[[00-Foundation/metodologie/meta/llm-wiki-pattern]]` e `[[00-Foundation/metodologie/meta/llm-wiki-original]]`

**Fondazione vuota in attesa di compilazione**:
- `[[00-Foundation/azienda/overview]]`, `posizionamento`, `tono-di-voce`, `valori`
- `[[00-Foundation/offerte/README]]` — nessuna offerta ancora caricata
- `[[00-Foundation/icp/README]]` — nessun ICP ancora definito
- `[[00-Foundation/funnel/README]]` — funnel non documentato
- `[[00-Foundation/obiezioni/README]]` — playbook obiezioni vuoto
- `[[00-Foundation/scenari/README]]` — scenari non mappati
- `[[00-Foundation/sales-rep/README]]` — nessun rep profilato

**Layer entità vuoto in attesa di alimentazione**:
- `[[10-Account/README]]` — 0 account caricati
- `[[20-Persone/README]]` — 0 persone caricate
- `[[30-Trattative/README]]` — 0 trattative aperte
- `[[40-Interazioni/README]]` — 0 interazioni
- `[[50-Output/README]]` — 0 output prodotti
- `[[raw/README]]` — fonti grezze vuote

**TODO immediati per l'imprenditore** (vedi `[[ONBOARDING]]` per la sequenza completa):
1. Compilare `00-Foundation/azienda/*` (4 file di overview, positioning, tono, valori)
2. Creare almeno una scheda offerta in `00-Foundation/offerte/`
3. Creare almeno un ICP in `00-Foundation/icp/`
4. Creare il proprio profilo rep in `00-Foundation/sales-rep/<nome>.md`
5. Depositare i primi materiali esistenti (brochure, case study, slide) in `raw/materiali/`
6. Depositare le prime trascrizioni meeting in `raw/meetings/`
7. Lanciare la prima ingestione e osservare l'aggiornamento delle pagine collegate

**Note di genesi**:
- Tutto il vault è in italiano (anglicismi standard sales conservati).
- Nessun dato operativo reale è stato inserito — il vault è scheletro pronto, non popolato.
- Il codice Python degli script NON è stato copiato nella wiki: solo schede funzionali con path al sorgente.
- I template hanno contenuto integrale copiato con frontmatter.
- Le bibbie del pattern sono archiviate immutabili in `meta/` (testo originale + frontmatter di archiviazione).

---

*(le voci successive vengono appese sotto questa, sempre con prefisso `## [YYYY-MM-DD] <tipo> | ...`)*
