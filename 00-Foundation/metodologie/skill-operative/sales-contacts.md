---
type: skill-operativa
nome: sales-contacts
trigger: /sales contacts <url>
inputs: [URL azienda, eventuale company research pregressa]
outputs: [DECISION-MAKERS.md con buying committee map + Contact Access Score 0-100]
dipendenze: [WebFetch, WebSearch, contact_finder.py, agente sales-contacts]
---

# sales-contacts

## Cosa fa
Motore di intelligence sui decision maker. Mappa il buying committee dell'azienda (Economic Buyer, Champion, Technical Evaluator, End User, Blocker, Coach), costruisce l'organigramma testuale, identifica email pattern aziendale, raccoglie personalization anchor per i top 3-5 contatti (LinkedIn activity, career history, published content, shared connections, interests, trigger events) e disegna una multi-threading strategy calibrata sulla dimensione aziendale. Invocabile standalone o come sub-agente in `prospect`.

## Quando si usa
- Pre-outreach su un nuovo account per multi-threading
- Mapping aggiornato della buying committee dopo cambio di stagione/leadership
- Preparazione di una sequence enterprise con 4-6 stakeholder
- Identificazione del champion in un deal stalled
- Refresh dei contatti su account dormant prima di riattivarli

## Procedura
1. **Phase 1 Contact Identification:** fetch team, about, contact, press, board pages. Estrazione di nomi, titoli, link LinkedIn, bio, foto, email patterns.
2. 7 query WebSearch per LinkedIn lookup di CEO, CTO, VP Engineering, VP Sales, CMO, Head of [department], Director [function].
3. **Org Chart Mapping:** CEO → C-suite → Director → IC chiave. Annota "[Unknown — likely exists]" per ruoli mancanti.
4. Detection email pattern (firstname@, firstname.lastname@, finitial.lastname@, etc.) tramite contact page, blog author, mailto, signatures.
5. **Phase 2 Buying Committee Classification:** assegna a ogni contatto Primary + Secondary role usando l'Assignment Matrix calibrata sulla dimensione aziendale (1-20 → 1-2 ruoli, 21-100 → 2-3, 100-500 → 3-4, 500+ → 5-8).
6. **Phase 3 Personalization Anchor Research:** per i top 3-5 contatti raccoglie LinkedIn activity, career history, published content, shared connections, interests, trigger events. Rating Strong/Moderate/Weak.
7. **Phase 4 Scoring Contact Access Score (0-100):** Decision Makers Identified (0-25), Contact Info Accessibility (0-25), Personalization Anchor Quality (0-25), Warm Paths Available (0-25).
8. **Phase 5 Multi-Threading Strategy:** sequence 4-step (Champion Day 0-1 → Economic Buyer Day 2-3 → Technical Evaluator Day 5-7 → End User Day 7-10) con messaging per ruolo.
9. Output `DECISION-MAKERS.md` con buying committee map, org chart, top 3 priority contacts, multi-threading strategy + terminal scorecard.

## Input richiesti dalla wiki
- `[[10-Account/<azienda>]]` — scheda account
- `[[20-Persone/...]]` — eventuali persone già mappate sull'account
- `[[00-Foundation/icp/...]]` — personas dell'ICP per matching
- Eventuale `[[50-Output/...-research-<account>]]` per leadership data

## Output prodotto
- `DECISION-MAKERS.md` archiviato in `50-Output/YYYY-MM-DD-contacts-<account>.md`
- Sezioni: Executive Summary, Buying Committee Map, Org Chart, Top 3 Priority Contacts (con personalization anchor, career background, recommended approach, suggested opening message), Multi-Threading Strategy, Contact Access Score breakdown, Recommended Outreach Order

## Collegamenti
- Agenti: `[[skill-operative/agenti/sales-contacts]]`
- Script: `[[skill-operative/script/contact_finder]]`
- Skill correlate: `[[skill-operative/sales-prospect]]`, `[[skill-operative/sales-outreach]]`, `[[skill-operative/sales-prep]]`, `[[skill-operative/sales-qualify]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/consultativa/miller-heiman-strategic-selling]]`, `[[biblioteca-vendita/consultativa/lahoutifard-meddic]]`, `[[biblioteca-vendita/challenger/dixon-challenger-customer]]`, `[[biblioteca-vendita/psico/cialdini-influence]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-contacts/SKILL.md`
