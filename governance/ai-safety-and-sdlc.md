# 🤖 AI-Safety & Governance in the SDLC

In a modern engineering environment, AI-assisted development (GitHub Copilot, ChatGPT, etc.) is a force multiplier. However, without a governance framework, it introduces risks to code security, maintainability, and intellectual property. 

Our strategy focuses on **Augmented Intelligence** with **Human Accountability**.

## 1. AI-Assisted Development Policy
* **Human-in-the-Loop:** AI-generated code is never "trusted" by default. It must be reviewed, tested, and "owned" by a human engineer as if they wrote it themselves.
* **Sensitive Data:** No proprietary business logic or PII (Personally Identifiable Information) may be fed into public LLMs unless using an Enterprise-grade, private instance.
* **License Compliance:** AI-generated code must be scanned to ensure it does not violate open-source licensing constraints.

## 2. AI-Safety Tooling
We integrate automated safety gates to catch "hallucinated" vulnerabilities:
* **Snyk for AI:** We use Snyk to scan AI-suggested code for security flaws before it reaches the main branch. 
* **SonarQube Quality Gates:** Automated checks for "Maintainability" and "Reliability" ratings to ensure AI-generated code follows our architectural standards.
* **Static Analysis for Patterns:** AI often suggests "old" ways of doing things; our linting rules enforce modern, secure syntax.

## 3. The SDET's AI Playbook
The Quality Engineering team leverages AI to accelerate the "Paved Road":
* **Test Generation:** Using AI to generate boilerplate unit and integration tests, allowing engineers to focus on complex logic.
* **PR Summarization:** Using AI to generate high-level technical summaries of changes to help human reviewers focus on high-risk areas.
* **Synthetic Data Generation:** Leveraging LLMs to create realistic, non-sensitive data sets for high-traffic load testing.

## 4. Risks of "AI-Drift"
We actively monitor for:
* **Code Bloat:** AI makes it easy to write code, which can lead to unnecessarily large codebases. We prioritize **simplicity** over "clever" AI suggestions.
* **Dependency Risk:** AI may suggest outdated or unmaintained packages. Our dependency scanners (Snyk) act as the final gate.

---
*“AI is our engine, but Human Quality Engineering is our steering wheel.”*