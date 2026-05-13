---
type: skill-operativa
nome: sales-competitors
trigger: /sales competitors <url>
inputs: [URL prospect, eventuali analisi pregresse]
outputs: [COMPETITIVE-INTEL.md con battle card per ogni soluzione attuale del prospect]
dipendenze: [WebFetch, WebSearch, agente sales-competitive]
---

# sales-competitors

## Cosa fa
Sales competitive intelligence focalizzata. Analizza quali tool, servizi e soluzioni il prospect usa ATTUALMENTE e genera battle card actionable per vincere il deal contro ogni competitor rilevato. NON è un'analisi di mercato generica: tutto è orientato al singolo prospect e al singolo deal. Output: detection table delle current solutions, battle card complete (strengths, weaknesses, switching cost, switching trigger, landmine questions), feature gap analysis, win/loss patterns, recommended competitive strategy.

## Quando si usa
- Pre-pitch su deal contro incumbent identificato
- Preparazione di sales rep prima di una demo competitiva
- Refresh delle battle card per deal in negoziazione finale
- Onboarding nuovo rep che deve imparare il landscape competitivo
- Post-loss analysis per capire perché si perde contro X

## Procedura
1. **Step 1 Current Solution Detection (parallelo):** 6 metodi di detection: website tech analysis (script tag, meta, integration badge, "powered by", login pages, API docs), job posting analysis (tool-specific requirements = High confidence), case study & partnership search, review site search (G2, Capterra), tech stack detection services (BuiltWith, StackShare), social signal analysis.
2. Ogni detection annotata con confidence (High/Medium/Low) e source.
3. **Step 2 Categorize:** organizza in tabella per categoria (CRM, marketing automation, analytics, support, PM, communication). Evidenzia quelle che overlap con la propria offerta.
4. **Step 3 Battle Card per ogni competitor rilevante:** What the Prospect Uses Them For, Competitor Strengths (3-5 onesti), Competitor Weaknesses (3-5 specifiche), Your Advantages with proof, Their Advantages + neutralizzazione, Switching Cost Assessment (technical/financial/organizational/data/timeline), Switching Triggers, Landmine Questions (5), Trap to Avoid, Positioning Statement.
5. **Step 4 Feature Gap Analysis:** tabella side-by-side onesta (include feature dove perdi).
6. **Step 5 Win/Loss Pattern Recognition:** 3-5 ragioni per cui vinci e 3-5 per cui perdi contro quel competitor. Deal qualification signals derivati.
7. **Step 6 Recommended Competitive Strategy:** strategy summary, conversation sequence ordinata, what to lead with, what to avoid, displacement timeline.
8. Output `COMPETITIVE-INTEL.md` con detection sources data-stamped.

## Input richiesti dalla wiki
- `[[10-Account/<azienda>]]` — scheda account
- `[[00-Foundation/azienda/...]]` — propri differentiator e proof point
- `[[00-Foundation/offerte/...]]` — confronto pricing/feature
- Eventuali `[[50-Output/...-prospect-<account>]]` o research file per arricchimento

## Output prodotto
- `COMPETITIVE-INTEL.md` archiviato in `50-Output/YYYY-MM-DD-competitors-<account>.md`
- Sezioni: Executive Summary, Current Solutions Detected, Battle Cards (una per competitor), Feature Gap Analysis, Win/Loss Patterns, Competitive Positioning Statements, Switching Cost Assessment, Recommended Competitive Strategy, Detection Sources

## Collegamenti
- Agenti: `[[skill-operative/agenti/sales-competitive]]`
- Skill correlate: `[[skill-operative/sales-prospect]]`, `[[skill-operative/sales-objections]]`, `[[skill-operative/sales-prep]]`, `[[skill-operative/sales-proposal]]`
- Metodologie strategiche (biblioteca): `[[biblioteca-vendita/challenger/dixon-challenger-sale]]`, `[[biblioteca-vendita/consultativa/miller-heiman-strategic-selling]]`, `[[biblioteca-vendita/negoziazione/voss-never-split]]`, `[[biblioteca-vendita/psico/cialdini-pre-suasion]]`

## Riferimento sorgente
`ai-sales-manager/skills/sales-competitors/SKILL.md`
