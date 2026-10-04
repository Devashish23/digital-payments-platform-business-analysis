# Elicitation Notes (Simulated)

> Interviews below are simulated for the case study. Answers are assumptions I created to drive realistic requirements.

**Techniques used:** stakeholder interviews, document analysis (existing KYC SOP, support ticket categories), process observation (support desk), workshop with Ops and Compliance, user survey (assumed 200 respondents).

## Interview 1 – Head of Operations
| Question | Assumed answer | Resulting requirement |
|----------|----------------|-----------------------|
| What takes the most time daily? | Matching our ledger with the bank's settlement file in Excel | FR-14 automated reconciliation |
| How are failed transactions handled? | Agent raises a request to the bank; refund takes 2–3 days | FR-09 auto-reversal |
| What do customers contact you about most? | "Money debited, payment failed" (about 45% of tickets) | FR-09, FR-10, FR-11 |

## Interview 2 – Compliance Officer
| Question | Assumed answer | Resulting requirement |
|----------|----------------|-----------------------|
| What KYC tiers do we support? | Minimum KYC and full KYC with different wallet limits | FR-02, BR-01 to BR-03 |
| What must be auditable? | Every KYC decision, limit change and manual override | NFR-05 audit logging |
| Any data constraints? | Personal data stays in India, encrypted at rest | NFR-04 |

## Interview 3 – Customer Support Lead
| Question | Assumed answer | Resulting requirement |
|----------|----------------|-----------------------|
| Why do customers abandon onboarding? | They upload blurry documents and wait a day for manual review | FR-02 guided capture, instant verification |
| What would reduce tickets? | Visible transaction status and a self-service dispute option | FR-08, FR-10 |

## Customer survey summary (assumed)
- 62% abandoned onboarding when asked to wait more than 1 hour for verification.
- 71% want real-time status on a pending or failed payment.
- 54% worry about fraud when linking a bank account.

## Key findings
1. Slow KYC is the main driver of onboarding drop-off.
2. Failed-payment ambiguity drives support volume.
3. Manual reconciliation is a scalability and audit risk.
