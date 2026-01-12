# 🔗 Third-Party Vendor Reliability Strategy

High-traffic systems are often dependent on external APIs. Our Quality Strategy extends beyond our code to the entire **Supply Chain**.

## 1. Defensive Integration (The "Trust No One" Policy)
* **Contract Testing (Pact):** We use Consumer-Driven Contracts to ensure that if a vendor changes their API response format, our builds fail *before* deployment.
* **Service Virtualization (Mocking):** We simulate vendor failures (500 errors, timeouts, 429 rate limiting) in Staging to ensure our system fails gracefully.

## 2. Failure Patterns for External Dependencies
* **Circuit Breakers:** If a vendor (e.g., a Payment Gateway) slows down, we trip the circuit to prevent our own threads from hanging.
* **Fallbacks:** If a "Premium" non-essential service fails (e.g., an AI Recommendation engine), the system must default to a "Basic" static experience.

## 3. Vendor Quality Audits
We treat major vendors as part of our infrastructure:
* **SLA Monitoring:** We track vendor uptime/latency independently of their status pages.
* **Disaster Recovery (DR):** For critical path vendors, we maintain a "Warm Standby" strategy or a clear manual failover process.