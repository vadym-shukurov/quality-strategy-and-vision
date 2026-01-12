# 🛠️ Engineering & Automation Standards

This document defines the high-level technical standards for all automation and testing activities within the organization.

## 1. The "Testing Honeycomb" Approach
For our microservice architecture, we prioritize **Integration Tests** over brittle E2E tests.
* **Unit Tests:** Focus on complex logic/algorithms.
* **Integration Tests:** Focus on service boundaries and data contracts.
* **E2E Tests:** Reserved only for "Critical Path" user journeys (e.g., Signup to Checkout).

## 2. Automation Best Practices
To ensure our CI/CD remains fast and reliable, we follow these principles:
* **Atomic & Independent:** Tests must be able to run in parallel. No test should depend on the state of a previous test.
* **Headless First:** All web automation must run headless in CI to optimize resource usage and speed.
* **The "3-Strike" Flaky Rule:** Any test that fails intermittently 3 times is automatically quarantined. We do not tolerate "flaky" greens.
* **Data over Mocks:** We prefer using "Data Factories" to seed real database state over mocking internal service logic, ensuring higher fidelity.

## 3. The "Clean Test" Code Standards
Test code is **Production Code**. It must be maintained with the same rigor:
* **Page Object Model (POM) / App Actions:** Mandatory for UI automation to separate logic from selectors.
* **No Hard Wait/Sleep:** Use dynamic waits (Smart Waits) only. Hard sleeps are a "Blocker" in Code Reviews.
* **Self-Healing Selectors:** We prioritize resilient attributes (e.g., `data-testid`) over brittle CSS paths or XPaths.

## 4. API-First Verification
Before testing through the UI, verify through the API.
* 90% of business logic should be verified at the API/Service level.
* Use **Contract Testing (Pact)** to catch breaking changes before the code is even merged.

---
*“Speed is a feature, and reliability is a requirement. Our automation must provide both.”*