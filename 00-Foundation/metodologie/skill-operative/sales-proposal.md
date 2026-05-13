---
type: skill-operativa
nome: sales-proposal
trigger: /sales proposal <client>
inputs: [nome cliente, industry, pain point, soluzione proposta, engagement model, budget, timeline, case study]
outputs: [CLIENT-PROPOSAL.md di 11 sezioni + 6-email follow-up sequence]
dipendenze: [template proposal-template.md, analisi pregresse del cliente]
---

# sales-proposal

## Cosa fa
Genera proposte commerciali client-ready, professionali, persuasive. È un sales document (non SOW, non capabilities deck, non brochure): ogni sezione lead con i problemi del cliente, ancora ogni prezzo all'ROI generato, usa il linguaggio del cliente, guida verso una decisione chiara. Output: 11 sezioni (Cover, Executive Summary, Situation Analysis, Proposed Solution con phased approach, Scope of Work, Timeline, Investment three-tier, ROI Projection conservative/moderate/aggressive, Team, Case Studies, Next Steps) + 6-email follow-up sequence ready-to-send.

## Quando si usa
- Dopo una serie di discovery call quando il cliente ha chiesto "manda una proposta"
- Risposta a un RFP formale
- Closing di un deal mid-market o enterprise
- Riconfigurazione di un'offerta esistente per upsell/expand
- Conversione di un pilot a contratto annuale

## Procedura
1. **Step 1 Inputs:** raccogli i 8 required input (client name, industry, pain point, solution, engagement model, budget range, timeline, case study). Se mancano critici → chiedi. Verifica file pregressi (`PROSPECT-ANALYSIS.md`, `COMPANY-RESEARCH.md`, `LEAD-QUALIFICATION.md`, `COMPETITIVE-INTEL.md`, `DECISION-MAKERS.md`, `MEETING-PREP.md`, `OBJECTION-PLAYBOOK.md`) e incorpora automaticamente.
2. **Section 1 Cover Page:** titolo specifico ("Digital Transformation Strategy for Acme"), prepared for/by, valid until +30gg, CONFIDENTIAL.
3. **Section 2 Executive Summary (1 pagina, 250-350 parole):** 5 paragrafi obbligatori (Acknowledge Their Situation → State Problem → Preview Solution → Hint at Outcomes → Create Urgency). Narrative, no bullet.
4. **Section 3 Situation Analysis:** Current State, 3-5 Opportunities Identified con impact stimato, Competitive Context, 2-3 Key Challenges (frame as opportunity).
5. **Section 4 Proposed Solution:** Strategic Framework (3-5 frasi) + Phased Approach 3 fasi con nomi aspirazionali ("Foundation", "Activation", "Scale"), objective, key activities con deliverable specifico, milestone, client involvement.
6. **Section 5 Scope of Work:** Deliverables, Meeting Cadence, Response Times, Tools, MINIMO 3 Explicit Exclusions, Client Responsibilities.
7. **Section 6 Timeline:** tabella visual settimana-per-settimana + Key Dates.
8. **Section 7 Investment:** TRE TIER obbligatori (Good-Better-Best) con nomi aspirazionali, middle tier marcato RECOMMENDED, ROI math per ogni tier, mensile + annuale (con sconto).
9. **Section 8 ROI Projection:** Conservative / Moderate / Aggressive (mai solo best case), assumptions trasparenti.
10. **Section 9 Team (0.5 pagina):** profili rilevanti per il cliente specifico.
11. **Section 10 Case Studies (2-3):** Challenge-Solution-Results format, stessa industry/size, min 3 metriche, quote.
12. **Section 11 Next Steps:** 3-4 step (review, walkthrough, agreement, kickoff) con data proposta e e-signature mention.
13. **Step 3 Follow-Up Sequence:** 6 email (Day 0 delivery, Day 2 walkthrough, Day 5 value-add, Day 7 check-in, Day 14 second value-add, Day 21 soft close).
14. Output `CLIENT-PROPOSAL.md` sotto le 15 pagine totali.

## Input richiesti dalla wiki
- `[[10-Account/<cliente>]]` — scheda cliente
- `[[20-Persone/...]]` — decision maker da indirizzare
- `[[30-Trattative/<deal>]]` — trattativa attiva con stage, pain identificati, budget
- `[[00-Foundation/offerte/...]]` — offerta base e pricing
- `[[00-Foundation/azienda/...]]` — case study e team
- Tutte le analisi pregresse del cliente in `50-Output/`

## Output prodotto
- `CLIENT-PROPOSAL.md` archiviato in `50-Output/YYYY-MM-DD-proposal-<cliente>.md`
- 11 sezioni + Appendix con la 6-email follow-up sequence

## Collegamenti
- Template: `[[skill-operative/template/proposal-template]]`
- Skill correlate: `[[skill-operative/sales-prospect]]`, `[[skill-operative/sales-qualify]]`, `[[skill-operative/sales-competitors]]`, `[[skill-operative/sales-objections]]`, `[[skill-operative/sales-followup]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/consultativa/lahoutifard-meddic]]`, `[[biblioteca-vendita/direct-response/hopkins-scientific-advertising]]`, `[[biblioteca-vendita/negoziazione/voss-never-split]]`, `[[biblioteca-vendita/consultativa/miller-heiman-strategic-selling]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-proposal/SKILL.md`
