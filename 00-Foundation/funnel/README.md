---
type: foundation-index
sezione: funnel
status: TODO-imprenditore
---

# Funnel marketing — Materiali

> **TODO imprenditore.** In questa cartella documenta i materiali e le tappe del funnel marketing/sales. Serve a contestualizzare ogni lead: da quale canale è arrivato, quali contenuti ha consumato, in che stadio del funnel si trova.

## Cosa va qui
- **Stadi del funnel** (TOFU/MOFU/BOFU o nomenclatura propria) con definizioni operative.
- **Mapping canali → stadi**: SEO, ads, eventi, referral, outbound, content.
- **Materiali per stadio**: white paper, case study, webinar, demo, free audit.
- **Lead magnet attivi** con conversion rate noti.
- **Trigger di passaggio** stadio → stadio (es. "ha richiesto demo" = MQL → SQL).

## Struttura suggerita

```
funnel/
├── README.md            (questo file)
├── stadi.md             (definizioni operative di ogni stadio)
├── canali.md            (mapping canale → stadio → metriche)
├── materiali/
│   ├── tofu-blog-post-X.md
│   ├── mofu-white-paper-Y.md
│   └── bofu-case-study-Z.md
```

## Convenzione frontmatter materiale
```yaml
---
type: materiale-funnel
nome: Case study ACME — efficienza energetica 2025
stadio: bofu
canale: outbound | sito | linkedin | evento
conversion_rate: 12%
fonte: [[raw/materiali/case-study-acme.pdf]]
---
```

## Riferimenti
- `[[../icp/README]]` — chi entra nel funnel
- `[[../offerte/README]]` — cosa offriamo a ogni stadio
- `[[../../00-Foundation/metodologie/biblioteca-vendita/direct-response/schwartz-breakthrough-advertising]]` — livelli di consapevolezza del prospect
- `[[../../00-Foundation/metodologie/biblioteca-vendita/etica/godin-permission-marketing]]` — funnel basati sul consenso
