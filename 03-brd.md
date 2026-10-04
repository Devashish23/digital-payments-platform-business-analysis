# Business Requirements Document (BRD) – PayNest Digital Payments Platform v2

| Field | Value |
|-------|-------|
| Version | 1.0 (Draft for review) |
| Author | Devashish Kale, Business Analyst |
| Sponsor | Chief Product Officer (fictional) |
| Status | Independent case study |

## 1. Purpose
Define the business and functional requirements for PayNest Platform v2 so engineering can estimate, build and test.

## 2. Problem statement
Manual KYC, opaque failed-transaction handling and spreadsheet reconciliation limit PayNest's growth, increase cost-to-serve and create audit risk. See objectives BO-1 to BO-4 in the [README](README.md).

## 3. Scope
See README section 4.

## 4. Business rules
| ID | Rule |
|----|------|
| BR-01 | Users with minimum KYC have a lower wallet balance and monthly load cap than full-KYC users (limits to be confirmed by Compliance against current RBI PPI guidelines). |
| BR-02 | Full KYC is required before wallet-to-bank withdrawal. |
| BR-03 | A user may hold only one active wallet per verified mobile number. |
| BR-04 | A debit that is not confirmed as successful by the bank within 30 minutes triggers automatic reversal. |
| BR-05 | Transactions exceeding per-transaction or daily velocity limits are blocked or held for review. |
| BR-06 | Every KYC decision and manual override must be logged with user, timestamp and reason. |

## 5. Functional requirements
| ID | Requirement | Priority |
|----|-------------|----------|
| FR-01 | Register using mobile number and OTP; enforce one wallet per number (BR-03). | Must |
| FR-02 | Complete minimum KYC in-app with guided document capture and automated verification; offer full KYC via video or assisted verification. | Must |
| FR-03 | Link a bank account or UPI ID with confirmation and a masked display. | Must |
| FR-04 | Top up the wallet from a linked bank account or UPI. | Must |
| FR-05 | Transfer money to another user by mobile number, UPI ID or QR (P2P). | Must |
| FR-06 | Pay a merchant by scanning a QR code with instant confirmation. | Must |
| FR-07 | Pay utility bills (electricity, mobile, DTH) from the wallet. | Should |
| FR-08 | View transaction history with real-time status (Pending, Success, Failed, Reversed) and downloadable receipts. | Must |
| FR-09 | Automatically reverse failed or unconfirmed debits per BR-04 and notify the user. | Must |
| FR-10 | Raise and track disputes in-app; route to the support queue with SLA timers. | Should |
| FR-11 | Send SMS and push notifications for key events (OTP, payment, failure, reversal, KYC outcome). | Must |
| FR-12 | Apply configurable fraud rules (velocity limits, device binding, new-payee cooling-off). | Must |
| FR-13 | Provide an admin console with KYC review queue, dispute queue and manual override with audit logging. | Must |
| FR-14 | Auto-reconcile the internal ledger against the partner bank's daily settlement file and flag mismatches. | Must |
| FR-15 | Provide an operations dashboard (volumes, success rate, refund time, tickets). | Could |

## 6. Non-functional requirements
| ID | Category | Requirement |
|----|----------|-------------|
| NFR-01 | Performance | 95% of payment requests complete in under 3 seconds (excluding bank-side delay). |
| NFR-02 | Availability | 99.9% monthly uptime for payment APIs. |
| NFR-03 | Security | Transactions authenticated by UPI PIN or app PIN/biometric; TLS 1.2+ in transit. |
| NFR-04 | Data protection | Personal and KYC data encrypted at rest and stored in India. |
| NFR-05 | Auditability | Immutable audit trail for KYC decisions, limit changes and overrides; retained per regulation. |
| NFR-06 | Usability | New user completes onboarding in under 5 minutes; supports English, Hindi and Marathi. |
| NFR-07 | Scalability | Handle 5x current peak transactions per second without redesign. |
| NFR-08 | Compliance | Align with RBI PPI guidelines, NPCI UPI rules and PCI DSS where card data is touched. |

## 7. Assumptions, constraints, dependencies
- **Assumptions:** the partner bank exposes APIs for status enquiry and reversal; a third-party KYC verification vendor is available.
- **Constraints:** 6-month delivery window; fixed budget; regulatory limits are set externally.
- **Dependencies:** partner bank API readiness, KYC vendor contract, Compliance sign-off on limits.

## 8. Success metrics
BO-1 to BO-4 tracked monthly via the FR-15 dashboard.

## 9. Approval
| Name | Role | Status |
|------|------|--------|
| (fictional) CPO | Sponsor | Pending |
| (fictional) Compliance Officer | Compliance | Pending |
| (fictional) CTO | Technology | Pending |
