---
type: agente
nome: sales-strategy
invocato-da: [[skill-operative/sales-prospect]]
focus: Outreach Readiness (channel, messaging framework, personalization per contatto, objection prep, timing, draft first message) — peso 20% del Prospect Score
---

# sales-strategy

## Ruolo
Sub-agente lanciato in parallelo durante `/sales prospect <url>`. Traduce la ricerca degli altri 4 sub-agenti in un piano di outreach actionable. Determina best channel, sceglie messaging framework, costruisce personalization strategy per ogni decision maker, predice obiezioni con risposte preparate, raccomanda timing ottimale e scrive la first outreach message ready-to-send. Pesa il 20% del Prospect Score. Trasforma intelligence in azione.

## Cosa analizza
- **Best Outreach Channel:** valuta tutti i 9 canali (Cold Email, LinkedIn DM, LinkedIn Engage-First, Phone, Warm Intro, Event-Based, Community-Based, Customer Referral, Content Trigger). Mai default a email. Seleziona Primary/Secondary/Tertiary con justification.
- **Messaging Framework:** sceglie tra 6 framework (PAS, BAB, AIDA, Challenger Sale, Social Proof Led, Trigger Event Based) in base al prospect context.
- **Personalization Strategy per Decision Maker:** per i top 3-5 contatti: buying role, their priority, personalization hook specifico, message angle, tone adjustment (technical per CTO, business per CFO, UX per team lead), CTA preference, what NOT to say.
- **Objection Prediction:** 5-7 obiezioni più probabili. Per ogni: exact words, underlying concern, response framework, proof point, redirect. Categorie standard: status quo, budget, timing, authority, trust, complexity, competition, risk.
- **Optimal Timing:** best day (Tue-Thu generalmente), best time of day per timezone, time of month/quarter, trigger event da leveragare, upcoming event come natural conversation starter.
- **Follow-Up Cadence:** Day 1 primary → Day 3 secondary → Day 7 value-add → Day 14 new angle → Day 21 soft touch → Day 30 final.
- **First Message Draft:** email <150 parole o LinkedIn DM <100 parole. Almeno 1 personalization specifica, real pain point/trigger reference, low-friction CTA, no buzzword, no spam trigger. + subject <50 char + LinkedIn connection note <300 char + follow-up message Day 3.

## Output prodotto
Restituisce all'orchestratore una sezione markdown `## Outreach Strategy Analysis`:
- **Outreach Readiness Score: X/100** (media di Personalization Quality + Channel Strategy + Messaging Fit + Objection Preparedness + Timing Opportunity, ognuna 0-10, * 10)
- Dimension Scores
- Recommended Outreach Channel table (Primary/Secondary/Tertiary con rationale)
- Messaging Framework Selected + reasoning + Core Message Structure (Hook/Value/Proof/CTA)
- Personalization Map per contact
- Objection Predictions table (5+ obiezioni)
- Timing Recommendation
- Follow-Up Cadence table
- Draft First Outreach (email + follow-up Day 3 + LinkedIn connection note + LinkedIn DM se primary)
- Outreach Risk Factors
- Strategy Summary 2-3 frasi

Calibrazione: personalization must be real (mai fabricare), messages ready to send senza placeholder, channel justified, timing specifico ("Tuesday morning their time referencing Series B last week").

## Sorgente
`ai-sales-manager/agents/sales-strategy.md`
