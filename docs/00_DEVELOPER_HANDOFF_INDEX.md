# GROW Developer Handoff

## Document control

| Field | Value |
|---|---|
| Product | GROW |
| Package | Developer documentation and project scoping |
| Version | 0.1 |
| Prepared | 25 November 2026 |
| Status | Draft for owner review |
| Authority | zakshub/grow |
| Working destination | zakshub/grow-prod |
| Intended readers | Product owner, technical lead, backend and frontend developers, UX designer, QA, operations and safeguarding reviewers |

## Executive summary

GROW is a Pakistan first education access, self discovery, capability discovery, career exploration and student direction platform. It is intended for people who do not yet understand their interests, strengths, working preferences, constraints, or realistic education and career options.

The product must not be reduced to a personality quiz, a chatbot, a course marketplace, a generic learning management system, or an automated career prediction service. Its central method is progressive discovery: gather context, collect multiple kinds of evidence, preserve uncertainty and contradictions, test promising directions through practical activities, and provide explainable guidance with human review where required.

The current source repository contains a synthetic Django domain foundation, deterministic assessment and evidence engine, and versioned career intelligence registry. It does not yet operate with real participants and does not contain production recommendation delivery, WhatsApp integration, AI interpretation, speech, payments, production operator permissions, or deployment.

The next proposed engineering milestone is a transparent recommendation engine. It must begin only after the owner reviews and approves the assessment snapshot and career snapshot contracts.

## How to use this package

Read in this order:

1. Product and Scope Definition
2. Requirements Catalogue
3. Architecture and Domain Boundaries
4. Participant Journeys
5. Privacy, Safety and Operations
6. Roadmap and Milestones
7. Risks and Decision Register
8. Developer Onboarding
9. Source Verification Record

This package is the developer handoff layer. The original source repository remains authoritative when a discrepancy is found. If this package conflicts with verified source code or an approved owner decision, record the discrepancy and resolve it rather than silently choosing one.

## Deliverables in this package

| File | Purpose |
|---|---|
| 01_PRODUCT_AND_SCOPE.md | Product definition, audience, boundaries and operating context |
| 02_REQUIREMENTS_CATALOGUE.md | Functional and non functional requirements with IDs and acceptance criteria |
| 03_ARCHITECTURE_AND_DOMAIN_BOUNDARIES.md | Current architecture, domain model, integrations and technical constraints |
| 04_PARTICIPANT_JOURNEYS.md | Participant and operator journeys, including minors and adult career reset |
| 05_PRIVACY_SAFETY_AND_OPERATIONS.md | Consent, minor protection, privacy, security and human operations |
| 06_ROADMAP_AND_MILESTONES.md | Existing milestone status, next build sequence, gates and effort estimates |
| 07_RISKS_AND_DECISIONS.md | Risk register, unresolved questions and owner decisions |
| 08_DEVELOPER_ONBOARDING.md | Repository workflow, local setup, tests and contribution discipline |
| 09_SOURCE_VERIFICATION_RECORD.md | Source snapshot, files inspected, verified claims and limits |

## Product principles

1. Discovery before recommendation.
2. No career inference from one trait or one personality label.
3. Separate interest, current ability, learning potential, values, constraints and opportunity.
4. Preserve unknowns rather than manufacturing certainty.
5. Preserve contradictory evidence and record human resolution.
6. Treat practical experiments as important evidence, not decorative gamification.
7. Keep human review for sensitive or high consequence decisions.
8. Do not automate a process until its quality is understood.
9. Urdu is the primary participant language; repository and engineering documentation remain English.
10. Build for smartphone access and uneven connectivity in Pakistan.
11. Never place identifiable participant records in GitHub.
12. Product claims must match implemented reality.

## Status vocabulary

Use the exact status labels defined in the README. In particular, do not use the word complete for a planned feature or for a model that exists without an end to end workflow.

## Approval checklist

Before a development team treats this package as a build contract, the owner must review:

- Product scope and public positioning.
- The proposed Milestone 4 input and output contracts.
- Assessment and career data versioning rules.
- Minor and guardian policy.
- Safeguarding ownership and escalation.
- Data retention, deletion and encryption policy.
- Production authentication and operator roles.
- Pilot cohort, review capacity and success criteria.
- WhatsApp provider and account ownership.
- Fee and payment policy.

Until these decisions are approved, related implementation must remain blocked or explicitly limited to synthetic development.
