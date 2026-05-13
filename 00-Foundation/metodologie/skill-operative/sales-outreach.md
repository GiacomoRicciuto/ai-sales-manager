---
type: skill-operativa
nome: sales-outreach
trigger: /sales outreach <prospect>
inputs: [URL o nome azienda, eventuale contatto specifico, analisi pregresse]
outputs: [OUTREACH-SEQUENCE.md con 5 email + 4 LinkedIn touchpoint + A/B variants + Outreach Readiness Score]
dipendenze: [WebSearch per trigger event, template outreach-cold/warm/referral, agente sales-strategy]
---

# sales-outreach

## Cosa fa
Genera sequence outbound complete, personalizzate, ready-to-send. Ogni email è costruita su uno dei 4 framework provati (Observation → Connection → Ask; Problem → Proof → Ask; Trigger Event; Mutual Connection) selezionato in base ai dati di personalizzazione disponibili. Mai email generica: regola critica = no email prima della personalization research. Output: 5 email (Hook day 1 / Value Add day 3 / Social Proof day 7 / Different Angle day 14 / Breakup day 21) + 4 LinkedIn touchpoint integrati + A/B variants + Outreach Readiness Score 0-100.

## Quando si usa
- Avvio outbound su lead qualificato
- Re-engagement di lead dormant con nuovo trigger event
- Sequence post-evento (conferenza, webinar) con personalizzazione caldissima
- Outreach referral da connessione mutua
- Multi-threading enterprise (una sequence per ogni stakeholder)

## Procedura
1. **Phase 1 Personalization Research (CRITICA):** Company Trigger Research (7 query: funding, launch, hiring, leadership, expansion, partnership, recognition) con classificazione Hot (<30gg) / Warm (<90gg) / Cool (<6 mesi). Personal Trigger Research (LinkedIn, interview, presentation, article). Industry Trigger Research (regulation, market shift, competitor move).
2. Compilazione Research Summary con Best Opening Angle + Secondary Angle.
3. **Phase 2 Framework Selection:** decision tree → Hot trigger? → Mutual connection? → Strong anchor? → Case study? → fallback industry-level.
4. **Phase 3 Email Writing Rules:** subject 4-7 parole no spam trigger, first line MAI "I hope this finds you well", body 100/75 parole, no jargon, ONE CTA per email, low friction.
5. Email 1 Hook (1g): subject + first line specifica + bridge + value statement con metrica + CTA come domanda.
6. Email 2 Value Add (3g): gives senza ask, condividi insight/benchmark/article (non marketing tuo).
7. Email 3 Social Proof (7g): case study same-industry, metriche specifiche, bridge esplicito al prospect.
8. Email 4 Different Angle (14g): cambia stakeholder/perspective (es. da strategic a operational, da cost saving a revenue growth).
9. Email 5 Breakup (21g): sotto 75 parole, no guilt trip, lascia la porta aperta.
10. **Phase 4 LinkedIn Integration:** Day 0 connection request <300 char personalizzata, Day 5 like+comment sostanziale, Day 10 LinkedIn message cross-channel, Day 18 share content rilevante.
11. **Phase 5 A/B Variations** per subject line e opening line.
12. **Phase 6 Sending Best Practices:** deliverability (SPF/DKIM/DMARC), send timing per audience, follow-up rules.
13. **Outreach Readiness Score (0-100):** Personalization Depth + Trigger Events + Channel Strategy + Message-Market Fit.
14. Output `OUTREACH-SEQUENCE.md`.

## Input richiesti dalla wiki
- `[[10-Account/<azienda>]]` — scheda account
- `[[20-Persone/<contatto>]]` — scheda persona con personalization anchor
- `[[00-Foundation/sales-rep/...]]` — firma e tono del rep
- `[[00-Foundation/offerte/...]]` — value prop e proof point
- `[[00-Foundation/azienda/...]]` — case study citabili
- Analisi pregresse: `COMPANY-RESEARCH.md`, `DECISION-MAKERS.md`, `LEAD-QUALIFICATION.md`, `COMPETITIVE-INTEL.md`

## Output prodotto
- `OUTREACH-SEQUENCE.md` archiviato in `50-Output/YYYY-MM-DD-outreach-<account>.md`
- Sezioni: Prospect Summary, Personalization Research (Company/Personal/Industry Triggers), Selected Framework + reasoning, Full 5-Email Sequence (ognuna con subject A/B + body copy-paste-ready + CTA + LinkedIn touchpoint), LinkedIn Touchpoint Summary, Sending Best Practices, Objection Preparation

## Collegamenti
- Agenti: `[[skill-operative/agenti/sales-strategy]]`
- Template: `[[skill-operative/template/outreach-cold]]`, `[[skill-operative/template/outreach-warm]]`, `[[skill-operative/template/outreach-referral]]`
- Skill correlate: `[[skill-operative/sales-prospect]]`, `[[skill-operative/sales-contacts]]`, `[[skill-operative/sales-followup]]`, `[[skill-operative/sales-objections]]`, `[[skill-operative/sales-prep]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/direct-response/hopkins-scientific-advertising]]`, `[[biblioteca-vendita/direct-response/schwartz-breakthrough-advertising]]`, `[[biblioteca-vendita/psico/cialdini-influence]]`, `[[biblioteca-vendita/challenger/dixon-challenger-sale]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-outreach/SKILL.md`
