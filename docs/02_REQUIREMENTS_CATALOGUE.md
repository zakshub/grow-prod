# Requirements Catalogue

## Requirement status

- **Implemented:** verified in code and tests.
- **Planned:** approved direction, not yet implemented.
- **Blocked:** cannot be implemented safely until a named decision or control exists.
- **Proposed:** requires owner approval.

Priority: P0 means a release or safety blocker; P1 means essential for the next usable workflow; P2 means important follow on; P3 means later expansion.

## Functional requirements

| ID | Requirement | Priority | Status | Acceptance criteria |
|---|---|---:|---|---|
| GROW-FR-001 | Maintain a participant record separate from direct identifiers | P0 | Implemented | Participant domain record uses a random UUID; direct identifiers are stored separately |
| GROW-FR-002 | Record consent as an explicit, versionable event | P0 | Partially implemented | Consent record exists and journey guards check consent; production consent wording and legal flow remain blocked |
| GROW-FR-003 | Represent guardian relationships and guardian handling state | P0 | Partially implemented | Relationship model exists; actual guardian identity verification and consent are blocked |
| GROW-FR-004 | Maintain one active participant journey with explicit state transitions | P1 | Implemented | State transition validates allowed graph, guards, reason and expected version; transition and audit write are atomic |
| GROW-FR-005 | Preserve unknown values explicitly | P0 | Implemented | Unknown states are represented without coercing missing values to zero or false |
| GROW-FR-006 | Support versioned assessment definitions and sessions | P1 | Implemented | Session pins definition version, audience, language, locale and item limit |
| GROW-FR-007 | Capture responses and observations as evidence with provenance | P1 | Implemented | Evidence records source, method, context, version, confidence, privacy class and time |
| GROW-FR-008 | Preserve contradictory evidence and reviewed resolution | P0 | Implemented | Contradiction links evidence items; resolution is audited and does not delete either item |
| GROW-FR-009 | Determine whether more assessment evidence is required | P1 | Implemented | Selector returns ASK_MORE, SUFFICIENT, HUMAN_REVIEW_REQUIRED or UNKNOWN |
| GROW-FR-010 | Maintain a versioned career intelligence registry | P1 | Implemented | Taxonomy, career profiles, skills, pathways, sources and market observations are versioned and reviewable |
| GROW-FR-011 | Publish career reference content only after human approval | P0 | Implemented | Import is staged, diffed and requires approval before publication |
| GROW-FR-012 | Generate a career snapshot without participant matching | P1 | Implemented | Snapshot contains career data, unknowns, freshness and limitations; it accepts no participant input |
| GROW-FR-013 | Match participant evidence to multiple career directions transparently | P1 | Planned | Given frozen versioned inputs, engine returns candidates with supporting, conflicting and missing evidence, constraints and explanations |
| GROW-FR-014 | Keep capability fit separate from pathway feasibility | P1 | Planned | Output separately represents evidence of capability/interest and practical feasibility constraints |
| GROW-FR-015 | Trigger human review when evidence is weak, conflicting or high consequence | P0 | Planned | Defined review triggers create a review requirement; no final participant advice is delivered before required review |
| GROW-FR-016 | Assign and capture practical experiments | P1 | Planned | Experiment has purpose, instructions, expected output, review rubric, submission and resulting evidence |
| GROW-FR-017 | Support follow up and longitudinal progress | P2 | Partially implemented | Follow up record exists; scheduling, delivery and outcome capture workflow remain unimplemented |
| GROW-FR-018 | Connect participant journey to official WhatsApp Business Platform | P1 | Blocked | Verified account/provider, consent, webhook verification, message mapping, opt out and failure handling pass integration tests |
| GROW-FR-019 | Provide production operator authentication and role based access | P0 | Blocked | Authenticated staff identities, least privilege roles, MFA and access audit are implemented and reviewed |
| GROW-FR-020 | Provide participant facing web experience | P2 | Planned | Approved UX prototype is implemented against production APIs and accessibility tests |
| GROW-FR-021 | Provide public information website | P2 | Planned | Public pages communicate verified capabilities and do not imply unavailable registration or service functions |
| GROW-FR-022 | Support fee and access decisions with human approval | P1 | Partially implemented | Access record exists; approved fee rules, payment integration and reconciliation are not implemented |
| GROW-FR-023 | Keep identifiable participant information out of GitHub | P0 | Implemented policy / ongoing control | Repository contains only synthetic fixtures; automated secret and data scans are added to CI |
| GROW-FR-024 | Provide AI assisted interpretation through a provider independent boundary | P2 | Planned | Business logic calls an internal interface; provider errors, data minimisation, prompt versioning and human review are tested |
| GROW-FR-025 | Provide speech transcription through a separate provider independent interface | P3 | Planned | Consent, language quality, retention and failure handling are validated before participant use |

