```
zero-trust/
└── aws/
    └── 01-detect-and-respond/
        ├── README.md
        ├── architecture/
        │   ├── detect-and-respond.mmd
        │   └── detect-and-respond.png
        ├── labs/
        │   ├── 01-logging-foundation/
        │   │   └── README.md
        │   ├── 02-guardduty-detection/
        │   │   └── README.md
        │   ├── 03-security-hub-centralization/
        │   │   └── README.md
        │   └── 04-automated-response/
        │       └── README.md
        ├── terraform/
        │   ├── guardduty/
        │   ├── security-hub/
        │   ├── eventbridge/
        │   └── lambda-response/
        └── evidence/
            └── screenshots/
```
         

            # AWS Zero Trust — Detect and Respond
## Volume 01: Continuous Visibility, Threat Detection, and Automated Response

This module implements the **Detect and Respond** pillar of Zero Trust on AWS.
The objective is to eliminate static trust assumptions by continuously observing
behavior, detecting anomalies, and responding automatically to risk signals.

---

## Zero Trust Alignment

| Zero Trust Principle | AWS Implementation |
|---------------------|-------------------|
| Assume Breach | GuardDuty continuous threat analysis |
| Continuous Verification | CloudTrail + VPC Flow Logs |
| Least Privilege Reaction | Automated isolation and credential revocation |
| Minimize Blast Radius | Event-driven containment |

---

## Architecture Overview

**Signal Sources**
- AWS CloudTrail
- VPC Flow Logs
- DNS Logs

**Detection**
- Amazon GuardDuty

**Aggregation & Compliance**
- AWS Security Hub

**Automation**
- Amazon EventBridge
- AWS Lambda (response functions)

---

## Labs Overview

| Lab | Focus |
|----|------|
| Lab 01 | Logging & telemetry foundation |
| Lab 02 | Threat detection with GuardDuty |
| Lab 03 | Centralized findings via Security Hub |
| Lab 04 | Automated response and isolation |

Each lab is independent but builds toward a unified Zero Trust detection fabric.

---

## Outcomes

By completing this module, you will be able to:

- Explain Zero Trust detection to executives and auditors
- Demonstrate hands-on GuardDuty + Security Hub integration
- Prove automated containment using event-driven security
- Reuse this pattern across multi-account AWS environments

---

## Compliance Mapping (Reference)

- CIS AWS Foundations
- AWS Foundational Security Best Practices
- PCI-DSS (monitoring & incident response controls)
- HIPAA Security Rule (audit & response alignment)

---

## Next Module

➡ **02-device-and-workload-trust**  
Device posture, workload verification, and identity-aware access enforcement.

# Lab 0X — <Title>

## Objective
What Zero Trust control this lab enforces.

## Architecture
Describe signal → detection → response flow.

## Prerequisites
- AWS Account
- IAM permissions
- Prior labs (if any)

## Steps
1. Configuration
2. Validation
3. Threat simulation (where applicable)

## Evidence
Screenshots or logs proving execution.

## Zero Trust Takeaway
What trust assumption was removed.
