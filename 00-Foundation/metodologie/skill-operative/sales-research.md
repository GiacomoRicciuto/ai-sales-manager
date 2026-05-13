---
type: skill-operativa
nome: sales-research
trigger: /sales research <url>
inputs: [URL azienda, eventuale discovery briefing dal comando prospect]
outputs: [COMPANY-RESEARCH.md con Company Fit Score 0-100 su 8 dimensioni]
dipendenze: [WebFetch, WebSearch, agente sales-company quando invocata come subagent]
---

# sales-research

## Cosa fa
Motore di ricerca aziendale che produce intelligence strutturata su 8 dimensioni di analisi: company overview, business model & revenue, product & technology, leadership & team, funding & financial health, market position, culture & employer brand, recent developments. Stima firmographics, employee count, revenue range, funding history e tech stack incrociando website, SEC filings, Crunchbase, LinkedIn, press, review sites, social. Invocabile in standalone o come sub-agente `sales-company` dentro `prospect`.

## Quando si usa
- Approfondimento di un account prima di una call discovery
- Validazione di un lead inbound prima di assegnarlo a un rep senior
- Preparazione di un pitch enterprise che richiede deep dive firmographico
- Refresh periodico (ogni 6 mesi) su account strategici
- Verifica di trigger event come funding round o leadership change

## Procedura
1. **Phase 1 Website Analysis:** fetch homepage, about, team, pricing, blog, careers, customers, press, legal.
2. Detection tech stack da job postings, meta tags, integration pages, dev docs, blog tecnici.
3. **Phase 2 Web Research:** 7 query WebSearch su funding, revenue, news recenti, CEO/founder, reviews Glassdoor, competitors.
4. Applicazione della source priority hierarchy (website → SEC → Crunchbase → LinkedIn → press → news → review sites → social).
5. Validazione data freshness: employee count <6 mesi, funding deve includere ultimo round, news <6 mesi.
6. **Phase 3:** popolamento delle 8 dimensioni con dati specifici, fonti e confidence level.
7. **Phase 4 Scoring:** calcolo Company Fit Score 0-100 su 5 sub-dimensioni (Size Fit 0-20, Industry Fit 0-20, Growth Trajectory 0-20, Tech Sophistication 0-20, Budget Signals 0-20).
8. Identificazione di 3-5 strengths e 3-5 risks con evidenze e sales implications.
9. Estrazione di 5 key insights non-ovvi e actionable per il sales team.
10. Output `COMPANY-RESEARCH.md` + terminal summary.

## Input richiesti dalla wiki
- `[[10-Account/<azienda>]]` — scheda account base
- `[[00-Foundation/icp/...]]` — ICP per calibrare il Company Fit
- `[[00-Foundation/offerte/...]]` — offerta per valutare la rilevanza dei tech signals
- Eventuali fonti raw in `raw/` (PDF investor deck, articoli scrapati)

## Output prodotto
- `COMPANY-RESEARCH.md` archiviato in `50-Output/YYYY-MM-DD-research-<account>.md`
- Sezioni: Executive Summary, Company Snapshot, 8 dimensioni di research, Company Fit Score breakdown, Strengths, Risks, Key Insights for Sales

## Collegamenti
- Agenti: `[[skill-operative/agenti/sales-company]]`
- Script: `[[skill-operative/script/analyze_prospect]]`
- Skill correlate: `[[skill-operative/sales-prospect]]`, `[[skill-operative/sales-qualify]]`, `[[skill-operative/sales-contacts]]`, `[[skill-operative/sales-competitors]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/consultativa/lahoutifard-meddic]]`, `[[biblioteca-vendita/consultativa/miller-heiman-strategic-selling]]`, `[[biblioteca-vendita/sistemica/holmes-ultimate-sales-machine]]`, `[[biblioteca-vendita/direct-response/ogilvy-on-advertising]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-research/SKILL.md`
