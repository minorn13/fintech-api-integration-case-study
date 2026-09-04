# Functional Requirements

## Digital Account Funding API Integration

### Purpose

This document defines the functional behavior required to support external account funding within the digital account opening experience.

---

## Institution Search & Selection

### FR-001
The system shall allow the customer to search for supported external financial institutions.

### FR-002
The system shall display matching supported institutions returned by the external account provider.

### FR-003
The customer shall be able to select a financial institution from the returned results.

### FR-004
If an institution is unavailable or unsupported, the system shall provide an appropriate customer-facing message.

---

## Authentication

### FR-005
The system shall initiate the third-party authentication experience for the selected financial institution.

### FR-006
The integration shall support multi-factor authentication and other authentication challenges when required by the external institution.

### FR-007
The system shall recognize successful, failed, cancelled, and timed-out authentication attempts.

### FR-008
Authentication failures shall return the customer to an actionable state with appropriate guidance.

---

## External Account Retrieval

### FR-009
Following successful authentication, the system shall request available external accounts.

### FR-010
The system shall identify accounts eligible for external funding.

### FR-011
MVP shall support eligible consumer checking and savings accounts.

### FR-012
Ineligible account types shall not be selectable as funding sources.

### FR-013
If no eligible accounts are returned, the customer shall receive an appropriate message.

---

## Account Verification

### FR-014
The system shall perform required external account ownership verification before funding submission.

### FR-015
An account that fails required ownership verification shall not be eligible for funding.

### FR-016
The system shall record the result of the verification process without exposing sensitive authentication information.

---

## Funding

### FR-017
The customer shall be able to select one eligible external account as the funding source.

### FR-018
The customer shall be able to enter a funding amount.

### FR-019
The system shall validate the funding amount against applicable minimum and maximum limits.

### FR-020
The system shall prevent submission when the funding amount is below $25 or above $5,000 for the MVP.

### FR-021
The customer shall be presented with an opportunity to review relevant funding information before submission.

### FR-022
The system shall submit an approved funding request to the designated ACH processing workflow.

---

## Transaction Processing

### FR-023
The system shall assign or retain a unique identifier sufficient to trace each funding transaction.

### FR-024
The solution shall support the following transaction states:

- Submitted
- Processing
- Completed
- Failed
- Returned

### FR-025
The system shall update the transaction status when relevant downstream status information becomes available.

### FR-026
The customer shall receive confirmation when the funding request has been successfully submitted.

### FR-027
Submission messaging shall clearly indicate that submission does not represent final settlement.

---

## Duplicate Prevention

### FR-028
The system shall prevent accidental duplicate funding submissions caused by repeated customer actions.

### FR-029
The integration shall support an appropriate mechanism for identifying or safely processing repeated transaction requests.

---

## Error Handling

### FR-030
The system shall handle third-party API errors without leaving the customer in an indefinite processing state.

### FR-031
The system shall handle API timeouts using defined timeout and recovery behavior.

### FR-032
Customer-facing errors shall provide actionable guidance when appropriate.

### FR-033
Technical error details shall be captured for authorized operational troubleshooting without exposing sensitive information to the customer.

### FR-034
The solution shall support appropriate handling of failed and returned ACH transactions.

---

## Operational Support

### FR-035
Authorized Operations users shall be able to identify funding transactions and view current status.

### FR-036
Authorized users shall be able to identify failed and returned transactions.

### FR-037
Operational transaction information shall include sufficient identifiers and failure information to support investigation.

### FR-038
Customer Support shall not have access to external financial institution credentials.

---

## Analytics

### FR-039
The solution shall capture defined customer journey events related to external funding.

### FR-040
The solution shall capture successful and unsuccessful external account connection attempts.

### FR-041
The solution shall capture funding initiation, submission, completion, failure, and return events.

### FR-042
The solution shall support measurement of customer abandonment during the external funding journey.

### FR-043
The solution shall capture integration performance information necessary to monitor API failures and timeouts.

---

## Notifications

### FR-044
The solution should support customer notification when significant funding status changes occur.

Notification requirements and channels will be finalized during detailed solution design.
