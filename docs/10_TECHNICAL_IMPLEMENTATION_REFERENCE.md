# Technical Implementation Reference

## Document control

| Field | Value |
|---|---|
| Package | GROW developer handoff |
| Version | 1.0 draft |
| Prepared | 25 November 2026 |
| Authority | `zakshub/grow` main |
| Source commit | `80fb54fdb6bd37848c4f201bdeb643a876ca8e3c` |
| Status | Verified repository reference, pending owner review |

## 1. Architecture at a glance

GROW currently uses a Python 3.13+ and Django 5.2 modular monolith. Domain modules are separated in the application package and share one relational database. The current implementation favours explicit services, versioned records, deterministic rules and synthetic data.

The implemented architecture must be distinguished from the future target architecture. Redis, Dramatiq, WhatsApp, AI, speech, payment processing, a participant web frontend, production staff authentication and production deployment are not part of the current running product.

## 2. Verified technology baseline

| Area | Current evidence | Status |
|---|---|---|
| Language | Python, project declares Python >=3.13 | Implemented |
| Web framework | Django 5.2 | Implemented |
| Application structure | `src/grow` modular monolith | Implemented |
| Local database | SQLite default for local development and tests | Implemented |
| Deployment database | PostgreSQL configuration and ADR direction | Configured, not deployed |
| PostgreSQL CI | PostgreSQL 18 service in GitHub Actions | Verified successful run on 5 October 2026 |
| Tests | pytest and pytest-django | Implemented |
| Formatting and lint | Ruff | Implemented |
| Type checking | mypy with Django stubs | Implemented |
| Background jobs | Redis and Dramatiq | Not installed or used |
| Participant channel | Official WhatsApp Business Platform | Planned |
| AI and speech | Provider independent adapters | Planned, not implemented |
| Operator interface | Django Admin inspection only | Not production ready |
| Deployment | No production deployment verified | Not implemented |

## 3. Current domain modules

| Module | Main responsibility | Important boundary |
|---|---|---|
| `participants` | Participant, identifier, profile, consent, guardian relationship, referral source | Direct identifiers are separate from the participant domain record |
| `journeys` | Participant journey and state transition | Transitions use guarded services and append only history |
| `assessments` | Versioned definitions, items, sessions, responses, observations, evidence, dimension results and contradictions | Deterministic evidence handling; no AI or NLP interpretation |
| `careers` | Versioned taxonomy, profiles, aliases, relationships, skills, pathways, research sources and market observations | Participant independent reference registry; no matching or ranking |
| `reviews` | Human review and human overrides | Reviewer references are not production authenticated staff identities |
| `grow_access` | Fee and access decision records | No implemented fee policy or payment processor |
| `followups` | Follow up records | No scheduler or outbound messaging |
| `audit` | Audit event records | Production tamper resistance and event contract versioning remain open |
| `common` and `config` | Shared infrastructure and Django configuration | Not a substitute for production operations and security controls |

## 4. Implemented participant state model

The source state machine includes the following workflow states:

- `NEW`
- `CONSENT_PENDING`
- `PROFILE_INCOMPLETE`
- `DISCOVERY_IN_PROGRESS`
- `ASSESSMENT_IN_PROGRESS`
- `EXPERIMENT_PENDING`
- `EXPERIMENT_SUBMITTED`
- `HUMAN_REVIEW_REQUIRED`
- `RECOMMENDATION_READY`
- `ROADMAP_ACTIVE`
- `FOLLOW_UP_DUE`
- `COMPLETED`
- `PAUSED`
- `OPTED_OUT`

Important interpretation: `RECOMMENDATION_READY` is a guarded workflow state only. It does not mean a recommendation model, ranking, explanation, or participant delivery exists.

Each transition validates the allowed graph and guards, checks an expected state version when supplied, requires a reason, writes a transition record, increments the version and writes an audit event atomically. Pause and resume preserve the prior active state. Opt out closes the active journey.

The acknowledgement used by the development workflow for guardian handling is not legal guardian consent. No unresolved legal age threshold is hard coded.

## 5. Assessment and evidence model

The assessment engine is deterministic and versioned.

