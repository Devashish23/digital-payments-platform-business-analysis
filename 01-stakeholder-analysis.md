# Stakeholder Analysis

## Stakeholder register
| Stakeholder | Role | Interest / Need | Influence | Engagement |
|-------------|------|-----------------|-----------|------------|
| Chief Product Officer (sponsor) | Funds and approves scope | Growth, faster onboarding, roadmap delivery | High | Weekly steering update |
| Head of Operations | Owns support and reconciliation | Fewer tickets, automated reconciliation | High | Workshops, UAT sign-off |
| Compliance Officer | RBI/KYC and audit compliance | Regulatory adherence, audit trail | High | Review of all KYC/limit rules |
| CTO / Engineering Lead | Technical delivery | Feasible scope, clear NFRs | High | Refinement calls |
| Partner Bank Liaison | Settlement and UPI connectivity | Correct file formats, SLAs | Medium | Interface workshops |
| Customer Support Lead | Handles disputes | Self-service for refunds/disputes | Medium | Interviews, UAT |
| Fraud / Risk Analyst | Monitors suspicious activity | Rule configurability, alerts | Medium | Workshops |
| Retail Customer (end user) | Pays, transfers, tops up | Fast, safe, simple payments | Medium | Interviews, usability tests |
| Small Merchant (end user) | Accepts QR payments | Instant confirmation, settlement clarity | Medium | Interviews |
| QA Lead | Test planning | Testable, unambiguous requirements | Low | Review of acceptance criteria |

## Power / Interest grid
```mermaid
quadrantChart
    title Stakeholder Power vs Interest
    x-axis Low Interest --> High Interest
    y-axis Low Power --> High Power
    quadrant-1 Manage closely
    quadrant-2 Keep satisfied
    quadrant-3 Monitor
    quadrant-4 Keep informed
    CPO: [0.9, 0.9]
    Head of Ops: [0.85, 0.75]
    Compliance: [0.7, 0.85]
    CTO: [0.8, 0.8]
    Bank Liaison: [0.5, 0.55]
    Support Lead: [0.75, 0.4]
    Fraud Analyst: [0.65, 0.45]
    Customer: [0.8, 0.25]
    Merchant: [0.7, 0.2]
    QA Lead: [0.55, 0.2]
```
