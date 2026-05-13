---
type: index
generato: 2026-05-12
totale-file-md: 112
totale-pagine-skill: 14
totale-schede-libro: 44
---

# index.md — Catalogo della wiki

> Catalogo content-oriented. L'LLM legge questo file in apertura di ogni query per individuare le pagine rilevanti, poi scende nei dettagli. L'imprenditore lo usa come mappa di navigazione.

---

## Punti di ingresso

| Pagina | Scopo |
|--------|-------|
| `[[README]]` | Intro umana alla wiki |
| `[[CLAUDE]]` | Schema operativo per l'LLM (LEGGERE IN APERTURA SESSIONE) |
| `[[ONBOARDING]]` | Guida primi 7 giorni per l'imprenditore |
| `[[log]]` | Registro cronologico append-only |

---

## Fondazione — Azienda

> **STATUS: scheletro vuoto, da compilare dall'imprenditore.**

- `[[00-Foundation/azienda/overview]]` — chi siamo, numeri, canali
- `[[00-Foundation/azienda/posizionamento]]` — USP, anti-ICP, claim
- `[[00-Foundation/azienda/tono-di-voce]]` — voce del brand
- `[[00-Foundation/azienda/valori]]` — manifesto, principi

## Fondazione — Offerte, ICP, funnel, obiezioni, scenari, rep

> **STATUS: README + struttura presenti, schede vuote.**

- `[[00-Foundation/offerte/README]]` — catalogo offerte (0 schede)
- `[[00-Foundation/icp/README]]` — Ideal Customer Profile (0 schede)
- `[[00-Foundation/funnel/README]]` — funnel marketing (0 materiali)
- `[[00-Foundation/obiezioni/README]]` — playbook obiezioni (0 schede)
- `[[00-Foundation/scenari/README]]` — scenari di vendita (0 schede)
- `[[00-Foundation/sales-rep/README]]` — profili rep (0 schede) — `[[00-Foundation/sales-rep/_template-rep|template]]`

---

## Fondazione — Skill operative (14 skill + 5 agenti + 4 script + 6 template)

> Catalogo completo in `[[00-Foundation/metodologie/skill-operative/README]]`.

### Orchestratore

| Skill | Trigger | Output |
|-------|---------|--------|
| `[[00-Foundation/metodologie/skill-operative/sales]]` | `/sales <comando>` | varia |

### 13 sub-skill — per fase del funnel

| Skill | Trigger | Output | Dipendenze chiave |
|-------|---------|--------|-------------------|
| `[[00-Foundation/metodologie/skill-operative/sales-icp]]` | `/sales icp` | IDEAL-CUSTOMER-PROFILE.md | azienda, offerta |
| `[[00-Foundation/metodologie/skill-operative/sales-prospect]]` | `/sales prospect` | PROSPECT-ANALYSIS.md | 5 agenti paralleli |
| `[[00-Foundation/metodologie/skill-operative/sales-research]]` | `/sales research` | COMPANY-RESEARCH.md | WebFetch |
| `[[00-Foundation/metodologie/skill-operative/sales-qualify]]` | `/sales qualify` | LEAD-QUALIFICATION.md | account + persone |
| `[[00-Foundation/metodologie/skill-operative/sales-contacts]]` | `/sales contacts` | DECISION-MAKERS.md | account |
| `[[00-Foundation/metodologie/skill-operative/sales-competitors]]` | `/sales competitors` | COMPETITIVE-INTEL.md | account |
| `[[00-Foundation/metodologie/skill-operative/sales-prep]]` | `/sales prep` | MEETING-PREP.md | account + persone + interazioni + rep |
| `[[00-Foundation/metodologie/skill-operative/sales-outreach]]` | `/sales outreach` | OUTREACH-SEQUENCE.md | account + persona + ICP + tono |
| `[[00-Foundation/metodologie/skill-operative/sales-objections]]` | `/sales objections` | OBJECTION-PLAYBOOK.md | obiezioni + interazioni |
| `[[00-Foundation/metodologie/skill-operative/sales-proposal]]` | `/sales proposal` | CLIENT-PROPOSAL.md | trattativa + qualifica + offerta |
| `[[00-Foundation/metodologie/skill-operative/sales-followup]]` | `/sales followup` | FOLLOWUP-SEQUENCE.md | interazioni + trattativa |
| `[[00-Foundation/metodologie/skill-operative/sales-report]]` | `/sales report` | SALES-REPORT.md | tutte le trattative attive |
| `[[00-Foundation/metodologie/skill-operative/sales-report-pdf]]` | `/sales report-pdf` | SALES-REPORT-*.pdf | sales-report + reportlab |