- Assessment sessions pin the exact assessment definition version, audience, language, locale and item limit.
- Published assessment content is immutable through the intended application service contract. A correction requires a new version.
- Nine item types are supported: Likert, binary, single choice, multiple choice, ranking, numeric, short text, long text and scenario choice.
- The synthetic dimension catalogue contains 81 pilot engineering dimensions across seven categories.
- The bundled synthetic assessment uses eight required dimensions and 14 items.
- The synthetic pack includes Urdu variants for Grade 8, Grade 10, Intermediate, University, Graduate and adult career switcher contexts, plus an English general fallback.
- Supported evidence sources include self report, structured question, open response, practical task, human observation, behavioural signal, historical example, follow up and reviewer judgment.
- Evidence and dimension results are append only and retain provenance, version, confidence inputs, sufficiency and contradiction references.
- Sufficiency states are UNKNOWN, INSUFFICIENT, TENTATIVE, SUPPORTED and CONTRADICTORY.
- The confidence value is an engineering heuristic for workflow control, not a psychometric score or scientific validity claim.

## 6. Career intelligence registry

Milestone 3 is implemented as a participant independent registry.

It contains versioned career taxonomy and profile records, aliases, career relationships, dimension relationships, environment observations, skills, skill requirements, pathways, research source metadata, market observations, human review decisions, staged import batches and import diffs.

Published content is protected by the application workflow and requires review. Market data supports explicit UNKNOWN and freshness states. Expired observations can be treated as stale without rewriting historical evidence.

The current synthetic career pack contains 12 reference careers. They are labelled synthetic and reference only, are not ready for participant recommendations, and have unknown demand, remote and salary observations.

## 7. Data integrity and privacy boundaries

- Domain primary keys use random UUIDs.
- Direct and external participant identifiers are stored separately from the participant record.
- Synthetic fixtures use hashed lookup aliases.
- One active journey per participant is database constrained.
- UNKNOWN is explicit and is not coerced to zero, false or low.
- Evidence corrections supersede prior versions rather than deleting history.
- Contradictory evidence is retained and requires audited resolution.
- No real participant data belongs in Git, fixtures, tests or ordinary logs.

Application level append only behaviour is not a complete security boundary. Raw SQL, bulk updates and privileged database access can bypass application rules. Production database permissions, encryption, tamper evidence, retention and deletion controls remain required.

## 8. Integration boundaries

| Integration | Current state | Required before production |
|---|---|---|
| WhatsApp | Not implemented | Official provider, account, opt in/out, webhook verification, templates, delivery reconciliation and security review |
| AI text | Not implemented | Provider evaluation, data processing terms, privacy review, typed outputs, evidence lineage and human review |
| Speech | Not implemented | Representative Pakistani Urdu benchmark, secure media handling, transcription uncertainty and retention controls |
| Payments | Not implemented | Approved fee rules, payment provider, reconciliation and exception handling |
| Staff identity | Not implemented | Authenticated staff accounts, RBAC, MFA, sensitive read audit and access review |
| Hosting | Not deployed | Environment, secrets, backups, restore drills, monitoring, incident response and recovery objectives |

## 9. Future target architecture principles

The future system may add an official WhatsApp adapter, durable inbound and outbound event handling, asynchronous workers, authenticated operator experience, AI and speech adapters, practical experiments, transparent recommendations and a participant web experience.

These are architectural directions, not existing services. Add them only against an approved milestone and the entry criteria in the roadmap.

## 10. Source files for implementation work

Start with these source locations:

- `src/grow/participants`
- `src/grow/journeys`
- `src/grow/assessments`
- `src/grow/careers`
- `src/grow/reviews`
- `src/grow/access`
- `src/grow/followups`
- `src/grow/audit`
- `src/grow/config`
- `docs/implementation/00_CURRENT_STATE.md`
- `docs/technical/01_ARCHITECTURE.md`
- `docs/technical/03_DATA_MODEL.md`
- `docs/technical/04_STATE_MACHINE.md`
- `docs/adr/README.md`

## 11. Implementation rule

Before adding a model, service, integration or state, inspect the current source implementation and the relevant ADR. Do not duplicate existing entities, infer a feature from a planning diagram, or treat synthetic content as approved participant facing content.
