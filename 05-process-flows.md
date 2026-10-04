# Process Flows

## 1. As-is: onboarding and KYC (manual)
```mermaid
flowchart TD
    A[User installs app] --> B[Registers with mobile and OTP]
    B --> C[Uploads ID photos]
    C --> D[Request goes to ops queue]
    D --> E{Agent reviews within 24h?}
    E -- Image unclear --> F[Agent emails user to re-upload]
    F --> C
    E -- Approved --> G[Wallet activated]
    E -- Rejected --> H[User notified, drops off]
    F -. high drop-off .-> H
```
**Pain points:** up to 24-hour wait, unclear rejection reasons, repeated uploads, no real-time feedback.

## 2. To-be: onboarding and KYC (automated)
```mermaid
flowchart TD
    A[User installs app] --> B[Registers with mobile and OTP]
    B --> C[Guided document capture with quality check]
    C --> D[Automated verification via KYC vendor]
    D --> E{Result}
    E -- Pass --> F[Wallet activated with min-KYC limits]
    E -- Fail, retryable --> G[Show reason and retry]
    G --> C
    E -- Needs manual check --> H[Compliance review queue]
    H --> I{Decision}
    I -- Approve --> F
    I -- Reject --> J[Notify with reason]
    F --> K[Optional upgrade to full KYC via video]
```

## 3. To-be: P2P payment sequence
```mermaid
sequenceDiagram
    actor U as Sender
    participant App as PayNest App
    participant P as Payment Service
    participant F as Fraud Engine
    participant B as Partner Bank / UPI
    participant N as Notification Service
    U->>App: Enter payee and amount, authenticate
    App->>P: Create payment request
    P->>F: Check limits and risk rules
    F-->>P: Allow / Hold / Block
    alt Allowed
        P->>B: Debit and credit request
        B-->>P: Success / Failure / No response
        P->>N: Trigger notifications
        N-->>U: Payment status
    else Hold or Block
        P-->>App: Show reason
    end
```

## 4. To-be: failed-transaction auto-reversal
```mermaid
flowchart TD
    A[Debit initiated] --> B{Bank confirms within 30 min?}
    B -- Success --> C[Mark Success, notify]
    B -- Failure --> D[Auto-reverse debit]
    B -- No response --> E[Status enquiry to bank]
    E --> F{Status}
    F -- Success --> C
    F -- Failed or unknown after 30 min --> D
    D --> G[Mark Reversed, link refund entry]
    G --> H[Notify user]
    G --> I[Flag in reconciliation if bank mismatch]
```
