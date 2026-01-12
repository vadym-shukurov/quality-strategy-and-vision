# 📊 Quality Intelligence Dashboard

We measure quality through a lens of **Business Impact** and **Engineering Velocity**. These are the North Star metrics for the Quality Department.

## 1. Customer-Centric Metrics
* **Defect Escape Rate (DER):** Target < 5%. (Bugs found by users / Total bugs found). 
* **Customer Reported Incidents:** Tracking the correlation between releases and support ticket spikes.

## 2. Engineering Health Metrics
* **Mean Time to Detection (MTTD):** How fast our **Observability** triggers an alert vs. a human finding it.
* **Flaky Test Index:** We treat flaky tests as "Technical Debt." Any test with >1% flake rate is automatically quarantined and assigned for repair.
* **Change Failure Rate (CFR):** The % of deployments that result in a rollback or hotfix.

## 3. The "Cost of Quality" (CoQ)
We track the balance between:
* **Prevention Costs:** Time spent on Design Reviews, Pair Programming, and Automation.
* **Failure Costs:** Time spent on Hotfixes, Incident Management, and Customer Churn.

---
*“In God we trust; all others must bring data.”*