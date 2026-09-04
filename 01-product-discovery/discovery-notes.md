# Product Discovery Notes

## Digital Account Funding API Integration

### Purpose

The purpose of product discovery is to validate the business need, identify customer and operational requirements, understand technical and regulatory constraints, and define the appropriate scope before development begins.

The initial business request was to allow customers opening a new bank account digitally to connect an external financial institution and fund their new account without leaving the onboarding experience.

Discovery identified several additional considerations that must be addressed before the solution can be considered development-ready.

---

## Discovery Stakeholders

The discovery process includes representatives from:

- Digital Banking
- Product
- Engineering
- UX
- Operations
- Customer Support
- Risk & Compliance
- Third-Party API Provider

---

## Key Discovery Areas

### 1. Customer & Eligibility

**Questions**

- Who are the target customers for this capability?
- Will the capability support new customers, existing customers, or both?
- What types of newly opened accounts are eligible for external funding?
- What types of external accounts can be connected?
- Can jointly owned external accounts be used?
- Are additional authorization or notification requirements needed for joint accounts?

**Discovery Findings**

The long-term capability may support both new and existing retail customers opening eligible checking or savings products.

For MVP, the experience will focus on customers opening a new checking account through the digital account opening channel.

Eligible external funding accounts include:

- Checking accounts
- Savings accounts

The following are out of scope for MVP:

- Credit cards
- Brokerage accounts
- Business accounts
- Other unsupported account types

A jointly owned external account may be used if the applicant successfully authenticates and account ownership verification requirements are satisfied.

Additional joint-account consent requirements require confirmation from Compliance.

---

### 2. Authentication & Security

**Questions**

- What authentication method is required to connect an external financial institution?
- Does the experience need to support multi-factor authentication?
- How are authentication challenges handled?
- What level of account ownership verification is required?

**Discovery Findings**

Authentication will be facilitated through the third-party financial technology provider.

The integration must support authentication challenges required by the external financial institution, including multi-factor authentication where applicable.

External account ownership must be successfully verified before the customer can initiate a funding transaction.

Customer banking credentials must not be exposed to bank employees or internal support teams.

---

### 3. Funding Rules

**Questions**

- What is the minimum opening deposit?
- What is the maximum digital funding amount?
- Do limits vary by product or customer type?
- Can multiple external accounts fund the opening deposit?

**Discovery Findings**

Minimum opening deposit:

**$25**

Maximum digital external funding transaction:

**$5,000**

Additional product-specific limits may apply.

MVP will allow one external funding account per application.

---

### 4. Transaction Lifecycle

**Questions**

- What payment rail will be used?
- Is funding immediate or delayed?
- When is the account considered successfully funded?
- What transaction statuses need to be communicated?
- What happens if a transaction is returned after submission?

**Discovery Findings**

External funding will be processed using ACH.

A successful submission does not indicate that funds have settled.

Transactions may progress through the following states:

`Submitted → Processing → Completed`

Exception states include:

`Failed`

`Returned`

The customer experience must clearly distinguish between a submitted funding request and a completed funding transaction.

---

### 5. Exception & Failure Scenarios

Discovery identified several failure scenarios that must be addressed during product design and backlog development.

These include:

- Unsupported financial institution
- Invalid credentials
- Failed multi-factor authentication
- Locked external account
- No eligible external accounts returned
- Failed ownership verification
- API timeout
- Third-party provider outage
- Duplicate funding submission
- Transaction rejection
- Insufficient funds
- ACH return

Engineering identified API latency and timeout handling as an important technical consideration.

The customer should not remain on an indefinite loading screen when an integration request fails or times out.

---

### 6. Operations & Customer Support

**Questions**

- Does Operations require visibility into funding transactions?
- Who manages failed or returned transactions?
- What information does Customer Support require?
- Are any transactions subject to manual review?

**Discovery Findings**

Operations requires visibility into:

- Funding transaction status
- Failed transactions
- Returned transactions

Customer Support must have sufficient transaction information to assist customers with funding issues without accessing external banking credentials.

Additional requirements for manual review will be evaluated with Operations and Risk.

---

### 7. Risk & Compliance

External account ownership must be verified before funding can proceed.

Funding activity must support appropriate auditability and transaction history.

Existing enterprise fraud monitoring capabilities should be leveraged rather than introducing a new fraud model specifically for this initiative.

Compliance must provide additional guidance regarding joint-account authorization and consent requirements.

---

### 8. Data & Analytics

The product should capture sufficient data to evaluate both technical performance and customer behavior.

Potential events and metrics include:

- Financial institution searches
- Institution selected
- Authentication attempts
- Successful account connections
- Failed account connections
- Eligible accounts returned
- Funding initiated
- Funding submitted
- Funding completed
- Funding failed
- ACH returns
- Customer abandonment
- Failure reason
- API response time

Final analytics requirements will be defined as part of detailed requirements development.

---

### 9. Artificial Intelligence

No current business requirement has been identified that requires artificial intelligence or machine learning.

Existing fraud and risk capabilities should be leveraged where appropriate.

AI functionality is therefore considered:

**Out of Scope for MVP**

AI use cases may be evaluated in the future if they provide measurable value to the customer or business.

---

## Business Objective

The primary business objective is to increase the percentage of digitally opened checking accounts that successfully receive an opening deposit while reducing customer abandonment caused by leaving the digital onboarding experience to fund the account through another channel.

---

## Open Questions / Dependencies

The following items require additional stakeholder resolution:

1. Joint-account consent and authorization requirements
2. Product-specific funding limits
3. Manual review requirements
4. ACH return handling procedures
5. Customer notification requirements
6. Final analytics and reporting requirements
7. Third-party API service-level expectations
8. Timeout and retry thresholds

These items will be tracked as product dependencies and addressed before the affected capabilities are considered development-ready.

---

## Discovery Outcome

Product discovery expanded the initial request beyond the basic ability to connect an external bank account.

The discovery process identified requirements and dependencies related to customer eligibility, authentication, account ownership, funding limits, ACH processing, API reliability, exception handling, operational support, compliance, and analytics.

These findings will be used to define the MVP scope and develop detailed business, functional, and technical integration requirements.
