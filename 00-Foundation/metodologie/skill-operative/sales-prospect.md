---
type: skill-operativa
nome: sales-prospect
trigger: /sales prospect <url>
inputs: [URL azienda target, eventuale ICP, eventuali analisi pregresse]
outputs: [PROSPECT-ANALYSIS.md con Prospect Score 0-100, email primo contatto pronta]
dipendenze: [5 sub-agenti paralleli, analyze_prospect.py, tutte le sub-skill di analisi]
---

# sales-prospect

## Cosa fa
Comando flagship dell'intero sistema. Esegue un audit completo del prospect lanciando in parallelo 5 sub-agenti specializzati (company, contacts, opportunity, competitive, strategy). Aggrega i risultati in un Prospect Score 0-100 ponderato, produce un piano d'azione su tre orizzonti temporali (24-48 ore, 1-2 settimane, 1-3 mesi) e una email di primo contatto copy-paste ready, personalizzata sulla base dei dati raccolti.

## Quando si usa
- Nuovo lead in arrivo da segnalare, qualificare, e mettere in pipeline
- Account-Based Marketing su target list selezionata
- Preparazione di un trigger event scoperto (funding, lancio prodotto, nuovo VP)
- Routine settimanale di valutazione di nuove opportunità
- Sostituzione di un'analisi superficiale fatta su 60 secondi con `/sales quick`

## Procedura
1. **Phase 1 Discovery (sequenziale):** fetch homepage + fino a 5 pagine interne (about, team, pricing, blog, careers, contact) tramite WebFetch.
2. Detection del tipo azienda (SaaS, Agency, E-commerce, Enterprise, SMB, Startup) e dell'industry vertical.
3. Estrazione strutturata via `analyze_prospect.py --url <url> --output json` per ottenere meta-dati, tech stack, social profile, contatti.
4. Compilazione di un "Discovery Briefing" che verrà passato a tutti i sub-agenti.
5. **Phase 2 Parallel Analysis:** lancio simultaneo (Task tool) dei 5 sub-agenti con `subagent_type: "general-purpose"`, ognuno restituisce uno score 0-100 per la sua area.
6. **Phase 3 Synthesis:** aggregazione con formula ponderata (`0.25*CompanyFit + 0.20*ContactAccess + 0.20*OpportunityQuality + 0.15*CompetitivePosition + 0.20*OutreachReadiness`).
7. Assegnazione del grade A+/A/B/C/D e generazione del piano d'azione su 3 orizzonti.
8. Drafting dell'email di primo contatto (sotto 100 parole, 2 subject line A/B, CTA low-friction).
9. Calcolo del Confidence Level (High/Medium/Low/Very Low) in base ai sub-agenti completati.
10. Output finale su `PROSPECT-ANALYSIS.md` + terminal scorecard condensato.

## Input richiesti dalla wiki
- `[[10-Account/<azienda>]]` — scheda dell'azienda target (URL, contesto, note CRM)
- `[[00-Foundation/icp/...]]` — Ideal Customer Profile per calibrare il Company Fit
- `[[00-Foundation/offerte/...]]` — cosa stiamo vendendo (per personalizzare value prop)
- `[[00-Foundation/azienda/...]]` — case study di riferimento da citare nell'email
- `[[00-Foundation/sales-rep/...]]` — firma e tono di voce del rep

## Output prodotto
- `PROSPECT-ANALYSIS.md` archiviato in `50-Output/YYYY-MM-DD-prospect-<account>.md`
- Sezioni: Executive Summary, Prospect Snapshot, Score Breakdown, Company Profile, Decision Maker Map (org chart + top 3 contatti prioritari), Opportunity Assessment (BANT + MEDDIC), Competitive Landscape, Recommended Outreach Strategy, Prioritized Action Plan, Ready-to-Send First Email

## Collegamenti
- Agenti: `[[skill-operative/agenti/sales-company]]`, `[[skill-operative/agenti/sales-contacts]]`, `[[skill-operative/agenti/sales-opportunity]]`, `[[skill-operative/agenti/sales-competitive]]`, `[[skill-operative/agenti/sales-strategy]]`
- Script: `[[skill-operative/script/analyze_prospect]]`
- Skill correlate: `[[skill-operative/sales-research]]`, `[[skill-operative/sales-qualify]]`, `[[skill-operative/sales-contacts]]`, `[[skill-operative/sales-competitors]]`, `[[skill-operative/sales-outreach]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/consultativa/lahoutifard-meddic]]`, `[[biblioteca-vendita/challenger/dixon-challenger-sale]]`, `[[biblioteca-vendita/consultativa/rackham-spin-selling]]`, `[[biblioteca-vendita/sistemica/holmes-ultimate-sales-machine]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-prospect/SKILL.md`
