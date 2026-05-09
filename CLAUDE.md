# CLAUDE.md — `apac-regulations`

> **Scope:** Project-level memory for the APAC financial-services regulatory research reference.

## What this repo is

A **research reference** covering financial-services regulatory and technology constraints across **10 APAC markets**:

| Market | Primary Regulator(s) | Key Frameworks |
|---|---|---|
| Australia | APRA, ASIC, OAIC | CPS 234, CPS 230, Privacy Act |
| China | PBOC, CBIRC, CAC | DSL, PIPL, MLPS 2.0, Cybersecurity Law |
| Hong Kong | HKMA, SFC, PCPD | SA-2, OR-2, PDPO |
| India | RBI, SEBI, MeitY | RBI Cyber Framework, DPDP Act 2023 |
| Indonesia | OJK, BI, KOMINFO | OJK 11/POJK.03/2022, PDP Law (UU PDP) |
| Japan | FSA, PPC | FISC Security Guidelines, APPI |
| Malaysia | BNM, Securities Comm. | RMiT, PDPA |
| Singapore | MAS, IMDA, PDPC | MAS TRM, MAS Notice 644, PDPA |
| Taiwan | FSC, NCC | Cybersecurity Mgmt Act, PDPA |
| Thailand | BOT, SEC | BOT Notification on IT Risk, PDPA |

## Coverage Domains (per market)

For each market, structure findings under:

1. **Data localisation** — must data be stored in-country? Which classes? Cross-border transfer rules.
2. **System localisation** — must systems run in-country? Disaster recovery requirements.
3. **Legal entity segregation** — must local entities have separate infra/data plane?
4. **Cloud adoption mandates** — public cloud allowed? Notification/approval thresholds? Outsourcing rules.
5. **Cyber & operational resilience** — incident reporting timelines, board-level accountability, third-party risk.
6. **Identity / KYC / AML** — local KYC norms, biometric rules, AML obligations.
7. **AI / model risk** — emerging AI governance frameworks where they exist.

## Sourcing Rules

- **Primary sources only** for normative text (regulator websites, gazetted notices, official English translations).
- **Secondary sources** (Big 4 advisories, law firm bulletins) acceptable as interpretation aids — always cite alongside the primary.
- **Date every claim** — APAC regulation moves fast; an unsourced "as of" claim ages badly.
- **No machine translation as authoritative** — flag where only an unofficial translation is available.

## What This Repo Is NOT

- **Not legal advice.** Every page should make this clear in a banner.
- **Not a snapshot in time** — must track which regulations are in force, in transition, in consultation.
- **Not exhaustive** — focused on **financial services + cloud + cyber**. Tax, employment, consumer protection are out of scope unless they touch the above.

## Structure & File Conventions

- One file per market: `markets/<iso2>-<market>.md` (e.g. `markets/sg-singapore.md`).
- Cross-market comparison tables: `compare/<dimension>.md` (e.g. `compare/data-localisation.md`).
- Living documents: every file has a **"Last verified"** date in the front matter.

## Companion Repo

- The `zta-financial-institution-c4-ai` reference architecture references this repo for regional constraints. When updating regulatory facts here, consider whether the C4 reference needs a companion update.

## What NOT to Do

- **Don't paraphrase a regulation in a way that could be read as legal interpretation.** Quote the source, then summarise — never invert.
- **Don't reproduce regulator text verbatim** beyond fair-use snippets — link to the primary.
- **Don't generalise across "APAC"** — every market is materially different. Comparison tables are fine; sweeping statements are not.
- **Don't include screenshots of paywalled content.**

## When Asked to Add a Market

Push back if the market doesn't have a financial-services regulator with public English-language guidance — better to keep the set tight and accurate than broad and stale.
