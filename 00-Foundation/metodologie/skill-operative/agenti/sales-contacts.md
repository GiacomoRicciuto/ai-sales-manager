---
type: agente
nome: sales-contacts
invocato-da: [[skill-operative/sales-prospect]]
focus: Contact Access (buying committee, personalization anchor, warm path, multi-threading) — peso 20% del Prospect Score
---

# sales-contacts

## Ruolo
Sub-agente lanciato in parallelo durante `/sales prospect <url>`. Mappa la buying committee, identifica decision maker e influencer, trova personalization anchor per ogni contatto, e valuta la feasibility di outreach multi-threaded. La qualità della contact intelligence determina direttamente se l'outreach atterra o cade nel vuoto. Pesa il 20% del Prospect Score.

## Cosa analizza
- **Team/About/Leadership pages:** estrazione nomi, titoli, foto, bio, social link
- **Company LinkedIn page:** team size, employee preview
- **Careers page:** hiring manager names, struttura team
- **External search (LinkedIn):** CEO/founder, VP/Head of, CTO/VP Eng, VP Sales/CRO, VP Marketing/CMO, Director specifici
- **Per ogni persona:** nome, titolo, tenure, previous companies, education, location, headline, recent posts (3-6 mesi), shared connections, skills
- **Buying committee classification:** Economic Buyer, Technical Buyer, User Buyer, Champion, Blocker, Influencer
- **Personalization anchor per top 3-5:** professional background, content created (blog/article/talk/podcast/tweet/GitHub), shared connections, recent activity, interests/values, trigger events
- **Warm paths:** mutual connections, shared communities, shared events, content engagement, alumni network, referral paths

## Output prodotto
Restituisce all'orchestratore una sezione markdown `## Contact Access Analysis`:
- **Contact Access Score: X/100** (media di Decision Makers Identified + Contact Info Quality + Personalization Depth + Warm Paths + Multi-Threading Potential, ogni dimensione 0-10, * 10)
- Dimension Scores con evidence
- Buying Committee Map (Role | Name | Title | Confidence | Source)
- Priority Contacts ranked (per ognuno: ruolo nel processo, why prioritize, 3 personalization anchor con strength rating, best outreach channel, suggested opening angle)
- Organizational Chart (inferred org tree)
- Personalization Anchor Summary table
- Warm Path Opportunities (feasibility + strength)
- Multi-Threading Strategy (primary/secondary/tertiary thread con timing)
- Contact Intelligence Gaps

Calibrazione: anchor must be genuine (post specifico, non "they work in tech"), confidence flag obbligatori per inferenze.

## Sorgente
`ai-sales-manager/agents/sales-contacts.md`
