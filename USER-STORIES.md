# Patient Care Context — User Stories

## Domain Context Mapping

### Patient Management
**Primary Entities:**
- Patient
- Appointment
- Medical Record
- Doctor

**Responsibility:** Manages patient information, appointments, medical records, and patient care activities.

### Billing & Insurance Claims
**Primary Entities:**
- Invoice
- Payment
- Insurance Claim
- Insurance Provider

**Responsibility:** Manages patient billing, payments, insurance verification, and insurance claims.

### Lab Test Diagnostics
**Primary Entities:**
- Lab Test
- Test Order
- Sample
- Test Result
- Diagnosis

**Responsibility:** Manages laboratory test requests, samples, test results, and diagnostic information.

---

# User Story 1 — Appointment Rescheduling

**As a patient, I want to reschedule my appointment so that I can change my appointment time when I am unable to attend the original appointment.**

### Acceptance Criteria

#### Scenario: Patient reschedules an appointment within 24 hours of the appointment

**Given** a patient has a scheduled appointment for `2026-10-15T10:00:00Z`

**When** the patient requests a reschedule to `2026-10-16T14:00:00Z` less than 24 hours before the original time

**Then** the system should apply a `late-change` flag

**And** emit an `AppointmentRescheduled` event to the Notification Service

**And** display a confirmation message with updated appointment details to the patient.

---

# User Story 2 — View Lab Test Results

**As a patient, I want to view my completed laboratory test results so that I can understand the outcome of my tests and follow the recommended next steps in my care.**

### Acceptance Criteria

#### Scenario: Patient views a completed lab test result

**Given** the patient has a completed laboratory test with available results

**When** the patient requests to view the test result

**Then** the system should display the patient's test name, test date, result, and reference information

**And** the system should indicate that the test result is available

**And** the patient should be able to view the result without modifying the original laboratory record.

#### Scenario: Patient attempts to view an incomplete test result

**Given** the patient's laboratory test has not been completed

**When** the patient requests to view the test result

**Then** the system should display a message indicating that the result is not yet available

**And** the system should not display incomplete or unverified diagnostic results.
