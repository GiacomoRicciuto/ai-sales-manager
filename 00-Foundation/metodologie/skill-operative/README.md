---
type: indice
nome: skill-operative
---

# Skill Operative — Indice

Catalogo navigabile delle 14 skill operative del progetto `ai-sales-manager` organizzate per fase del funnel commerciale. Ogni skill espone un comando CLI `/sales ...` e produce un file di output archiviabile nel vault. Le metodologie strategiche (il "perché") sono nella `[[biblioteca-vendita/README|biblioteca-vendita]]`; queste skill sono il "come" operativo.

---

## Orchestratore

| Skill | Trigger | Output | Cosa fa |
|-------|---------|--------|---------|
| `[[sales]]` | `/sales <comando>` | varia in base al sub-skill | Punto di ingresso unico: routing al sub-skill corretto, applicazione standard di output e metodologia Prospect Score |

---

## Fase 1 — Awareness / Prospect (chi vale la pena cacciare)

| Skill | Trigger | Output | Cosa fa |
|-------|---------|--------|---------|
| `[[sales-icp]]` | `/sales icp <description>` | `IDEAL-CUSTOMER-PROFILE.md` | Costruisce l'ICP completo su 6 dimensioni + negative ICP + scoring rubric + buyer personas + prospecting playbook |
| `[[sales-prospect]]` | `/sales prospect <url>` | `PROSPECT-ANALYSIS.md` | Audit completo prospect con 5 sub-agenti paralleli, Prospect Score 0-100 e first email ready-to-send |
| `[[sales-research]]` | `/sales research <url>` | `COMPANY-RESEARCH.md` | Deep dive aziendale su 8 dimensioni + Company Fit Score 0-100 |

---

## Fase 2 — Discovery / Qualify (chi è veramente in target)

| Skill | Trigger | Output | Cosa fa |
|-------|---------|--------|---------|
| `[[sales-qualify]]` | `/sales qualify <url>` | `LEAD-QUALIFICATION.md` | Qualificazione BANT + MEDDIC con Opportunity Quality Score 0-100 e grade A/B/C/D |
| `[[sales-contacts]]` | `/sales contacts <url>` | `DECISION-MAKERS.md` | Mappa buying committee, org chart, top 3 contatti con personalization anchor, multi-threading strategy |
| `[[sales-competitors]]` | `/sales competitors <url>` | `COMPETITIVE-INTEL.md` | Detection current solutions del prospect + battle card sales-focused per ogni competitor |

---

## Fase 3 — Engagement / Outreach (come bussare alla porta)

| Skill | Trigger | Output | Cosa fa |
|-------|---------|--------|---------|
| `[[sales-outreach]]` | `/sales outreach <prospect>` | `OUTREACH-SEQUENCE.md` | 5-email sequence personalizzata + 4 LinkedIn touchpoint + A/B variants + Outreach Readiness Score |
| `[[sales-prep]]` | `/sales prep <url>` | `MEETING-PREP.md` | Brief meeting con cheat sheet, talking point, 10 discovery question, 5 obiezioni attese, agenda |

---

## Fase 4 — Negotiation / Proposal (chiudere)

| Skill | Trigger | Output | Cosa fa |
|-------|---------|--------|---------|
| `[[sales-objections]]` | `/sales objections <topic>` | `OBJECTION-PLAYBOOK.md` | 15 obiezioni universali + industry + competitive + pricing deep dive con FFF e ABC framework |
| `[[sales-proposal]]` | `/sales proposal <client>` | `CLIENT-PROPOSAL.md` | Proposta sales-document in 11 sezioni + 6-email follow-up sequence |

---

## Fase 5 — Close / Followup (mantenere il momentum)

| Skill | Trigger | Output | Cosa fa |
|-------|---------|--------|---------|
| `[[sales-followup]]` | `/sales followup <prospect>` | `FOLLOWUP-SEQUENCE.md` | 5 scenari di follow-up (post-meeting, post-demo, post-proposal, ghost recovery, nurture) multi-channel |

---

## Fase 6 — Reporting (vedere il pipeline)

| Skill | Trigger | Output | Cosa fa |
|-------|---------|--------|---------|
| `[[sales-report]]` | `/sales report` | `SALES-REPORT.md` | Compila tutte le analisi pregresse in pipeline dashboard, score distribution, top 5, weekly focus |
| `[[sales-report-pdf]]` | `/sales report-pdf` | `SALES-REPORT-YYYY-MM-DD.pdf` | Genera versione PDF professionale del pipeline report con grafici color-coded |

---

## Risorse di supporto

### Agenti (sub-skill invocate da `/sales prospect`)
- `[[agenti/sales-company]]` — Company Fit (firmographics, tech stack, growth) — 25% del score
- `[[agenti/sales-contacts]]` — Contact Access (buying committee, personalization, warm path) — 20%
- `[[agenti/sales-opportunity]]` — Opportunity Quality (BANT, pain, timeline, champion) — 20%
- `[[agenti/sales-competitive]]` — Competitive Position (current solutions, switching, gap) — 15%
- `[[agenti/sales-strategy]]` — Outreach Readiness (channel, messaging, objection prep, first draft) — 20%

### Script (automation Python)
- `[[script/analyze_prospect]]` — estrazione strutturata dati da homepage aziendale
- `[[script/lead_scorer]]` — scoring deterministico BANT + MEDDIC da JSON di signal
- `[[script/contact_finder]]` — estrazione contatti da pagine team/leadership con classificazione seniority e buying role
- `[[script/generate_pdf_report]]` — generazione PDF professionale del pipeline report con reportlab

### Template (boilerplate riutilizzabili)
- `[[template/meeting-prep]]` — brief meeting con cheat sheet
- `[[template/outreach-cold]]` — 5-email cold sequence con LinkedIn touchpoint
- `[[template/outreach-warm]]` — 3-email warm sequence con shared context
- `[[template/outreach-referral]]` — 3-email referral sequence con mutual connection
- `[[template/objection-playbook]]` — playbook LAER con 15 obiezioni universali
- `[[template/proposal-template]]` — proposta cliente in 11 sezioni con three-tier pricing
