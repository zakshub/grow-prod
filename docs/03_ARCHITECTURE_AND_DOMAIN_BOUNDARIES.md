# Architecture and Domain Boundaries

## 1. Current architecture

The source repository implements a Django modular monolith using Python 3.13+ and Django 5.2. The code is organised under src/grow with domain apps for participants, journeys, assessments, careers, reviews, access, followups and audit.

SQLite is the default for local development and tests. PostgreSQL configuration exists and PostgreSQL is the intended authoritative deployed database. GitHub Actions configures PostgreSQL 18 for CI validation.

Redis and Dramatiq are not installed or used. Their future boundary is documented in ADR 0003. Do not add them until a real asynchronous workload requires them.

Django Admin is currently an inspection surface for development. It is not a production operator interface and does not establish a production authorisation model.

## 2. Domain modules

| Module | Current responsibility | Boundary |
|---|---|---|
| participants | Participant, profile, identifier, consent, guardian relationship and referral records | Direct identifiers remain separate from participant domain identity |
| journeys | Participant journey and explicit state transitions | State changes go through guarded services and append only history |
| assessments | Versioned assessment definitions, items, sessions, responses, observations, evidence, results and contradictions | Deterministic evidence handling; no AI/NLP interpretation |
| careers | Versioned career taxonomy, profiles, skills, pathways, sources and market observations | Participant independent reference registry; no matching or ranking |
| reviews | Human review and append only human overrides | Reviewer identity is currently a pseudonymous reference, not production staff authentication |
| access | Fee/access decision record | No implemented fee policy or payment processor |
| followups | Follow up record | No scheduler or outbound delivery workflow |
| audit | Append only audit event records | Event contract versioning and production tamper resistance remain open |

## 3. Core data and evidence rules

- Domain primary keys use random UUIDs.
- Direct or external identifiers are stored separately from Participant.
- Synthetic fixtures use SHA-256 lookup aliases.
- One active journey per participant is database constrained.
- Unknown is explicit for important participant, consent, evidence, assessment, career market, review, access and follow up states.
- Evidence sources and evidence items are append only at the service contract level.
- New evidence can supersede older evidence without deleting the historical record.
- Contradictions retain all linked evidence and require audited resolution.
- Assessment sessions pin the exact definition version, audience, language, locale and item limit.
- Assessment result projections preserve evidence IDs, calculation inputs and version, confidence, sufficiency, contradictions, reasons and next action.
- Career taxonomy and profile content are versioned. Published content is application immutable; corrections create new versions.
- Market observations retain geography, source, freshness and unknown state.
- Staged career imports are validated, hashed, diffed and require human approval before publication.

Application level append only behaviour is not a complete security guarantee. Raw SQL, bulk updates and privileged database access can bypass it. Production controls must include database permissions and tamper evidence.

## 4. Participant state machine

Implemented normal transitions:

NEW → CONSENT_PENDING → PROFILE_INCOMPLETE → DISCOVERY_IN_PROGRESS → ASSESSMENT_IN_PROGRESS

ASSESSMENT_IN_PROGRESS → EXPERIMENT_PENDING or HUMAN_REVIEW_REQUIRED

EXPERIMENT_PENDING → EXPERIMENT_SUBMITTED → HUMAN_REVIEW_REQUIRED

HUMAN_REVIEW_REQUIRED → ASSESSMENT_IN_PROGRESS, EXPERIMENT_PENDING or RECOMMENDATION_READY

RECOMMENDATION_READY → ROADMAP_ACTIVE → FOLLOW_UP_DUE

FOLLOW_UP_DUE → ROADMAP_ACTIVE or COMPLETED

Active workflow states can pause and resume. Non terminal contactable states can opt out. Completion and opt out close the active journey.

Each transition locks the journey row, optionally checks the expected state version, validates the transition graph and guards, requires a reason, writes a state transition, increments state_version and writes an audit event atomically.

Important limitation: EXPERIMENT and RECOMMENDATION states are workflow gates only. Their full domain workflows and participant delivery are not implemented.

Consent progression requires a granted latest participation consent, known minor status, known guardian requirement, and required guardian handling acknowledgement. The acknowledgement is a development workflow marker, not legal guardian consent.

