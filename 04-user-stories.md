# User Stories and Acceptance Criteria

Priority uses MoSCoW. Format: *As a / I want / So that*, with Given/When/Then criteria.

## Epic A – Onboarding and KYC

### US-01 Register with OTP (FR-01) – Must
**As a** new user **I want** to register with my mobile number and OTP **so that** I can start quickly.
- **Given** a valid mobile number not already registered, **when** I enter the correct OTP within 5 minutes, **then** my account is created.
- **Given** a wrong OTP is entered 3 times, **when** I try again, **then** the number is locked for 15 minutes.
- **Given** the number already has an active wallet, **when** I register, **then** I am directed to log in instead (BR-03).

### US-02 Instant minimum KYC (FR-02) – Must
**As a** new user **I want** guided document capture with instant verification **so that** I don't wait a day to start paying.
- **Given** I upload an ID, **when** the image is blurry or cropped, **then** the app asks me to retake it and explains why.
- **Given** the document passes verification, **when** processing completes, **then** my wallet is activated with minimum-KYC limits within 2 minutes.
- **Given** verification fails, **when** the result returns, **then** I see the reason and an option to retry or request assisted review.

### US-03 Upgrade to full KYC (FR-02) – Should
**As a** verified user **I want** to upgrade via video KYC **so that** I get higher limits and bank withdrawals.
- **Given** I have minimum KYC, **when** I complete video KYC successfully, **then** limits increase and withdrawal is enabled (BR-02).

## Epic B – Payments

### US-04 Link bank account (FR-03) – Must
**As a** user **I want** to link my bank account **so that** I can top up and withdraw.
- **Given** valid bank details, **when** I confirm with an OTP, **then** the account is linked and shown masked (last 4 digits).

### US-05 Top up wallet (FR-04) – Must
**As a** user **I want** to add money from my bank **so that** I can pay from the wallet.
- **Given** a linked account, **when** the top-up succeeds, **then** my balance updates and I receive a notification.
- **Given** the top-up would exceed my KYC limit, **when** I submit, **then** it is blocked with the reason and an upgrade prompt (BR-01).

### US-06 Send money P2P (FR-05) – Must
**As a** user **I want** to send money by mobile number, UPI ID or QR **so that** I can split bills or repay friends.
- **Given** sufficient balance and a valid payee, **when** I authenticate, **then** the payment completes and both parties are notified.
- **Given** a first-time payee, **when** I send above the cooling-off limit, **then** the payment is held or limited (FR-12).

### US-07 Pay a merchant by QR (FR-06) – Must
**As a** customer **I want** to scan a merchant QR **so that** I pay in seconds.
- **Given** a valid QR, **when** I confirm the amount, **then** I see success within 3 seconds (NFR-01) and the merchant sees instant confirmation.

### US-08 Pay a bill (FR-07) – Should
**As a** user **I want** to pay utility bills in-app **so that** I avoid separate apps.
- **Given** a valid consumer number, **when** the bill is fetched, **then** I can pay and receive a receipt.

## Epic C – Transparency and exceptions

### US-09 See transaction status (FR-08) – Must
**As a** user **I want** real-time status on every payment **so that** I know whether money left my account.
- **Given** a payment is in progress, **when** I open history, **then** it shows Pending, Success, Failed or Reversed with a timestamp.
- **Given** a completed payment, **when** I tap Download, **then** I get a PDF receipt.

### US-10 Auto-reversal of failed debits (FR-09) – Must
**As a** user **I want** failed or unconfirmed debits reversed automatically **so that** I don't need to chase support.
- **Given** a debit is not confirmed within 30 minutes, **when** the timer expires, **then** the system reverses the amount and notifies me (BR-04).
- **Given** a reversal is processed, **when** I view history, **then** the original transaction shows "Reversed" linked to the refund entry.

### US-11 Raise a dispute (FR-10) – Should
**As a** user **I want** to raise a dispute in-app **so that** problems are tracked and resolved.
- **Given** a transaction in the last 90 days, **when** I raise a dispute with a reason, **then** a ticket is created with an SLA timer and I can track its status.

## Epic D – Operations

### US-12 KYC review queue (FR-13) – Must
**As a** compliance analyst **I want** a queue of KYC cases needing manual review **so that** edge cases are handled with a full audit trail.
- **Given** a case flagged for review, **when** I approve or reject with a reason, **then** the decision, user and timestamp are logged (BR-06).

### US-13 Automated reconciliation (FR-14) – Must
**As an** operations executive **I want** the system to match our ledger to the bank file **so that** I only review exceptions.
- **Given** the bank's daily file is received, **when** reconciliation runs, **then** matched items are auto-closed and mismatches appear in an exception list with amount, reference and age.

### US-14 Fraud rule configuration (FR-12) – Must
**As a** fraud analyst **I want** to configure velocity limits **so that** I can respond to new fraud patterns without a release.
- **Given** I change a limit with a valid reason, **when** I save, **then** it applies to new transactions and the change is audit-logged.
