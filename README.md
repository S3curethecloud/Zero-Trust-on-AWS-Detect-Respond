Zero Trust on AWS — Detect & Respond

STC Academy | Advanced Hands-On Lab

1. Purpose of This Lab

This lab demonstrates how Zero Trust is enforced on AWS through continuous detection and automated response, not merely through static IAM design.

Students will deploy, trigger, detect, correlate, and automatically respond to a trust violation using AWS-native services and event-driven automation.

This lab is:

Hands-on

Production-grade

Directly mappable to enterprise Zero Trust programs

Designed for STC Academy, consulting proof, and interviews

2. What “Zero Trust” Means in This Lab (Guru Perspective)

Zero Trust is not “deny by default.”
Zero Trust is continuous trust evaluation.

In AWS:

Detection = trust signal

Response = trust revocation

Automation = enforcement at scale

Trust is revoked dynamically when identity, behavior, or context violates expected intent.

3. Learning Objectives

By completing this lab, you will be able to:

Explain Zero Trust as a detect-and-respond model

Identify identity-based trust violations in AWS

Use GuardDuty + Security Hub for signal correlation

Build automated containment using event-driven security

Prove enforcement through audit-ready evidence

Map AWS controls to Zero Trust maturity levels

4. Zero Trust Maturity Mapping
Level	Capability	Implemented in This Lab
Level 1	Visibility	AWS CloudTrail
Level 2	Threat Detection	Amazon GuardDuty
Level 3	Signal Correlation	AWS Security Hub
Level 4	Automated Response	AWS Lambda
Level 5	Continuous Enforcement	Event-driven identity containment

This lab advances students from Level 2 → Level 5.

5. Architecture Overview
Core Flow
Identity Event
   ↓
CloudTrail
   ↓
GuardDuty
   ↓
Security Hub
   ↓
EventBridge
   ↓
Lambda (Containment)

Key AWS Services Used

AWS CloudTrail

Amazon GuardDuty

AWS Security Hub

Amazon EventBridge

AWS Lambda

6. Lab Prerequisites

AWS account with administrative permissions

Familiarity with IAM and STS concepts

Basic understanding of Lambda and JSON policies

Estimated time: 90–120 minutes

7. Hands-On Lab Walkthrough
Step 1 — Enable Detection Services

Enable the following:

GuardDuty (all regions)

Security Hub (AWS Foundational Security Best Practices)

Confirm CloudTrail is logging management events

Expected Outcome

GuardDuty operational

Security Hub receiving findings

📸 Screenshot to capture:

GuardDuty enabled

Security Hub dashboard

Step 2 — Simulate a Trust Violation

Trigger an identity-based anomaly such as:

Unusual STS role assumption

Privilege escalation attempt

API call from unexpected region

GuardDuty will generate a finding such as:

UnauthorizedAccess:IAMUser/AnomalousBehavior


📸 Screenshot to capture:

GuardDuty finding details page

Step 3 — Correlate Signals (Zero Trust Decision Point)

Security Hub aggregates:

GuardDuty finding

IAM context

Account metadata

This is the Zero Trust decision moment:

“Should this identity continue to be trusted?”

📸 Screenshot to capture:

Security Hub aggregated finding view

Step 4 — Automated Response (Trust Revocation)

EventBridge rule triggers a Lambda function that:

Disables the compromised IAM role

Revokes active STS sessions

Tags the principal as Quarantined=true

Logs evidence for forensics

📸 Screenshot to capture:

Lambda execution logs

IAM role disabled or modified

Step 5 — Validate Enforcement

Attempt the same access again.

Result

Access denied

Trust has been revoked

Incident fully documented

📸 Screenshot to capture:

Access denied error

Incident timeline

8. Evidence & Artifacts

This lab produces real security artifacts:

GuardDuty findings

Security Hub correlation

Lambda execution logs

CloudTrail evidence

Incident screenshots

Binder-ready documentation

All artifacts are referenced in:

04-screenshots/
binder/zero-trust-detect-respond.pdf

9. How This Integrates with STC / MGF

This lab registers as an MGF detection-response node:

MGF NODE
├── Signal: GuardDuty
├── Correlation: Security Hub
├── Decision: Lambda logic
├── Action: Identity containment
└── Artifact: Binder + screenshots


Supported conceptual commands:

mgf scan trust

mgf detect anomaly

mgf respond identity

mgf generate incident

10. Why This Matters (Interview & Consulting)

After this lab, you can confidently explain:

How Zero Trust actually works on AWS

How to automate containment safely

How to prove enforcement with evidence

How to design scalable detection-response pipelines

This lab is enterprise-credible, not theoretical.
