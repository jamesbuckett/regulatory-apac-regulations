# apac-regulations

![Scope](https://img.shields.io/badge/Scope-FinTech%20architecture%20constraints%20%C2%B7%2010%20APAC%20markets-2ea44f)
![Format](https://img.shields.io/badge/Format-Single--page%20HTML-1f6feb)
![License](https://img.shields.io/badge/License-MIT-blue)

**TL;DR** — A single-page research brief on **technology architecture design constraints** imposed by financial-services regulators across **10 APAC jurisdictions**, covering **12 dimensions** per jurisdiction with binding-instrument citations. Built as a self-contained `index.html` (no build step) and deployed on Vercel.

> **Live:** https://apac-regulations.vercel.app/

---

## What this repo is

A static, **architect-grade reference** intended for solutions and security architects sizing up regional constraints on data residency, workload placement, cyber resilience, and AI/model risk in APAC financial services.

- **Audience:** solutions architects, security architects, technology risk and outsourcing leads.
- **Form factor:** a single `index.html` — no framework, no build, no JavaScript dependencies in the runtime page.
- **Tone:** primary-source citations, dated claims, no legal advice.

## What this repo is *not*

- **Not legal advice.** Use as an architectural orientation; verify against the primary regulator before relying on it for compliance decisions.
- **Not exhaustive.** Focused on **financial services + cloud + cyber + AI risk**. Tax, employment, and consumer protection are out of scope unless they touch those domains.
- **Not a snapshot.** Claims are dated; expect drift between publication date and current state.

---

## Coverage

### Jurisdictions (10)

| Market | Primary regulator(s) |
|---|---|
| Australia | APRA, ASIC, OAIC |
| China | PBOC, CBIRC, CAC |
| Hong Kong | HKMA, SFC, PCPD |
| India | RBI, SEBI, MeitY |
| Indonesia | OJK, BI, KOMINFO |
| Japan | FSA, PPC |
| Malaysia | BNM, Securities Commission |
| Singapore | MAS, IMDA, PDPC |
| Taiwan | FSC, NCC |
| Thailand | BOT, SEC |

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

Each jurisdiction also includes an **Architectural Implications** summary. The brief opens with an **At a Glance** heat map across all 10 jurisdictions and a four-tier severity scale (strict / moderate / light / none).

---

## Repository layout

```
.
├── index.html        # Self-contained brief — open this to read the document
├── screenshot.mjs    # Playwright capture: mobile / tablet / desktop full-page PNGs
├── package.json      # Single dev dependency: playwright
├── VERIFICATION.md   # External assessment of accuracy as of 2026-04-17
├── LICENSE           # MIT
└── CLAUDE.md         # Project memory for Claude Code (git-ignored)
```

## View it locally

The page is fully self-contained — open it directly in a browser:

```bash
xdg-open index.html        # Linux
open index.html            # macOS
```

No server, install, or build step is required.

## Capture screenshots

The `screenshot.mjs` helper renders the page at three viewports and writes full-page PNGs to `./screenshots/`.

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
