# Digital Payments Platform – Business Analysis Case Study

> **Disclaimer:** Independent case study. *PayNest* is a fictional company. Interviews, baseline figures and targets are assumed for demonstration.

## 1. Scenario
**PayNest** is a fictional Indian fintech start-up (60 employees) offering a mobile wallet and UPI-based payments to individuals and small merchants. After 18 months in market it faces three problems:

1. **High onboarding drop-off.** KYC is largely manual and slow.
2. **Slow failed-transaction resolution.** Refunds for failed payments take days and generate heavy support volume.
3. **Limited ops visibility.** Reconciliation with the partner bank is done in spreadsheets.

Leadership has asked a Business Analyst to define requirements for a redesigned **Digital Payments Platform (v2)**.

## 2. My role
Business Analyst: elicitation, analysis, documentation, prioritisation, and traceability from objectives to test cases.

## 3. Business objectives (SMART, assumed baselines)
| ID | Objective | Baseline (assumed) | Target |
|----|-----------|--------------------|--------|
| BO-1 | Reduce onboarding drop-off (install → verified wallet) | 38% completion | 60% completion within 6 months of release |
| BO-2 | Cut average failed-transaction refund time | 3 days | under 4 hours (auto-reversal) |
| BO-3 | Reduce payment-related support tickets | 1,200 / month | 700 / month |
| BO-4 | Automate daily reconciliation | Manual, ~6 person-hours/day | Automated, under 1 hour/day exception review |

## 4. Scope
**In scope:** onboarding and KYC, wallet top-up, P2P transfer, merchant QR payment, bill payments, history and receipts, failed-transaction handling, disputes, notifications, fraud rules, admin console, reconciliation.
**Out of scope:** credit/lending products, international remittance, merchant POS hardware, loyalty programme.

## 5. Deliverables
| File | Description |
|------|-------------|
| [01-stakeholder-analysis.md](01-stakeholder-analysis.md) | Stakeholder register and power/interest grid |
| [02-elicitation-notes.md](02-elicitation-notes.md) | Simulated interviews, questions and findings |
| [03-brd.md](03-brd.md) | Business Requirements Document |
| [04-user-stories.md](04-user-stories.md) | Prioritised user stories with acceptance criteria |
| [05-process-flows.md](05-process-flows.md) | As-is / to-be flows and payment sequence |
| [06-traceability-and-risks.md](06-traceability-and-risks.md) | RTM, NFRs, risk register |
