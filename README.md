# AI Governance Framework for a High-Risk Clinical Decision Support System

**EU AI Act · EU MDR · GDPR**

A practical governance framework for a clinical AI triage system, mapping regulatory obligations from three overlapping EU frameworks into a single, integrated compliance architecture.

---

## What This Is

This is a self-initiated project I built as an MBA student to understand what responsible AI deployment in healthcare actually requires — not at a theoretical level, but operationally.

The system in question is a **Clinical Triage Decision Support System (AI-CTDSS)**: an AI that analyses patient vitals and symptoms at emergency department intake and recommends a triage priority score to the attending nurse.

The framework works through:
- How this system is classified under EU law (and why it is simultaneously regulated by *three* different regulations)
- What each of those regulations actually requires — and how those requirements interact with each other
- How specific design decisions (like how the UI presents the AI's recommendation) can satisfy multiple legal obligations at once
- What happens when something goes wrong — incident classification, reporting timelines, and who is accountable

---

## Regulatory Scope

| Regulation | Classification | Key Trigger |
|---|---|---|
| EU AI Act (2024/1689) | High-Risk AI System | Art. 6(1) — safety component in an MDR-regulated medical device |
| EU MDR (2017/745) | Class IIa Medical Device | Annex VIII Rule 11 — software influencing decisions with diagnostic intent |
| GDPR (2016/679) | Special Category Data Processing | Art. 9 — health data; Art. 22 — automated decision-making |

All three classifications apply simultaneously. This framework resolves the obligations from all three in one integrated architecture rather than treating them in isolation.

---

## Framework Structure

| Section | Title |
|---|---|
| 0 | Executive Summary |
| 1 | System Definition and Scope |
| 2 | Risk Classification Analysis |
| 3 | GDPR Compliance Architecture |
| 4 | Human Oversight Design |
| 5 | Technical Documentation Requirements |
| 6 | Audit Trail and Logging |
| 7 | Transparency and User Information |
| 8 | Incident Response and Post-Market Monitoring |
| 9 | Governance Ownership Map |
| 10 | Limitations and Implementation Roadmap |

---

## Three Things Worth Reading First

If you don't want to read all 50+ pages, these are the sections with the most interesting design decisions:

### Section 4 — Human Oversight
The system uses a **"Delayed Reveal"** mechanism — the nurse must enter their own initial clinical impression *before* the AI's recommendation is displayed. This single design decision simultaneously satisfies:
- **GDPR Article 22** — the triage decision is never "based solely on automated processing"
- **EU AI Act Article 14** — effective human oversight is built into the workflow, not bolted on

Two legal requirements, one design solution. It also protects against automation bias — the documented tendency for clinicians to simply agree with whatever the algorithm outputs.

### Section 3.7 — Algorithmic Fairness
SpO2 sensors (the small finger clip measuring blood oxygen) are clinically documented to over-read in patients with darker skin pigmentation — producing falsely elevated readings and masking hypoxia. The framework treats this as a **regulatory compliance risk** under EU AI Act Article 10 (data governance), not just an ethical concern.

A second bias risk: atypical MI presentations. Women and elderly patients frequently present with heart attacks using non-classic symptoms (fatigue, nausea, indigestion rather than chest pain). An AI trained primarily on male demographic data will systematically under-triage these patients.

### Section 8 — Incident Response
Maps the difference between a "Serious Incident" under MDR Article 87 and a "Serious Incident involving a High-Risk AI System" under EU AI Act Article 73, and builds a unified incident classification matrix with the correct reporting timeline for each scenario (15-day maximum, 10-day escalation, and a strict 72-hour internal operational SLA).

---

## Compliance Timeline

Full EU AI Act enforcement for AI systems classified as medical devices: **August 2028 (per Digital Omnibus Reg. 2026/1744).**

---

## Limitations

This is a speculative project built by an MBA student, not a practising regulatory lawyer or clinical engineer. It is based on primary sources i.e. the regulations themselves, EU Commission guidance, and Notified Body standards — but should not be treated as legal advice or used as an actual regulatory submission.

---

## About Me

MBA student interested in AI governance, healthcare regulation, and the intersection of technology and policy.

Currently exploring roles in HealthTech AI governance, regulatory strategy, and GRC.

[LinkedIn](www.linkedin.com/in/vasu-sharma0011)
