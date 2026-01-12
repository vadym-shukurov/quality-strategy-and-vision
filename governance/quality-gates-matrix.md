# 🚦 Quality Gates & Governance Matrix

This document defines the mandatory "Quality Gates" that every feature must pass before progressing through our SDLC. These gates are designed to ensure **Customer Success**, **System Resilience**, and **Security**.

---

## 🏛️ The Governance Framework

We move away from "End-of-Cycle" testing. Instead, we treat quality as a series of automated and human-led checkpoints integrated into the development flow.

| Stage | Quality Gate | Primary Ownership | Tools / Evidence | Success Criteria (Definition of Done) |
| :--- | :--- | :--- | :--- | :--- |
| **01 Discovery** | **Outcome Alignment** | PM + Lead Engineer | Success Metric Doc | Feature linked to a specific Customer Satisfaction KPI. |
| **02 Design** | **Architecture Review** | System Architect | RFC / Design Doc | "Failure Mode" analysis completed (Retries, Circuit Breakers defined). |
| **03 Development** | **Static Analysis** | Developer | SonarQube | 0 New Blocker issues; Maintainability Rating: **A**. |
| **03 Development** | **Security Scan** | Developer | Snyk / AI Audit | No High or Critical vulnerabilities in code or dependencies. |
| **04 Integration** | **Contract Testing** | SDET / Developer | Pact.io | 100% compatibility between Consumer and Provider services. |
| **05 Verification** | **Functional CI** | Team (Automated) | Playwright / Pytest | 100% pass rate on critical paths (P0/P1 scenarios). |
| **05 Verification** | **Resilience Gate** | SDET / SRE | k6 / JMeter | Latency < P99 200ms at 2x expected peak traffic. |
| **06 Release** | **Human Intuition** | Whole Team | Exploratory Session | No "Critical" usability flaws found during field testing. |
| **07 Production** | **Observability** | Team / SRE | Datadog / New Relic | Service Level Objectives (SLOs) are defined and dashboarded. |

---

## 🛑 The "Hard Stop" Policy
To maintain high-traffic reliability, we enforce a **Hard Stop** on deployments if:
1.  **Security Vulnerabilities:** Any 'Critical' or 'High' Snyk finding is discovered.
2.  **Performance Regression:** P99 latency increases by >10% during Load Testing.
3.  **Code Coverage:** Total test coverage for *new code* drops below 85%.
4.  **SLO Violation:** The service's Error Budget is exhausted.

## 🤝 The Role of the SDET in Governance
In this model, the SDET does not "perform" all these gates. Instead, they:
* **Architect** the automation that powers the gates.
* **Mentor** the team on how to interpret and fix gate failures.
* **Audit** the process to ensure the gates remain effective and don't cause unnecessary friction.

---
*“Quality is an accelerator. When the gates are automated and clear, we can ship faster with higher confidence.”*