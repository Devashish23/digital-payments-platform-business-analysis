# Requirements Traceability Matrix and Risks

## Requirements Traceability Matrix (RTM)
| Business objective | Requirement | User story | Test scenario |
|--------------------|-------------|------------|---------------|
| BO-1 Onboarding completion | FR-01, FR-02 | US-01, US-02, US-03 | TC-01 OTP success/lock, TC-02 blurry image retake, TC-03 KYC pass activates wallet |
| BO-1 | FR-03, FR-04 | US-04, US-05 | TC-04 link account, TC-05 top-up within and over limit |
| BO-2 Refund time | FR-08, FR-09 | US-09, US-10 | TC-06 status display, TC-07 auto-reversal at 30 min |
| BO-3 Support tickets | FR-10, FR-11 | US-11 | TC-08 dispute creation and SLA, TC-09 notifications |
| BO-4 Reconciliation | FR-14 | US-13 | TC-10 match and exception report |
| Compliance and risk | FR-12, FR-13 | US-12, US-14 | TC-11 velocity limit block, TC-12 KYC override audit log |
| Core payments | FR-05, FR-06, FR-07 | US-06, US-07, US-08 | TC-13 P2P, TC-14 QR in under 3s, TC-15 bill pay |

## Risk register
| ID | Risk | Likelihood | Impact | Mitigation |
|----|------|------------|--------|------------|
| R-1 | Partner bank APIs delayed | Medium | High | Agree API milestones early; build against a mock service |
| R-2 | KYC vendor accuracy lower than expected | Medium | High | Pilot with sample data; keep manual review fallback |
| R-3 | Regulatory limits change mid-project | Medium | Medium | Make limits configuration-driven, not hard-coded |
| R-4 | Fraud spike after faster onboarding | Medium | High | Velocity limits, device binding, new-payee cooling-off |
| R-5 | Scope creep (lending, rewards) | High | Medium | Change control through the sponsor; explicit out-of-scope list |
| R-6 | Low user trust in linking bank accounts | Low | Medium | Masked display, clear consent messages, security messaging |

## Open questions
1. Exact wallet and load limits per KYC tier (Compliance to confirm).
2. Which KYC vendor and verification methods are approved?
3. Does the bank support real-time status enquiry for all payment types?
