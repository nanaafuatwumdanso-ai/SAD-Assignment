# Patient Care Context — Domain Context Map

```mermaid
flowchart LR
    PM["Patient Management"]
    BI["Billing & Insurance Claims"]
    LD["Lab Test Diagnostics"]
    NS["Notification Service"]

    PM -->|"Patient / Appointment Information"| BI
    PM -->|"Lab Test Orders"| LD
    LD -->|"Test Results"| PM
    BI -->|"Billing / Insurance Status"| PM
    PM -->|"Appointment Events"| NS
```

## Bounded Contexts

### Patient Management
**Entities:** Patient, Appointment, Medical Record, Doctor

Manages patient information, appointments, medical records, and patient care activities.

### Billing & Insurance Claims
**Entities:** Invoice, Payment, Insurance Claim, Insurance Provider

Manages patient billing, payments, insurance verification, and insurance claims.

### Lab Test Diagnostics
**Entities:** Lab Test, Test Order, Sample, Test Result, Diagnosis

Manages laboratory test requests, samples, test results, and diagnostic information.
