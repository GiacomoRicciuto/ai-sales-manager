---
type: skill-operativa
nome: sales-followup
trigger: /sales followup <prospect>
inputs: [contatto/azienda, tipo interazione precedente, key discussion points, deal stage, temperature]
outputs: [FOLLOWUP-SEQUENCE.md con sequence scelta + LinkedIn + voicemail + SMS + cadence calendar]
dipendenze: [analisi pregresse del prospect]
---

# sales-followup

## Cosa fa
Genera sequence strategiche di follow-up dopo un'interazione iniziale (meeting, demo, proposta, silenzio post-engagement, long-term nurture). NON è cold outreach: è follow-up che fa leva su contesto condiviso. Ogni email deve aggiungere NEW value, fare reference a punti specifici della conversazione precedente, e contenere un clear next step. 5 scenari diversi (Post-Meeting, Post-Demo, Post-Proposal, Ghost Recovery, Nurture) con numero email calibrato. Integra multi-channel: LinkedIn touchpoint, voicemail script 30 secondi, SMS per warm lead opted-in.

## Quando si usa
- Riepilogo same-day post discovery call
- Sequence post-demo per accelerare la decisione
- Follow-up post-proposta inviata
- Recovery di prospect ghosted dopo engagement
- Nurture mensile su prospect buon fit ma non ready

## Procedura
1. **Step 1 Gather Context:** 10 input (nome, azienda, tipo interazione, data, key discussion points, pain, agreed next step, ruolo, deal stage Early/Active/Near/Stalled, temperature Hot/Warm/Cool/Cold).
2. Auto-incorporazione da file pregressi (`PROSPECT-ANALYSIS.md`, `MEETING-PREP.md`, etc.).
3. **Step 2 Select Scenario:**
   - **Post-Meeting (3 email):** Summary+Next Steps (same day) → Value Reinforcement (3g) → Decision Nudge (5g)
   - **Post-Demo (4 email):** Recap+Resources (same day) → Address Objections (3g) → Social Proof (5g) → Decision Timeline (7g)
   - **Post-Proposal (5 email):** Delivery → Walkthrough Offer (2g) → Value-Add (5g) → Direct Check-In (5g) → Breakup (10g)
   - **Ghost Recovery (3 email):** Pattern Interrupt → New Angle (7g) → Honest Breakup (14g)
   - **Nurture (6 monthly):** alternate Industry Insight / Resource / Case Study / Thought Leadership / Event Invite / Personal Check-In
4. Per ogni email: subject specifico (no "checking in"), open con riferimento concreto, 1 CTA, sotto 100 parole.
5. **Step 3 Multi-Channel Integration:** LinkedIn touchpoint (view profile, like+comment, share, DM con format specifico). 2 voicemail script 30 secondi. 2-3 SMS template per hot/warm lead.
6. **Step 4 Cadence Recommendations:** matrice temperature × deal stage per timing. Channel cadence rules. Time-of-day per role.
7. **Step 5 Breakup Best Practices:** respectful, no guilt-trip, leave door open, factual scarcity, sotto 60 parole.
8. Output `FOLLOWUP-SEQUENCE.md` con cadence calendar tabellare.

## Input richiesti dalla wiki
- `[[10-Account/<azienda>]]` — scheda account
- `[[20-Persone/<contatto>]]` — scheda persona
- `[[30-Trattative/<deal>]]` — trattativa con stage, history, agreed next step
- `[[40-Interazioni/<meeting>]]` — verbale dell'interazione precedente con key points
- `[[00-Foundation/sales-rep/...]]` — firma e tono

## Output prodotto
- `FOLLOWUP-SEQUENCE.md` archiviato in `50-Output/YYYY-MM-DD-followup-<account>.md`
- Sezioni: Prospect Context, Selected Scenario, Sequence completa (ogni email con timing + channel + body), Phone Scripts, SMS Templates, Cadence Calendar, Best Practices Applied

## Collegamenti
- Skill correlate: `[[skill-operative/sales-outreach]]`, `[[skill-operative/sales-prep]]`, `[[skill-operative/sales-proposal]]`, `[[skill-operative/sales-objections]]`, `[[skill-operative/sales-qualify]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/consultativa/sandler-cant-teach-a-kid]]`, `[[biblioteca-vendita/negoziazione/voss-never-split]]`, `[[biblioteca-vendita/consultativa/miller-heiman-strategic-selling]]`, `[[biblioteca-vendita/direct-response/schwartz-breakthrough-advertising]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-followup/SKILL.md`
