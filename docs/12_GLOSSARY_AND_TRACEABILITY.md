# Glossary and Traceability Guide

## Document control

| Field | Value |
|---|---|
| Package | GROW developer handoff |
| Version | 1.0 draft |
| Prepared | 25 November 2026 |
| Status | Draft for owner review |

## 1. Glossary

| Term | Meaning in GROW |
|---|---|
| Participant | Person using GROW for education, self discovery or career direction |
| Journey | A versioned operational process tracking a participant from entry through discovery, review and follow up |
| Life stage track | Context such as school discovery, college direction, university/graduate or adult career reset |
| Assessment definition | Stable identity for a set of assessment content and rules |
| Assessment version | Immutable published release of assessment sections, dimensions, items and selection policy |
| Dimension | A distinct area being explored, such as interest, work value, communication or analytical reasoning |
| Evidence source | The method or origin from which evidence was collected |
| Evidence item | A provenance bearing record of a response, observation or other signal |
| Dimension result | Append only projection describing evidence sufficiency for one dimension |
| Sufficiency | Whether available evidence is absent, inadequate, tentative, supported or contradictory |
| Confidence | An internal pilot workflow heuristic about evidence strength, not a scientific or psychometric score |
| Contradiction | Two or more evidence items that point in opposing directions and must remain visible |
| Career taxonomy | Versioned classification of career clusters, families and profiles |
| Career profile | Structured reference description of a career and its skills, pathways and context |
| Market observation | Sourced, dated and geographically contextual evidence about salary, demand or opportunity |
| Freshness | Whether a source or observation is current, stale, retired or unknown |
| Snapshot | Frozen, versioned representation of inputs used for a later reproducible process |
| Human review | A recorded review action by a responsible human reviewer |
| Human override | A reasoned human change that preserves the original proposal and its history |
| Synthetic data | Fabricated test records that do not represent real participants |
| UNKNOWN | An explicit state meaning that evidence is unavailable or insufficient to assert a value |
| Reference only | Content may support internal development but is not approved for participant recommendations |
| Release blocker | A condition that must be resolved before a named capability or live operation can proceed |

## 2. Status vocabulary

Use the following labels consistently across requirements, roadmap, architecture and delivery reports.

| Status | Definition |
|---|---|
| Implemented | Verified in current source code and relevant tests |
| Partially implemented | Some required records or logic exist, but the complete workflow is absent |
| Planned | Included in an approved direction or roadmap but not implemented |
| Proposed | Suggested and awaiting owner approval |
| Blocked | Cannot safely or correctly proceed until a named dependency or decision is resolved |
| Unknown | Evidence is insufficient to make a reliable status claim |
| Retired | Previously supported or planned but no longer intended |

A document, database model, mockup, workflow state or synthetic fixture alone does not prove an end to end feature is implemented.

## 3. Traceability map

| Topic | Product authority | Technical authority | Delivery reference |
|---|---|---|---|
| Product vision and scope | `docs/01_PRODUCT_VISION.md` | `docs/technical/00_TECHNICAL_PLAN.md` | `01_PRODUCT_AND_SCOPE.md` |
| Audience and participant journeys | `docs/02_AUDIENCE_AND_SCOPE.md`, `docs/05_PARTICIPANT_JOURNEY.md` | `docs/technical/04_STATE_MACHINE.md` | `04_PARTICIPANT_JOURNEYS.md` |
| Assessment and evidence | `docs/04_ASSESSMENT_MODEL.md` | `docs/technical/05_ASSESSMENT_ENGINE.md` | `10_TECHNICAL_IMPLEMENTATION_REFERENCE.md` |
| Career intelligence | `docs/03_CAREER_DISCOVERY_ENGINE.md` | `docs/technical/06_CAREER_INTELLIGENCE.md` | `10_TECHNICAL_IMPLEMENTATION_REFERENCE.md` |
| Privacy and safeguarding | `docs/09_DATA_PRIVACY_AND_SAFETY.md` | `docs/technical/10_SECURITY_PRIVACY.md` | `05_PRIVACY_SAFETY_AND_OPERATIONS.md`, `07_RISKS_AND_DECISIONS.md` |
| Architecture and data | `docs/10_SYSTEM_ARCHITECTURE.md` | `docs/technical/01_ARCHITECTURE.md`, `docs/technical/03_DATA_MODEL.md` | `03_ARCHITECTURE_AND_DOMAIN_BOUNDARIES.md`, `10_TECHNICAL_IMPLEMENTATION_REFERENCE.md` |
| Milestones and roadmap | `docs/12_MVP_BUILD_PLAN.md`, `docs/13_ROADMAP.md` | `docs/technical/13_IMPLEMENTATION_MILESTONES.md` | `06_ROADMAP_AND_MILESTONES.md` |
| Testing and acceptance | `docs/17_FEATURE_INVENTORY.md` | `docs/technical/12_TESTING.md` | `11_TESTING_AND_RELEASE_GATES.md` |
| Open decisions | `docs/16_OPEN_QUESTIONS.md` | `docs/technical/14_RISKS_AND_OPEN_DECISIONS.md` | `07_RISKS_AND_DECISIONS.md` |

## 4. Source hierarchy

When sources disagree, use this order:

1. Current verified source code and tests for implemented behaviour.
2. Explicitly approved owner decisions and ADRs for product/technical policy.
3. Current implementation status and milestone records.
4. Product and technical planning documents.
5. This developer handoff package.
6. Unapproved proposals and assumptions.

Do not silently resolve a conflict. Record it in the decision register and ask the relevant owner.

## 5. Repository references

- Source of truth: https://github.com/zakshub/grow
- Production workspace: https://github.com/zakshub/grow-prod
- UX decision intelligence: https://github.com/zakshub/designer
- Visual production intelligence: https://github.com/zakshub/studio

## 6. Design and documentation method used

The documentation structure uses the inspected Designer repository's product context first approach, evidence based hierarchy, mechanism based references, explicit tradeoffs and accessibility considerations.

The Designer skill manifest currently exposes one example fixture skill record, not a broad set of executable UX skills. This package therefore records the design methods inspected and applied, and does not claim that a large automated skill library was run.

Studio is an imagery production system. Its source preservation and provenance rules were inspected, but no image generation or editing was required for this technical documentation package.
