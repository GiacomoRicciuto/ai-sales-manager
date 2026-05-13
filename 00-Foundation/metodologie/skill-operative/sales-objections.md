---
type: skill-operativa
nome: sales-objections
trigger: /sales objections <topic/industry/url>
inputs: [industry, topic specifico o URL prospect, eventuali analisi pregresse]
outputs: [OBJECTION-PLAYBOOK.md con 15 obiezioni universali + industry-specific + competitive + pricing deep dive]
dipendenze: [WebFetch se URL, template objection-playbook.md]
---

# sales-objections

## Cosa fa
Genera script di gestione obiezioni word-for-word, ready-to-use durante call, meeting o email. Copre 15 obiezioni universali (price, status quo, timing, authority, brush-off, past failure, build in-house, missing feature, no ROI, contract lock-in, no priority, no bandwidth, no proof, not interested) + obiezioni industry-specific + obiezioni competitive + pricing deep dive con 5 tactic + 5 tecniche di prevention. Ogni obiezione ha sempre DUE framework di risposta (Feel-Felt-Found e Acknowledge-Bridge-Close) + follow-up question + proof point + walk-away criteria.

## Quando si usa
- Onboarding nuovo rep che deve imparare il playbook di gestione obiezioni
- Refresh prima di una call critica con obiezioni attese
- Risposta scritta a obiezioni ricevute via email
- Preparazione di un sales training/role-play
- Customizzazione su prospect specifico tramite URL

## Procedura
1. **Step 1 Gather Context:** prodotto/servizio, target industry, prospect size (SMB/MM/Ent), top 2-3 competitor, deal size medio, proof point più forti.
2. Se URL fornito → WebFetch del sito + lettura analisi pregresse (`PROSPECT-ANALYSIS.md`, `COMPETITIVE-INTEL.md`) per customizzazione.
3. **Step 2 Framework Setup:** spiegazione FFF e ABC con regole per acknowledge/bridge/close. Tempo target risposta: 15-25 secondi.
4. **Step 3 Le 15 Obiezioni Universali:** per ognuna scrivi What it really means + FFF Response (3-5 frasi) + ABC Response (3-5 frasi) + Follow-up question + Proof point con metriche + When to walk away.
5. **Step 4 Industry-Specific Objections:** 5 obiezioni uniche per il vertical (regolamentazione, tech constraint, buying process, cultural norms).
6. **Step 5 Competitive Objections:** per top 3 competitor scrivi One-sentence positioning + Response script + 3 landmine question + responses a "X è cheaper / has more features / is market leader".
7. **Step 6 Pricing Deep Dive:** 5 tactic (Reframe as Investment, Cost of Inaction, TCO Comparison, Tier Down, Payment Terms Flexibility) ognuna con script template.
8. **Step 7 Objection Prevention:** 5 tecniche (pre-emptive framing, social proof loading, discovery-driven, mutual action plan, champion building).
9. Output `OBJECTION-PLAYBOOK.md` + Practice Guide con role-play scenarios.

## Input richiesti dalla wiki
- `[[10-Account/<azienda>]]` (se applicabile) — per customizzazione
- `[[00-Foundation/obiezioni/...]]` — playbook obiezioni già archiviato dell'azienda
- `[[00-Foundation/azienda/...]]` — proof point e differentiator
- `[[00-Foundation/offerte/...]]` — pricing e packaging
- Eventuali `[[50-Output/...-competitors-<account>]]` per customizzazione competitive

## Output prodotto
- `OBJECTION-PLAYBOOK.md` archiviato in `50-Output/YYYY-MM-DD-objections-<industry|account>.md`
- Sezioni: Quick Reference Matrix, Frameworks (FFF + ABC), 15 Universal Objections complete, 5 Industry-Specific, Competitive Objections per top 3 competitor, Pricing Deep Dive (5 tactic), Objection Prevention (5 tecniche), Practice Guide

## Collegamenti
- Template: `[[skill-operative/template/objection-playbook]]`
- Skill correlate: `[[skill-operative/sales-prep]]`, `[[skill-operative/sales-competitors]]`, `[[skill-operative/sales-outreach]]`, `[[skill-operative/sales-followup]]`, `[[skill-operative/sales-proposal]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/consultativa/sandler-cant-teach-a-kid]]`, `[[biblioteca-vendita/negoziazione/voss-never-split]]`, `[[biblioteca-vendita/psico/cialdini-influence]]`, `[[biblioteca-vendita/consultativa/rackham-spin-selling]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-objections/SKILL.md`
