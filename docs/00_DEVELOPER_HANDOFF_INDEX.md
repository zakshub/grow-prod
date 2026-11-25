# GROW Developer Handoff

## Document control

| Field | Value |
|---|---|
| Product | GROW |
| Package | Developer documentation and project scoping |
| Version | 1.0 |
| Prepared | 25 November 2026 |
| Status | Draft for owner review |
| Authority | `zakshub/grow` |
| Working destination | `zakshub/grow-prod` |
| Intended readers | Product owner, technical lead, backend and frontend developers, UX designer, QA, operations and safeguarding reviewers |

## Executive summary

GROW is a Pakistan first education access, self discovery, capability discovery, career exploration and student direction platform. It is intended for people who do not yet understand their interests, strengths, working preferences, constraints or realistic education and career options.

The product must not be reduced to a personality quiz, chatbot, course marketplace, generic learning management system or automated career prediction service. Its central method is progressive discovery: gather context, collect multiple kinds of evidence, preserve uncertainty and contradictions, test promising directions through practical activities, and provide explainable guidance with human review where required.

The current source repository contains a synthetic Django domain foundation, deterministic assessment and evidence engine, and versioned career intelligence registry. The latest source state explicitly says that real participant operation, participant to career matching, recommendation logic, practical experiments, WhatsApp, external AI, speech, payment processing, production staff authentication and production deployment are not implemented.

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
10. Technical Implementation Reference
11. Testing and Release Gates
12. Glossary and Traceability

The original source repository remains authoritative when a discrepancy is found. If this package conflicts with verified source code or an approved owner decision, record the discrepancy and resolve it rather than silently choosing one.

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
| 09_SOURCE_VERIFICATION_RECORD.md | Source snapshot, inspected files, verified claims and limitations |
| 10_TECHNICAL_IMPLEMENTATION_REFERENCE.md | Current modules, data boundaries, state model and integration status |
| 11_TESTING_AND_RELEASE_GATES.md | Verified test evidence, release criteria and safety gates |
| 12_GLOSSARY_AND_TRACEABILITY.md | Shared terminology, source hierarchy and requirement traceability |
| diagrams/ | Editable Mermaid architecture and workflow diagram sources |

## Product principles

1. Discovery before recommendation.
2. No career inference from one trait or one personality label.
3. Separate interest, current ability, learning potential, values, constraints and opportunity.
4. Preserve evidence provenance, contradictions, confidence and unknowns.
5. Use practical experiments to test promising directions before major decisions.
6. Keep high impact decisions reviewable by a human.
7. Never confuse synthetic content with validated assessment or market evidence.
8. Do not activate minors or real participants until consent, safeguarding, privacy and operational gates are approved.

## Status vocabulary

- **Implemented:** verified in source code and relevant tests.
- **Partially implemented:** some records or logic exist, but the complete workflow is incomplete.
- **Planned:** in approved direction, not implemented.
- **Proposed:** awaiting owner approval.
- **Blocked:** cannot safely proceed until a named dependency is resolved.
- **Unknown:** evidence is insufficient to make a claim.

## Repository authority

- Source of truth: https://github.com/zakshub/grow
- Production workspace: https://github.com/zakshub/grow-prod
- UX decision intelligence: https://github.com/zakshub/designer
- Visual production intelligence: https://github.com/zakshub/studio

Do not commit new work to the source repository without explicit owner approval.
