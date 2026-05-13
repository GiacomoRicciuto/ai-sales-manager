---
type: biblioteca-index
sezione: biblioteca-vendita
totale-schede: 44
famiglie: 10
---

# Biblioteca della vendita

> 44 schede-libro che codificano l'intero corpus della teoria di vendita — dai pionieri storici (Aristotele, Hopkins, Ogilvy, Carnegie) ai framework moderni (MEDDIC, Challenger, SPIN, Gap Selling, Sandler), passando per la negoziazione (Voss, Fisher, Ury, Malhotra, Diamond), la psicologia (Cialdini, Kahneman, Klaff, Haidt, Damasio), e i sistemi (Ross, Roberge, Holmes, Coleman, van der Kooij).

Mentre le **skill operative** (`[[../skill-operative/README]]`) spiegano *come* eseguire una mossa commerciale, la biblioteca spiega *perché* quella mossa funziona e *quando* applicare quale approccio. Combinare sempre tattica + strategia.

## Le 10 famiglie

| Famiglia | Libri | Focus | Quando attivarla |
|----------|-------|-------|------------------|
| `[[atlante/atlante]]` | 1 | Atlante del corpus complessivo — meta-skill orchestratrice italiana | Triage iniziale, scelta del libro giusto, post-mortem di call |
| `[[challenger/README]]` | 4 | Insegnare al buyer una nuova prospettiva, sfidare lo status quo | Outbound enterprise, prospect senza pain dichiarato, cicli lunghi |
| `[[classica/README]]` | 2 | Retorica antica + relazione interpersonale | Rapport building, opener, comunicazione di base |
| `[[consultativa/README]]` | 7 | Discovery profonda, qualifica disciplinata, soluzione su misura | B2B mid-market e enterprise, deal complessi |
| `[[darkside/README]]` | 2 | Tecniche persuasive aggressive — uso etico raccomandato | Conoscenza difensiva, riconoscere manipolazione, ambienti competitivi duri |
| `[[direct-response/README]]` | 6 | Copy persuasivo, livelli di consapevolezza, advertising scientifico | Outreach scritto, lead magnet, landing, sales letter |
| `[[etica/README]]` | 5 | Vendita basata sul valore, permission marketing, relazione lunga | SaaS PLG, founder-led, brand awareness, retention |
| `[[negoziazione/README]]` | 5 | Negoziazione integrativa e tattica | Proposal, sconto, negoziazione contrattuale, gestione impasse |
| `[[psico/README]]` | 7 | Psicologia cognitiva e sociale applicata | Obiezioni, pitch, framing, bias decisionali |
| `[[sistemica/README]]` | 5 | Costruzione di sistemi commerciali ripetibili | Sales ops, scaling, ICP fitting, retention, predictable revenue |

## Matrice libro × stage del funnel

Linee guida per "quale libro consultare a quale stage". Non esclusivo — molti libri sono utili a più stage.

| Stage | Libri principali |
|-------|------------------|
| **ICP / Prospect** | Ross *Predictable Revenue*, Roberge *Sales Acceleration*, Holmes *Ultimate Sales Machine*, Godin *This is Marketing*, Schwartz *Breakthrough Advertising* |
| **Outreach** | Dixon *Challenger Sale*, Iannarino *Eat Their Lunch*, Ogilvy *On Advertising*, Hopkins *Scientific Advertising*, Bettger *How I Raised Myself*, Carnegie *How to Win Friends*, Godin *Permission Marketing* |
| **Discovery** | Rackham *SPIN Selling*, Keenan *Gap Selling*, Sandler *Can't Teach a Kid*, Hanan *Consultative Selling*, Bosworth *Solution Selling* |
| **Qualification** | Lahoutifard *MEDDIC*, Miller-Heiman *Strategic Selling*, Iannarino *Lost Art of Closing* |
| **Prep / Pitch** | Klaff *Pitch Anything*, Klaff *Flip the Script*, Cialdini *Pre-Suasion*, Dixon *Challenger Customer* |
| **Objections** | Voss *Never Split the Difference*, Ury *Getting Past No*, Cialdini *Influence*, Sandler *Can't Teach a Kid*, Kahneman *Thinking Fast & Slow* |
| **Proposal / Negotiation** | Fisher *Getting to Yes*, Malhotra *Negotiation Genius*, Diamond *Getting More*, Voss *Never Split*, Lahoutifard *MEDDIC* |
| **Close** | Iannarino *Lost Art of Closing*, Belfort *Way of the Wolf* (uso etico), Greene *48 Laws of Power* (consapevolezza difensiva) |
| **Follow-up / Retention** | Coleman *Never Lose a Customer Again*, Burg *Go-Giver*, Covey *7 Habits*, Bettger *How I Raised Myself* |
| **Cross / Account Expansion** | Holmes *Ultimate Sales Machine*, Miller-Heiman *Strategic Selling*, van der Kooij *SaaS Sales Blueprints* |
| **Foundation / Strategia** | Aristotele *Retorica*, Pink *To Sell Is Human*, Damasio *Descartes' Error*, Haidt *Righteous Mind* |

## Come l'LLM la usa

Quando una skill operativa viene invocata (`/sales prep`, `/sales objections`, `/sales proposal`), il workflow di Interrogazione (vedi `[[../../../CLAUDE]]` §6) prevede di caricare **almeno una scheda-libro pertinente** insieme al contesto entità. Le schede sono brevi e strutturate proprio per essere "caricabili" come moduli strategici.

Esempi:
- `/sales prep` su discovery enterprise → carica `[[consultativa/rackham-spin-selling]]` + `[[consultativa/lahoutifard-meddic]]`
- `/sales objections` su prezzo → carica `[[negoziazione/voss-never-split]]` + `[[psico/cialdini-influence]]`
- `/sales outreach` cold enterprise → carica `[[challenger/dixon-challenger-sale]]` + `[[direct-response/hopkins-scientific-advertising]]`
- `/sales proposal` enterprise multi-stakeholder → carica `[[consultativa/miller-heiman-strategic-selling]]` + `[[negoziazione/fisher-getting-to-yes]]`

## Riferimenti
- `[[../skill-operative/README]]` — registro delle 14 skill operative tattiche
- `[[../meta/llm-wiki-pattern]]` — bibbia primaria del pattern wiki
- `[[../../../CLAUDE]]` — schema operativo del vault (sezione 10)
