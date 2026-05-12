# apac-regulations

[![Scope](https://img.shields.io/badge/Scope-FinTech%20architecture%20constraints%20%C2%B7%2010%20APAC%20markets-2ea44f)](#coverage)
[![Format](https://img.shields.io/badge/Format-Single--page%20HTML-1f6feb)](./index.html)
[![Live](https://img.shields.io/badge/Live-apac--regulations.vercel.app-000000?logo=vercel&logoColor=white)](https://apac-regulations.vercel.app/)
[![Last reviewed](https://img.shields.io/badge/Last%20reviewed-2026--04--19-B45309)](./VERIFICATION.md)
[![License](https://img.shields.io/badge/License-MIT-blue)](./LICENSE)

**TL;DR** — A single-page research brief on **technology architecture design constraints** imposed by financial-services regulators across **10 APAC jurisdictions**, covering **12 dimensions** per jurisdiction with binding-instrument citations. Plain HTML + CSS + a small block of vanilla JS for the interactive synthesis views — no framework, no build step, no external runtime dependencies. Deployed on Vercel.

> **Live:** https://apac-regulations.vercel.app/

![APAC FinTech Architecture brief — masthead, hero stats, severity heat map, and the start of the Indonesia jurisdiction.](./preview.png)

---

## What this repo is

A static, **architect-grade reference** for solutions and security architects sizing up regional constraints on data residency, workload placement, cyber resilience, and AI/model risk in APAC financial services.

- **Audience:** solutions architects, security architects, technology risk and outsourcing leads.
- **Form factor:** a single `index.html`. No framework, no build, no runtime libraries fetched at page load; just self-contained HTML, CSS, and inline vanilla JS.
- **Tone:** primary-source citations, dated claims, no legal advice.

## What this repo is *not*

- **Not legal advice.** Use as architectural orientation; verify against the primary regulator before relying on it for compliance decisions.
- **Not exhaustive.** Focused on **financial services + cloud + cyber + AI risk**. Tax, employment, and consumer protection are out of scope unless they touch those domains.
- **Not a snapshot.** Claims are dated; expect drift between publication date and current state.

---

## Coverage

### Jurisdictions (10)

| # | Market | Primary regulator(s) |
|---|---|---|
| 01 | Indonesia | OJK, BI, KOMINFO |
| 02 | India | RBI, SEBI, MeitY |
| 03 | Taiwan | FSC, NCC |
| 04 | Japan | FSA, PPC, FISC |
| 05 | China (Mainland) | PBOC, CBIRC, CAC |
| 06 | Hong Kong SAR | HKMA, SFC, PCPD |
| 07 | Singapore | MAS, IMDA, PDPC |
| 08 | Malaysia | BNM, Securities Commission |
| 09 | Australia | APRA, ASIC, OAIC |
| 10 | Thailand | BOT, SEC |

Ordering follows the brief's editorial sequence, not alphabetical.

### Dimensions (12 per jurisdiction)

1. Regulatory Bodies
2. Data Localization
3. System & Process Localization
4. Legal Entity Segregation
5. Workload Isolation & Placement
6. Cross-Border Data Flow
7. Cybersecurity Standards
8. API & Open Banking
9. Cloud & Infrastructure
10. Licensing & Compliance Tech
11. Encryption & Authentication
12. Key Legislation

Each jurisdiction closes with an **Architectural Implications** callout — five design constraints a practitioner can apply today.

---

## Page features

Beyond the per-country sections, the brief includes synthesis views designed to be useful in a workshop or design review:

- **At a Glance heat map** — 10 × 4 severity matrix across the four topology-shaping dimensions, with sort toggles (default / strictest-first / A → Z) and per-cell anchor instruments on hover.
- **Legislative timeline** — SVG timeline of binding instruments from 2008 → 2026.
- **Comparative matrix** — full 10-row, 4-column table view of the same severity data.
- **Comparison Lab** — pick up to three jurisdictions and view their binding-severity profile side by side.
- **Decision Flow** — SVG decision tree for siting a new workload by data class, jurisdiction, and regulator posture.
- **Glossary** — category filter (regulators / instruments & standards / architectural concepts) and live search by abbreviation, full name, or jurisdiction.
- **Dark mode** — theme toggle persisted to `localStorage`.
- **Sticky TOC** — left sidebar on desktop, top bar on mobile.

A four-tier severity scale (**Strict · Moderate · Light · None**) underpins both the heat map and the matrix.

---

## Repository layout

```
.
├── index.html        # Self-contained brief — open this to read the document
├── preview.png       # Hero screenshot used in this README
├── LICENSE           # MIT
├── README.md
├── VERIFICATION.md   # Third-party accuracy check (as of 2026-04-17)
├── screenshot.mjs    # Local helper: Playwright capture at 3 viewports (gitignored)
└── screenshots/      # Generated full-page + sliced PNGs (gitignored)
```

## View it locally

The page is fully self-contained — open it directly in a browser:

```bash
xdg-open index.html        # Linux
open index.html            # macOS
```

No server, install, or build step is required.

## Capture screenshots

The `screenshot.mjs` helper (kept local, gitignored) renders the page at three viewports and writes full-page PNGs to `./screenshots/`.

```bash
npm install                # one-time: installs playwright
npx playwright install     # one-time: fetches browser binaries
node screenshot.mjs        # captures ./index.html by default
node screenshot.mjs https://apac-regulations.vercel.app/   # or a URL
```

Viewports captured:

| Name    | Width | Height |
|---------|------:|-------:|
| mobile  |   375 |    812 |
| tablet  |   768 |   1024 |
| desktop |  1440 |    900 |

`deviceScaleFactor` is held at 1 — full-page captures of long pages otherwise overflow Chrome's max canvas (~16384 px).

## Sourcing rules

- **Primary sources only** for normative claims: regulator websites, gazetted notices, official English translations.
- **Secondary sources** (Big 4, law firm bulletins) acceptable as interpretation aids, always cited alongside the primary.
- **Every claim is dated** — APAC regulation moves fast.
- **Machine translation is never authoritative** — flagged where only an unofficial translation is available.

For a third-party correctness check, see [`VERIFICATION.md`](./VERIFICATION.md).

## Disclaimer

This brief is **not legal advice** and is **not a substitute for engagement with qualified counsel or the regulator**. Use it as a high-level architectural guide; verify specific requirements against the primary document repositories of the respective national regulators.

## License

[MIT](./LICENSE) © 2026 James Buckett
