# Business Requirements

## Digital Account Funding API Integration

### Purpose

This document defines the high-level business requirements for introducing external account funding into the digital account opening experience.

These requirements describe the business outcomes and capabilities the solution must support without prescribing a specific technical implementation.

---

## Business Objectives

The solution should:

1. Increase the percentage of digitally opened checking accounts that receive an opening deposit.
2. Reduce customer abandonment during digital account opening.
3. Eliminate unnecessary transitions outside of the digital onboarding experience.
4. Provide customers with a secure and intuitive method for funding newly opened accounts.
5. Provide Operations and Customer Support with sufficient visibility to support funding transactions.
6. Maintain appropriate security, risk, compliance, and audit controls.
7. Provide measurable data to evaluate product adoption, performance, and customer outcomes.

---

## Business Requirements

### BR-001 — External Account Funding

The bank shall provide eligible customers with the ability to fund a newly opened checking account using an eligible account held at an external financial institution.

### BR-002 — Integrated Customer Experience

External funding shall be incorporated into the digital account opening journey without requiring the customer to independently navigate to another banking channel.

### BR-003 — Eligible Funding Accounts

The solution shall support eligible consumer checking and savings accounts as external funding sources.

### BR-004 — Customer Authentication

Customers shall securely authenticate with their external financial institution before external account information is retrieved.

### BR-005 — Account Ownership

The bank shall verify that applicable account ownership requirements have been satisfied before allowing an external account to be used for funding.

### BR-006 — Funding Limits

The solution shall enforce established minimum and maximum digital funding limits.

For MVP:

- Minimum funding amount: $25
- Maximum funding amount: $5,000

### BR-007 — Transaction Processing

Approved external funding requests shall be submitted through the bank's designated ACH processing workflow.

### BR-008 — Transaction Transparency

Customers shall receive clear information regarding the status of their funding request and shall not be led to believe that submitted funds have settled before settlement occurs.

### BR-009 — Exception Management

The solution shall appropriately manage authentication failures, integration failures, transaction failures, and returned ACH transactions.

### BR-010 — Operational Support

Authorized internal teams shall have sufficient transaction visibility to investigate and support customer funding issues.

### BR-011 — Security & Privacy

External account funding shall comply with applicable enterprise security, privacy, risk, and compliance requirements.

### BR-012 — Auditability

Funding activity and relevant system events shall be recorded at a level sufficient to support operational investigation, compliance, and audit requirements.

### BR-013 — Measurement

The solution shall capture sufficient analytics to measure customer adoption, conversion, abandonment, transaction success, integration performance, and failure trends.

### BR-014 — Scalability

The solution should support future expansion to additional deposit products and funding experiences without requiring complete redesign of the integration.

---

## Business Constraints

The MVP is subject to the following constraints:

- A third-party provider will facilitate external financial institution connectivity.
- External funding will use ACH.
- Existing enterprise fraud capabilities will be leveraged.
- MVP supports one external funding source per application.
- MVP is initially limited to digital checking account opening.
- Credit cards, brokerage accounts, and business accounts are excluded as external funding sources.

---

## Assumptions

The requirements currently assume:

- The selected third-party provider supports required institution search, authentication, account retrieval, and verification capabilities.
- Existing ACH infrastructure can receive approved funding requests from the digital account opening platform.
- Existing identity, fraud, and account-opening controls remain in place.
- Appropriate API documentation and test environments will be available to Engineering.
- Required Compliance, Risk, Security, and Architecture stakeholders will participate in detailed solution review.

Any invalidated assumption may require changes to scope, requirements, or implementation approach.
