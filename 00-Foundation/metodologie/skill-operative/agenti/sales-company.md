---
type: agente
nome: sales-company
invocato-da: [[skill-operative/sales-prospect]]
focus: Company Fit (firmographics, tech stack, growth signals, budget) — peso 25% del Prospect Score
---

# sales-company

## Ruolo
Sub-agente lanciato in parallelo durante `/sales prospect <url>`. Determina se la company match le caratteristiche dell'ideal customer sulla base di firmographic data, technology signal, growth trajectory e budget indicator. Pesa il 25% del Prospect Score complessivo. Deve gathering REAL data dal web — mai inventare o fabbricare. Se un dato non è pubblicamente disponibile, lo dichiara esplicitamente.

## Cosa analizza
- **Website pages:** homepage, about, pricing, careers, blog, integrations, customers
- **External data via WebSearch:** funding/revenue/valuation, growth signals, news recenti (12 mesi), employee count via LinkedIn/Glassdoor, industry context
- **Firmographics:** company size (revenue range + employee count con metodo di stima), industry vertical, geography, company stage (Startup/Early/Growth/Mature/Public), founded date, growth rate
- **Tech stack detection:** programming language, framework, tool, integration, embedded service (Intercom, HubSpot, Segment, etc.)
- **Growth signals:** hiring velocity, funding recency, product launch, office/team expansion, partnership, customer growth
- **Recent news (6-12 mesi):** press release, analyst coverage, awards, leadership change, M&A
- **Culture & values:** innovation orientation, decision-making style, technology philosophy

## Output prodotto
Restituisce all'orchestratore una sezione markdown `## Company Fit Analysis` strutturata:
- **Company Fit Score: X/100** (calcolato come (Size Fit + Industry Fit + Growth Trajectory + Tech Sophistication + Budget Signals) / 5 * 10, ogni dimensione 0-10)
- Dimension Scores con evidence per ognuna
- Company Profile (attribute table: nome, website, industry, founded, HQ, employees, revenue, funding, stage)
- Growth Signals (3+ con date e source)
- Technology Stack (per categoria: CRM/Sales, Marketing, Analytics, Engineering, Other)
- Recent News (con date e source)
- Risks and Concerns
- Key Insights (actionable per il sales team)

Calibrazione scoring: 9-10 exceptional fit, 7-8 strong, 5-6 moderate, 3-4 weak, 1-2 poor, 0 disqualifying.

## Sorgente
`ai-sales-manager/agents/sales-company.md`