### Agenti (5 sub-agent paralleli di `sales-prospect`)
- `[[00-Foundation/metodologie/skill-operative/agenti/sales-company]]` — Company Fit (25% score)
- `[[00-Foundation/metodologie/skill-operative/agenti/sales-contacts]]` — Contact Access (20%)
- `[[00-Foundation/metodologie/skill-operative/agenti/sales-opportunity]]` — Opportunity Quality (20%)
- `[[00-Foundation/metodologie/skill-operative/agenti/sales-competitive]]` — Competitive Position (15%)
- `[[00-Foundation/metodologie/skill-operative/agenti/sales-strategy]]` — Outreach Readiness (20%)

### Script (4 Python utility)
- `[[00-Foundation/metodologie/skill-operative/script/analyze_prospect]]`
- `[[00-Foundation/metodologie/skill-operative/script/lead_scorer]]`
- `[[00-Foundation/metodologie/skill-operative/script/contact_finder]]`
- `[[00-Foundation/metodologie/skill-operative/script/generate_pdf_report]]`

### Template (6 boilerplate riutilizzabili)
- `[[00-Foundation/metodologie/skill-operative/template/meeting-prep]]`
- `[[00-Foundation/metodologie/skill-operative/template/outreach-cold]]`
- `[[00-Foundation/metodologie/skill-operative/template/outreach-warm]]`
- `[[00-Foundation/metodologie/skill-operative/template/outreach-referral]]`
- `[[00-Foundation/metodologie/skill-operative/template/objection-playbook]]`
- `[[00-Foundation/metodologie/skill-operative/template/proposal-template]]`

---

## Fondazione — Biblioteca della vendita (44 libri, 10 famiglie)

> Indice generale in `[[00-Foundation/metodologie/biblioteca-vendita/README]]`.

| Famiglia | Libri | README |
|----------|-------|--------|
| **atlante** | 1 | `[[00-Foundation/metodologie/biblioteca-vendita/atlante/README]]` |
| **challenger** | 4 | `[[00-Foundation/metodologie/biblioteca-vendita/challenger/README]]` |
| **classica** | 2 | `[[00-Foundation/metodologie/biblioteca-vendita/classica/README]]` |
| **consultativa** | 7 | `[[00-Foundation/metodologie/biblioteca-vendita/consultativa/README]]` |
| **darkside** | 2 (uso etico) | `[[00-Foundation/metodologie/biblioteca-vendita/darkside/README]]` |
| **direct-response** | 6 | `[[00-Foundation/metodologie/biblioteca-vendita/direct-response/README]]` |
| **etica** | 5 | `[[00-Foundation/metodologie/biblioteca-vendita/etica/README]]` |
| **negoziazione** | 5 | `[[00-Foundation/metodologie/biblioteca-vendita/negoziazione/README]]` |
| **psico** | 7 | `[[00-Foundation/metodologie/biblioteca-vendita/psico/README]]` |
| **sistemica** | 5 | `[[00-Foundation/metodologie/biblioteca-vendita/sistemica/README]]` |

### Libri-chiave (lista flat, kebab-case slug)

**atlante**
- `[[00-Foundation/metodologie/biblioteca-vendita/atlante/atlante]]` — meta-framework orchestratore (metodo italiano)

**challenger**
- `[[00-Foundation/metodologie/biblioteca-vendita/challenger/dixon-challenger-sale]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/challenger/dixon-challenger-customer]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/challenger/iannarino-eat-their-lunch]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/challenger/iannarino-lost-art-of-closing]]`

**classica**
- `[[00-Foundation/metodologie/biblioteca-vendita/classica/aristotele-retorica]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/classica/carnegie-how-to-win-friends]]`

**consultativa**
- `[[00-Foundation/metodologie/biblioteca-vendita/consultativa/rackham-spin-selling]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/consultativa/keenan-gap-selling]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/consultativa/sandler-cant-teach-a-kid]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/consultativa/bosworth-solution-selling]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/consultativa/hanan-consultative-selling]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/consultativa/miller-heiman-strategic-selling]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/consultativa/lahoutifard-meddic]]`

