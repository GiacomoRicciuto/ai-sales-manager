---
type: agente
nome: sales-opportunity
invocato-da: [[skill-operative/sales-prospect]]
focus: Opportunity Quality (BANT, pain severity, timeline urgency, champion potential) — peso 20% del Prospect Score
---

# sales-opportunity

## Ruolo
Sub-agente lanciato in parallelo durante `/sales prospect <url>`. Valuta se esiste un'opportunità di vendita genuina e actionable applicando un BANT pre-conversazione basato solo su public signal. Pesa il 20% del Prospect Score. Determina se il prospect ha Budget, Authority structure, Need severity e Timeline urgency per diventare un deal reale, non solo una "bella" azienda.

## Cosa analizza
- **Budget Assessment:** funding signals (recency, amount, time since last raise), revenue indicator, current tech spend (job posts, integration page, tools enterprise), pricing page del loro prodotto, hiring per role che usano la nostra category
- **Pain Points da fonti pubbliche:**
  - Job postings (linguaggio di pain: "fix our broken", "scale our", urgency language)
  - Review sites (Glassdoor frustrations, G2 customer review della loro company)
  - Blog signals (post sulle challenge, migration, post-mortem)
  - Social media (LinkedIn employee post su pain, forum question)
  - Industry context (regulatory, competitive, market shift)
- **Per ogni pain:** description, source, severity (Critical/High/Medium/Low), how manifests, solution relevance, current workaround
- **Authority Structure:** company size → decision speed, organizational complexity (flat vs deep), procurement signals (RFP processes, procurement team), champion accessibility
- **Buying Timeline:** trigger event recenti (funding <6 mesi, leadership change, hiring, launch, competitor move, regulation, failed initiative, renewal), urgency indicator (urgente/immediate, multiple role same function), budget cycle timing, buying stage signal
- **Champion Potential:** chi advocates publicly per la solution type, used similar tool at previous company, scritto/parlato del problem, recently joined da customer nostro, hiring per role impacted

## Output prodotto
Restituisce all'orchestratore una sezione markdown `## Opportunity Quality Analysis`:
- **Opportunity Quality Score: X/100** (media di Budget Signals + Authority Access + Need Severity + Timeline Urgency + Champion Potential, ognuna 0-10, * 10)
- Dimension Scores con evidence
- BANT Scorecard (per ogni dimensione: assessment + key evidence + budget/authority/need/timeline specific findings + risk)
- Pain Points Detected table (severity, source, solution relevance)
- Budget Signals table
- Timeline Assessment con Trigger Events e date
- Champion Candidates
- Opportunity Risks
- Opportunity Summary 2-3 frasi

Calibrazione: never invent pain, evidence-based, trigger events <12 mesi, champion rarely above 7 senza direct evidence.

## Sorgente
`ai-sales-manager/agents/sales-opportunity.md`
