# MVP Scope & Prioritization

## Digital Account Funding API Integration

### Objective

The MVP will enable customers opening a new checking account through the digital account opening experience to securely connect an eligible external financial institution and initiate an opening deposit without leaving the onboarding journey.

The MVP is intentionally focused on the minimum set of capabilities required to deliver a secure, reliable, and measurable external funding experience.

---

## Prioritization Approach

Capabilities were evaluated using the MoSCoW prioritization framework:

- **Must Have** — Required for MVP launch
- **Should Have** — Important but not required for initial launch
- **Could Have** — Valuable future enhancement
- **Won't Have** — Explicitly excluded from MVP

Prioritization considers customer value, business impact, regulatory and operational risk, technical dependencies, and implementation complexity.

---

## Must Have

### Financial Institution Search

Customers must be able to search for and select a supported external financial institution.

**Rationale:** External institution selection is required to begin the account connection process.

### External Account Authentication

Customers must be able to securely authenticate with the selected external financial institution.

**Rationale:** Authentication is required before external account information can be retrieved.

### Multi-Factor Authentication Support

The experience must support authentication challenges, including MFA, when required by the external financial institution.

**Rationale:** Customers cannot successfully connect institutions requiring additional authentication without this capability.

### External Account Retrieval

The system must retrieve eligible external accounts following successful authentication.

### Account Ownership Verification

External account ownership must be verified before the account can be used for funding.

**Rationale:** Required to mitigate unauthorized funding activity and satisfy risk requirements.

### Funding Account Selection

Customers must be able to select an eligible checking or savings account returned by the integration.

### Funding Amount

Customers must be able to specify their desired opening deposit.

MVP limits:

- Minimum: $25
- Maximum: $5,000

The system must prevent submission of funding requests outside permitted limits.

### ACH Funding Submission

The platform must submit the funding request through the appropriate ACH processing workflow.

### Funding Confirmation

Customers must receive confirmation that their funding request has been successfully submitted.

Confirmation must clearly distinguish **submission** from **settlement**.

### Transaction Status

The platform must support the following transaction states:

- Submitted
- Processing
- Completed
- Failed
- Returned

### API Error & Timeout Handling

The customer experience must appropriately handle:

- API errors
- Provider outages
- Authentication failures
- Timeouts
- Unexpected responses

Customers must not remain in an indefinite loading state.

### Duplicate Transaction Prevention

The platform must prevent accidental duplicate funding submissions.

### Failure & Return Handling

The system must support appropriate handling of rejected transactions, insufficient funds, and ACH returns.

### Operational Visibility

Operations must have sufficient visibility into funding transactions to identify:

- Current transaction status
- Failed transactions
- Returned transactions
- Transaction identifiers
- Relevant failure information

### Analytics & Instrumentation

The MVP must capture sufficient product analytics to evaluate customer behavior, system performance, and business outcomes.

Core events include:

- Institution search
- Institution selection
- Authentication attempt
- Successful connection
- Failed connection
- Funding initiated
- Funding submitted
- Funding completed
- Funding failed
- ACH return
- Customer abandonment

---

## Should Have

### Customer Support Transaction Lookup

Customer Support should have the ability to locate a customer's funding transaction and view non-sensitive status and error information.

This capability should not expose external banking credentials.

### Customer Notifications

Customers should receive appropriate notifications when meaningful funding events occur.

Potential notifications include:

- Funding request submitted
- Funding completed
- Funding failed
- Funding returned

Notification channels may include email, SMS, or existing digital banking messaging capabilities.

### Enhanced Operational Reporting

Operations should have access to reporting supporting funding volume, failure trends, returns, and exception analysis.

---

## Could Have

### Savings Account Opening Support

Expand the external funding experience to customers opening new savings accounts.

### Multiple Funding Sources

Allow customers to use more than one external account to fund a newly opened account.

### Enhanced Funding History

Provide customers with additional visibility into historical external funding activity.

### Advanced Operational Dashboard

Provide Operations and Product teams with enhanced visualization of transaction volume, completion rates, failure trends, API performance, and customer abandonment.

---

## Won't Have in MVP

### AI-Powered Customer Assistance

No current business requirement justifies introducing artificial intelligence into the initial funding experience.

Existing customer support and fraud capabilities will be leveraged.

### New Fraud Detection Model

The initiative will leverage existing enterprise fraud monitoring capabilities rather than developing a new fraud detection platform.

### Business Account Funding

External business accounts will not be supported as funding sources during MVP.

### Brokerage and Credit Card Funding

Brokerage accounts and credit cards are excluded as eligible funding sources.

### Multiple External Accounts Per Application

MVP will support a single external funding source per account-opening application.

---

## MVP Customer Journey

The targeted MVP experience is:

`Open Account`

↓

`Select External Funding`

↓

`Search Financial Institution`

↓

`Authenticate`

↓

`Complete MFA (if required)`

↓

`Retrieve Eligible Accounts`

↓

`Verify Account Ownership`

↓

`Select Funding Account`

↓

`Enter Funding Amount`

↓

`Review Funding Request`

↓

`Submit Funding Request`

↓

`Receive Confirmation`

↓

`Track Funding Status`

---

## MVP Success Measures

The product will be evaluated against measurable business and customer outcomes.

Key performance indicators include:

- Percentage of digitally opened accounts receiving an opening deposit
- External account connection success rate
- Funding submission success rate
- Funding completion rate
- Customer abandonment during funding
- Average time to complete external funding
- Authentication failure rate
- API error and timeout rate
- ACH return rate
- Funding-related Customer Support contacts

Baseline values and launch targets will be established with Digital Banking and Analytics before production release.

---

## MVP Exit Criteria

The MVP will be considered ready for production when:

1. All Must Have capabilities have been implemented.
2. Critical and high-severity defects have been resolved or formally accepted.
3. Required security and compliance reviews have been completed.
4. External account ownership verification has been validated.
5. End-to-end ACH funding has successfully completed in the production-like environment.
6. API failure and timeout scenarios have been tested.
7. Operational support procedures have been established.
8. Product analytics have been validated.
9. UAT has been completed and approved.
10. Production readiness approval has been received from required stakeholders.

---

## Future Considerations

Post-MVP development will be driven by customer behavior, operational feedback, analytics, and business priorities rather than automatically implementing all deferred capabilities.

Future opportunities may include expanded account eligibility, additional funding methods, enhanced customer notifications, operational dashboards, and improvements identified through production usage.