**darkside** (uso difensivo/diagnostico)
- `[[00-Foundation/metodologie/biblioteca-vendita/darkside/belfort-way-of-the-wolf]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/darkside/greene-48-laws-of-power]]`

**direct-response**
- `[[00-Foundation/metodologie/biblioteca-vendita/direct-response/schwartz-breakthrough-advertising]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/direct-response/hopkins-scientific-advertising]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/direct-response/hopkins-my-life-in-advertising]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/direct-response/ogilvy-on-advertising]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/direct-response/ogilvy-confessions]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/direct-response/bettger-how-i-raised-myself]]`

**etica**
- `[[00-Foundation/metodologie/biblioteca-vendita/etica/pink-to-sell-is-human]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/etica/godin-permission-marketing]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/etica/godin-this-is-marketing]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/etica/burg-go-giver]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/etica/covey-7-habits]]`

**negoziazione**
- `[[00-Foundation/metodologie/biblioteca-vendita/negoziazione/voss-never-split]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/negoziazione/fisher-getting-to-yes]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/negoziazione/ury-getting-past-no]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/negoziazione/malhotra-negotiation-genius]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/negoziazione/diamond-getting-more]]`

**psico**
- `[[00-Foundation/metodologie/biblioteca-vendita/psico/cialdini-influence]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/psico/cialdini-pre-suasion]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/psico/kahneman-thinking-fast-slow]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/psico/klaff-pitch-anything]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/psico/klaff-flip-the-script]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/psico/damasio-descartes-error]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/psico/haidt-righteous-mind]]`

**sistemica**
- `[[00-Foundation/metodologie/biblioteca-vendita/sistemica/ross-predictable-revenue]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/sistemica/roberge-sales-acceleration-formula]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/sistemica/holmes-ultimate-sales-machine]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/sistemica/van-der-kooij-saas-sales-blueprints]]`
- `[[00-Foundation/metodologie/biblioteca-vendita/sistemica/coleman-never-lose-customer-again]]`

---

## Fondazione — Meta-documentazione (bibbie del pattern)

- `[[00-Foundation/metodologie/meta/llm-wiki-pattern]]` — bibbia primaria (IT, sales-specialized)
- `[[00-Foundation/metodologie/meta/llm-wiki-original]]` — bibbia secondaria (EN, originale)

---

## Layer entità — Account / Persone / Trattative / Interazioni / Output

> **STATUS: vuoto.** Crescerà con l'uso (ingestione + skill).

| Cartella | Conteggio | README | Template |
|----------|-----------|--------|----------|
| `10-Account/` | 0 | `[[10-Account/README]]` | `[[10-Account/_template-azienda]]` |
| `20-Persone/` | 0 | `[[20-Persone/README]]` | `[[20-Persone/_template-persona]]` |
| `30-Trattative/` | 0 | `[[30-Trattative/README]]` | `[[30-Trattative/_template-trattativa]]` |
| `40-Interazioni/` | 0 | `[[40-Interazioni/README]]` | `[[40-Interazioni/_template-interazione]]` |
| `50-Output/` | 0 | `[[50-Output/README]]` | — |

---

## Fonti grezze — `raw/`

> **STATUS: vuoto.** Da popolare con trascrizioni meeting, email, export CRM, materiali, coaching.

- `[[raw/README]]` — regole di immutabilità, naming, mapping a interazioni
- `raw/meetings/` — trascrizioni Fathom/Fireflies/Otter
- `raw/email/` — thread email convertiti in .md
- `raw/crm-export/` — export CRM
- `raw/coaching/` — sessioni di coaching
- `raw/materiali/` — slide, brochure, contratti
- `raw/assets/` — immagini, allegati

---

## Metadati globali

- **Generato**: 2026-05-12 (genesi)
- **Ultima ingestione**: nessuna (vault appena creato)
- **Conteggio pagine totali**: 112
- **Pagine fondazione**: 64 (skill-operative + biblioteca-vendita + meta + azienda + altri foundation)
- **Schede entità**: 0 (account/persone/trattative/interazioni/output)
- **Pagine skeleton da popolare**: 18 (4 azienda + 6 foundation-README + 1 _template-rep + 5 entity-README + 4 _template-entity — meno duplicazioni)

> L'indice viene aggiornato dall'LLM dopo ogni ingestione o lint pass.
