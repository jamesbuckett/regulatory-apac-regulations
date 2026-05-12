# APAC FinTech Technology Architecture Design Constraints — Research Brief

![Description](https://img.shields.io/badge/Research-FinTech%20Architecture%20Constraints%20across%2010%20APAC%20markets-2ea44f)

You are a **senior Front-End Developer and FinTech Solutions Architect** with deep expertise in APAC financial regulation, cloud architecture, and web standards.

## Your Task

Research and present the **Technology Architecture Design Constraints** imposed by financial industry regulations and technology standards for the following 10 APAC countries/territories:

> **Indonesia, India, Taiwan, Japan, China, Hong Kong, Singapore, Malaysia, Australia, Thailand**

For each country, cover **ALL** of the dimensions below. Where a country has no explicit mandate for a dimension, state "No explicit mandate" and note any de facto industry practice or supervisory expectation.

---

## Research Dimensions

### **1. Regulatory Bodies**
- Name the primary financial regulators (e.g. MAS, APRA, RBI, OJK, FSA, CBIRC/PBOC)
- Include official website links
- Note the specific regulator responsible for technology risk / cyber supervision if distinct from the prudential regulator

### **2. Data Localization Mandates** *(where data must physically reside)*
- Must customer data, transaction data, or payment data be stored **on servers physically located within the country**?
- Are there asymmetric rules (e.g. "a copy must remain onshore" vs. "data may only exist onshore")?
- Cross-border transfer restrictions, approval regimes, or whitelisted jurisdictions
- Distinguish between **strict localization** (no data may leave) vs. **mirroring requirements** (a local copy must exist) vs. **conditional transfer** (transfer allowed with consent/approval)

### **3. System & Process Localization Mandates** *(where compute, processing, and operations must occur)*
- Must **processing, clearing, or settlement systems** physically operate within the country?
- Must **specific business processes** (e.g. payment authorization, fraud screening, customer onboarding) execute onshore?
- Are **support, administration, or DevOps functions** required to be performed by onshore personnel or from onshore locations?
- Disaster recovery (DR) site location mandates — must DR also be onshore, or can it be regional?

### **4. Legal Entity Segregation Requirements**
- Must the local business operate as a **separately incorporated legal entity** (subsidiary vs. branch)?
- Restrictions on **shared infrastructure or shared data planes** between the local entity and overseas affiliates
- Are **intra-group data flows** treated as cross-border transfers requiring notification, consent, or approval?
- **Local governance** expectations — resident directors, locally appointed CISO / CRO, fit-and-proper requirements
- **Books and records** that must be maintained at the local entity level (vs. accessible from group)

### **5. Cloud Adoption Mandates**
- Is **public cloud** permitted for in-scope financial workloads? Are specific data classes (e.g. customer PII, transaction data, cryptographic key material) excluded?
- **Notification, registration, or prior-approval** thresholds for material outsourcing to cloud providers
- **Outsourcing risk management** rules (e.g. MAS Outsourcing Guidelines, APRA CPS 230, HKMA SA-2, RBI Outsourcing of IT Services Directions, OJK 11/POJK.03/2022)
- **Exit, audit, and right-to-inspect** provisions regulators expect in cloud contracts
- Restrictions on **multi-tenant architectures**, shared control planes, or hyperscaler regions outside the country
- **Concentration risk** expectations where a single CSP supports systemically important workloads

### **6. Cyber & Operational Resilience**
- **Incident reporting timelines** (e.g. MAS — 1 hour notification for material incidents; APRA CPS 234 — 72 hours; RBI — 6 hours; HKMA — "as soon as possible")
- **Board and senior management accountability** for cyber and operational resilience
- **Third-party and supply-chain risk** obligations, including fourth-party visibility
- **Operational resilience** standards (e.g. APRA CPS 230, HKMA OR-2, MAS BCM Guidelines, FSA's "operational resilience" supervisory focus)
- **Threat-led penetration testing** or red-team mandates (e.g. HKMA iCAST, MAS AASE, BNM TLPT)
- **Critical / important business service** definitions, impact tolerances, and RTO/RPO expectations

### **7. Identity, KYC and AML Constraints**
- **Customer due diligence (CDD)** standards — risk-based vs. prescriptive
- Acceptable **identity evidence** and reliance on **government / national identity systems** (e.g. Aadhaar/DigiLocker, Singpass/MyInfo, MyKad, e-KTP, MyNumber, Taiwan Citizen Digital Certificate)
- **Remote / digital onboarding** rules — video-KYC, liveness, biometric capture, and any in-person fallback requirement
- **Biometric data** handling and storage restrictions
- **Sanctions screening, transaction monitoring, and STR/SAR reporting** obligations and timelines
- **Beneficial ownership** and PEP screening expectations
- Cross-border restrictions on **transferring identity or KYC data** to group entities or shared utilities

### **8. AI / Model Risk Governance**
- **AI-specific frameworks** where they exist (e.g. MAS FEAT and Veritas, HKMA Generative AI guidance, PBOC/CAC Interim Measures for Generative AI Services, MeitY AI advisories, Japan FSA discussion papers)
- **Model risk management** expectations for credit, fraud, AML, pricing, and capital models
- **Explainability, fairness, and bias** obligations — including auditability of automated decisions
- **Human-in-the-loop** requirements for consequential or adverse customer decisions
- **Training data provenance, lineage, and localisation** considerations
- Restrictions on **cross-border model training or inference** using regulated data
- **Generative AI / LLM-specific** constraints, including content labelling, hallucination risk controls, and prompt/output logging

---

> **Note:** This brief is a research scope, not legal advice. All findings must be sourced to primary regulator material and dated — see `CLAUDE.md` for sourcing rules.
