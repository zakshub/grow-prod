# Testing and Release Gates

## Document control

| Field | Value |
|---|---|
| Package | GROW developer handoff |
| Version | 1.0 draft |
| Prepared | 25 November 2026 |
| Authority | `zakshub/grow` source repository |
| Status | Repository evidence reference, pending owner review |

## 1. Verified test baseline

The source current state document records 126 passing pytest tests at its last verification on 5 October 2026.

The latest GitHub Actions run visible for the source repository at the time of this documentation review was:

| Field | Value |
|---|---|
| Workflow | Grow validation |
| Run ID | 37308846272 |
| Commit | `80fb54fdb6bd37848c4f201bdeb643a876ca8e3c` |
| Branch | main |
| Started | 5 October 2026 |
| Result | Success |

This is historical CI evidence. It is not a fresh test execution on 25 November 2026. Re-run the workflow before treating the baseline as current release evidence.

## 2. Existing quality gates

The source repository and CI configuration identify these checks:

1. Ruff formatting check.
2. Ruff lint.
3. mypy type checking.
4. Django system checks.
5. Migration drift check.
6. Fresh database migrations.
7. Synthetic foundation fixture loader.
8. Synthetic assessment pack loader.
9. Synthetic career pack loader.
10. Full pytest suite.
11. PostgreSQL 18 CI service.

The source current state records that local SQLite migration and fixture validation passed. It also records that local PostgreSQL validation was unavailable during the 5 October verification. The successful GitHub Actions run provides the recorded PostgreSQL CI evidence for that commit.

## 3. Test domains represented

The source tree includes tests and synthetic fixtures for:

- Participant and identifier separation.
- Consent and guardian state representation.
- Journey transitions and transition guards.
- State version and audit behaviour.
- Assessment definition and version lifecycle.
- Assessment item selection and audience variants.
- Evidence provenance and append only behaviour.
- Evidence sufficiency and confidence workflow.
- Contradiction preservation and reviewed resolution.
- Career taxonomy and profile versioning.
- Career source and market observation freshness.
- Career import validation and human publication review.
- Human review and overrides.
- Access decisions and follow up records.

A test existing for a domain invariant does not mean the corresponding end user feature is production ready.

## 4. Release gates by capability

| Capability | Required gate | Current release position |
|---|---|---|
| Synthetic domain foundation | Fresh migrations, service tests, state and audit invariants | Implemented baseline |
| Assessment engine | Version pinning, source lineage, contradiction tests, unknown handling, synthetic content labels | Implemented baseline; instrument validity not established |
| Career registry | Versioned content, source freshness, import diff and approval tests | Implemented baseline; content is reference only |
| Recommendations | Reproducibility, multi signal explanations, conflicts, unknowns, capability/feasibility separation, review triggers | Not implemented |
| Practical experiments | Accessible task design, rubric reliability, evidence lineage, reviewer workflow | Not implemented |
| Operator interface | Auth, RBAC, MFA, sensitive read audit, safeguarding escalation and usability testing | Not implemented |
| WhatsApp | Signature verification, replay protection, idempotency, retries, opt out suppression and delivery reconciliation | Not implemented |
| AI text | Provider data review, schema validation, source grounding, uncertainty handling, prompt injection controls and human review | Not implemented |
| Speech | Urdu benchmark, transcription confidence, correction flow, secure media, retention and deletion | Not implemented |
| Production deployment | Security review, secrets, backup restore, monitoring, incident response, load and recovery tests | Not implemented |

## 5. Minimum acceptance tests for the next engineering milestone

Before Milestone 4 can be accepted:

- Identical frozen assessment and career snapshots plus identical configuration produce identical results.
- A single dimension or personality signal cannot independently determine a career direction.
- Supporting, conflicting and missing evidence are all represented in the result.
- Capability evidence and pathway feasibility remain separate.
- Unknown and stale market evidence remain unknown or stale.
- Low confidence, contradictory evidence and high consequence cases trigger review or additional evidence.
- Every result records input snapshot IDs, taxonomy version, configuration version and calculation version.
- Human overrides preserve the original proposal, before and after state, reason, actor reference and timestamp.
- Synthetic fixtures cover missing, conflicting, stale and incomplete data.
- No recommendation is delivered to a participant by this milestone.

## 6. Safety and production gates

No real participant operation should begin until the following are approved and implemented:

1. Minor classification, guardian verification, assent and consent policy.
2. Safeguarding playbook with staffed escalation and referral ownership.
3. Privacy notice, data classification, lawful processing review and provider data terms.
4. Production encryption, key management, least privilege and staff RBAC.
5. Retention and deletion schedule, including messages, media, backups and audit records.
6. Incident response and breach handling.
7. Approved Urdu content and assessment validation plan.
8. Reviewer training, calibration and available review capacity.
9. Fee and access policy, approvers and payment reconciliation.
10. Deployment, monitoring, backup restore and recovery drills.
11. WhatsApp account, official provider, consent wording, templates and opt out behaviour.
12. Pilot cohort, success measures, stop criteria and owner go/no go.

## 7. Verification reporting template

For every milestone, report:

| Field | Required evidence |
|---|---|
| Scope | Approved milestone and included requirements |
| Commit | Exact commit SHA and branch |
| Environment | Runtime and database used |
| Automated checks | Command, result and test count |
| CI | Workflow run URL and final status |
| Data | Synthetic fixtures only, unless an approved test plan says otherwise |
| Security/privacy | Checks performed and unresolved issues |
| Manual acceptance | Scenario, expected result, observed result |
| Known limitations | Explicit list |
| Decision requests | Owner approvals still required |

Never state that tests passed without a command result or CI run. Never treat a historical test count as a current result.