## 5. Assessment architecture

The assessment system supports immutable numbered definition versions with DRAFT, PILOT, ACTIVE and RETIRED lifecycle states. Sessions pin the exact version and context. Nine structured/text item types are supported. The pilot taxonomy has 81 dimensions across seven categories; the synthetic v1 pack exercises eight required dimensions using 14 items.

Sufficiency states are UNKNOWN, INSUFFICIENT, TENTATIVE, SUPPORTED and CONTRADICTORY. Adaptive selection returns ASK_MORE, SUFFICIENT, HUMAN_REVIEW_REQUIRED or UNKNOWN.

Confidence is a deterministic engineering heuristic based on evidence source diversity, review and unresolved contradictions. It is not a validated psychometric score and must not be presented as one.

## 6. Career intelligence architecture

The registry includes versioned taxonomies, clusters, families, career profiles, aliases, relationships, dimension relationships, environment observations, skills, skill requirements, pathways, research sources, market observations, review decisions, import batches and import diffs.

The synthetic career pack contains 12 reference careers. All are marked SYNTHETIC, REFERENCE_ONLY and NOT_READY_FOR_PARTICIPANT_RECOMMENDATION. Bundled demand, remote and salary observations are UNKNOWN.

The career snapshot contains career reference information, unknowns, freshness, evidence, routes and limitations. It accepts no participant or assessment input. No matching or ranking is performed.

## 7. Proposed next architecture: recommendation boundary

Milestone 4 should be a deterministic, transparent service first. It should accept frozen, versioned assessment and career snapshots plus an explicit versioned configuration. It should return candidate directions with support, conflict, missing evidence, feasibility constraints, source freshness, explanation and review requirement.

It must not mutate source snapshots. It must not create false precision. It must not use AI as the ranking authority. It must not deliver final advice without required human review.

Before implementation, the owner must approve:
- Assessment snapshot contract.
- Career snapshot contract.
- Candidate taxonomy and granularity.
- How capability evidence differs from feasibility.
- Minimum evidence and review thresholds.
- Output explanation and participant language.
- Human override and audit contract.

## 8. Integration boundaries

| Integration | Status | Required future boundary |
|---|---|---|
| WhatsApp Business Platform | Not implemented | Official Meta platform or approved provider, verified webhooks, opt out, idempotency and message failure handling |
| AI provider | Not implemented | Provider independent interface, prompt versioning, data minimisation, structured outputs and review |
| Speech transcription | Not implemented | Separate speech interface, Urdu quality evaluation, consent and retention |
| Payment provider | Not implemented | Owner approved fee policy, reconciliation, refund and audit handling |
| Background jobs | Not implemented | Add Redis/Dramatiq only when a concrete scheduled or asynchronous workload exists |
| Web frontend | Not implemented | API and UI contract to be designed after approved journeys |
| Mobile/offline | Future | Sync, conflict handling, device storage, offline privacy and accessibility decisions |

## 9. Deployment and environment

The project uses environment based settings. Local default is SQLite. PostgreSQL settings are available through environment variables. The development secret fallback is only allowed with DEBUG enabled; production requires DJANGO_SECRET_KEY.

The current CI workflow runs Python 3.13, installs the development dependencies, checks Ruff formatting and lint, mypy, Django system checks, migration drift, migrations, all three synthetic loaders and pytest against PostgreSQL 18.

No production deployment topology, VPS provider, TLS termination, secrets manager, backup executor, monitoring stack or recovery objective has been implemented or approved.

## 10. Architecture rules

1. Preserve modular monolith until a measured need justifies distribution.
2. Keep business logic behind domain services.
3. Treat PostgreSQL as deployed workflow authority.
4. Keep direct identifiers separated and access restricted.
5. Preserve immutable version and evidence history.
6. Use synthetic data only in development.
7. Do not introduce integrations before policy, ownership and failure behaviour are defined.
8. Keep AI and speech behind provider independent interfaces.
9. Keep participant recommendations explainable and reviewable.
10. Do not expose internal provider routing, prompts or secrets in participant interfaces.