## Non functional requirements

| ID | Requirement | Priority | Acceptance criteria |
|---|---|---:|---|
| GROW-NFR-001 | Auditability | P0 | Important state changes, reviews, overrides and publication decisions retain actor, reason, time and immutable history |
| GROW-NFR-002 | Data minimisation | P0 | Each field has a defined purpose, access class and retention decision |
| GROW-NFR-003 | Privacy by design | P0 | Sensitive records are isolated, access controlled and never committed to source control |
| GROW-NFR-004 | Accessibility | P1 | Keyboard operation, semantic structure, contrast, readable Urdu and responsive layouts are tested |
| GROW-NFR-005 | Mobile first usability | P1 | Core participant flows work on common smartphone viewport sizes and constrained connections |
| GROW-NFR-006 | Explainability | P0 | Every recommendation identifies evidence, conflicts, unknowns, limitations and next action |
| GROW-NFR-007 | Reproducibility | P1 | Assessment and career versions and calculation inputs are pinned to outputs |
| GROW-NFR-008 | Reliability | P1 | Webhook and background workflows are idempotent, retry safe and observable before production use |
| GROW-NFR-009 | Maintainability | P1 | Domain logic remains modular, typed, tested and documented |
| GROW-NFR-010 | Data integrity | P0 | Critical invariants have database constraints where possible and service level validation |
| GROW-NFR-011 | Performance | P2 | Performance targets are set after realistic workload and deployment sizing; no unsupported SLA is claimed |
| GROW-NFR-012 | Localization | P1 | Participant content supports Urdu and right to left presentation without hard coded English assumptions |
| GROW-NFR-013 | Operational safety | P0 | Human escalation, opt out, pause and incident procedures are tested before live pilot |
| GROW-NFR-014 | Portability | P2 | Environment configuration is externalised; deployment and backup procedures are reproducible |

## User roles

These are logical roles, not a claim that production RBAC exists.

| Role | Responsibility | Access boundary |
|---|---|---|
| Participant | Complete discovery, tasks and follow up | Own participant facing information only |
| Guardian | Provide required consent and appropriate support | Only approved information and actions under a confirmed policy |
| Reviewer | Review evidence, recommendations and exceptions | Assigned cases and minimum necessary sensitive information |
| Career content editor | Maintain career profiles and sources | Career registry only; publication requires approval |
| Operations administrator | Manage service workflow | Operational data according to role |
| Security administrator | Manage access, incident and security controls | Security metadata and authorised controls |
| Product owner | Approve product scope and policy | Decision authority, not automatic access to all sensitive content |

## User story examples

- As a student who does not know what career to choose, I want GROW to explore my interests through examples and tasks so that I am not forced to guess a career.
- As a participant, I want to understand why a question is being asked so that the process feels transparent.
- As a reviewer, I want to see evidence and contradictions rather than only a generated score so that I can make a responsible decision.
- As a guardian, I need a clear explanation of consent and safeguarding responsibilities before a minor participates.
- As a career content editor, I need sources, freshness and approval states so that outdated market claims are not silently published.

## Global acceptance rules

1. No single trait or personality label can determine a career.
2. Unknown is a valid outcome.
3. Evidence and interpretation must remain distinguishable.
4. A planning document does not establish implementation.
5. A recommendation must not be delivered as certain or guaranteed.
6. A human review gate cannot be bypassed by AI output.
7. Fee eligibility must not be inferred from career capability.
8. No real participant data may be used in fixtures, screenshots or demo accounts.
