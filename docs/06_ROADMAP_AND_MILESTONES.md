# Roadmap and Milestones

## Roadmap principle

Build in the order that evidence and operational readiness mature. Do not scale acquisition, automation or geography faster than recommendation quality and safety.

## Verified implementation status

| Milestone | Scope | Status |
|---|---|---|
| Foundation decisions | Django structure, database direction, identifiers, audit, state transitions, versioning, overrides and synthetic data policy | Implemented |
| Milestone 1 | Synthetic domain foundation, participants, consent records, journeys, review, access and audit | Implemented |
| Milestone 2 | Versioned assessment engine, evidence, sufficiency, contradiction and adaptive selection | Implemented |
| Milestone 3 | Versioned career intelligence registry, sources, market observations, staged imports and snapshots | Implemented |
| Milestone 4 | Transparent participant to career recommendation engine | Proposed next; owner contract review required |
| Milestone 5 | Practical experiment assignment, submission and evidence workflow | Planned |
| Milestone 6 | Small operator review interface and workflow | Planned |
| Milestone 7 | Official WhatsApp Business Platform integration | Planned and blocked by account, policy and operational decisions |
| Milestone 8 | Follow up automation, referral tracking and operational reporting | Planned |

Milestones 1 to 3 are code backed. The last source state document records 126 passing tests at its 5 October 2026 verification. Re run CI before relying on that count for a release.

## Recommended next milestone: Milestone 4

**Objective:** Produce transparent, reproducible candidate career directions from approved assessment and career snapshots.

### Entry conditions

- Owner reviews the assessment snapshot contract.
- Owner reviews the career snapshot contract.
- Candidate career taxonomy and granularity are approved.
- Minimum evidence and review triggers are defined.
- Capability and feasibility are separated.
- Recommendation explanation format is approved.

### Scope

- Frozen, versioned input snapshots.
- Versioned deterministic configuration.
- Candidate generation from multiple signals.
- Supporting evidence, conflicts and unknowns.
- Separate capability and feasibility dimensions.
- Market evidence freshness and unknown handling.
- Human review triggers.
- Immutable recommendation result and override history.
- Synthetic scenarios and regression tests.

### Explicit exclusions

- No AI generated ranking.
- No automatic participant delivery.
- No unsupported fit percentage.
- No salary guarantee.
- No external scraping.
- No production WhatsApp.
- No practical experiment workflow unless separately approved.
- No real participant data.

### Acceptance criteria

1. Same frozen inputs and config produce the same result.
2. One trait cannot independently determine a career.
3. Unknown and stale market data remain visible.
4. Supporting and conflicting evidence are both explained.
5. Capability and feasibility are not collapsed into one score.
6. Weak or contradictory evidence triggers more evidence or human review.
7. Every output records input and config versions.
8. Human override preserves the original output and requires reason.
9. Tests cover missing, conflicting, stale and synthetic data.
10. No participant facing recommendation is sent by this milestone.

## Subsequent milestones

| Milestone | Goal | Main deliverables | Exit gate |
|---|---|---|---|
| 5. Practical experiments | Validate candidate directions through real tasks | Experiment library, task rubric, assignment, submission, review and evidence link | Tasks are accessible, fair and produce useful additional evidence |
| 6. Operator workflow | Give humans a safe way to review and operate cases | Authenticated queue, participant summary, evidence view, review decisions, overrides and escalation | RBAC, audit and safeguarding workflow pass review |
| 7. WhatsApp integration | Enable the first participant channel | Official platform connection, webhook gateway, identity mapping, message state, templates, opt out and failure handling | Provider, account, consent, security and live message tests approved |
| 8. Follow up and reporting | Support continuity and operating insight | Scheduler, reminders, follow up outcomes, referral attribution and basic reporting | Delivery is reliable and human workload is measured |
| 9. Controlled pilot | Validate the service with a small cohort | Pilot operations, review capacity, feedback, completion and outcome measurement | Owner confirms quality, safety and operational readiness |
| 10. Web experience | Provide participant web access | Approved public site and authenticated participant experience | UX, API, privacy and accessibility acceptance |
| 11. Learning and longitudinal guidance | Support sustained development | Learning goals, activities, progress, reflection and roadmap updates | Learning content and outcomes are validated |
| 12. Channel and platform expansion | Add mobile, offline, voice and institutional capabilities | Separate technical and product projects | Each capability has a validated use case, cost and safeguarding plan |

## Effort estimates

The following are planning ranges for a small experienced team, not commitments or quotations. They exclude long external legal reviews, content research lead times and owner approval delays.

| Work package | Indicative effort |
|---|---:|
| Milestone 4 recommendation engine | 2 to 4 engineer weeks |
| Milestone 5 practical experiments | 2 to 4 engineer weeks plus content design |
| Milestone 6 operator workflow and RBAC | 3 to 6 engineer weeks |
| Milestone 7 WhatsApp integration | 2 to 4 engineer weeks plus provider setup |
| Milestone 8 follow up and reporting | 2 to 3 engineer weeks |
| Pilot preparation and validation | 3 to 6 calendar weeks depending on recruitment and reviewer availability |

Estimate after technical discovery. Do not convert these ranges into fixed delivery dates before the team reviews code, test coverage, deployment needs and dependencies.

## Product roadmap beyond the technical foundation

1. Karachi assisted discovery pilot.
2. Urdu first WhatsApp MVP after safety and quality gates.
3. Career intelligence depth and Pakistan market evidence.
4. Sindh and Punjab expansion with regional validation.
5. Automation maturity only after repeated quality evidence.
6. Longitudinal guidance and learning.
7. Broader Pakistan support.
8. Institutional products only after direct participant value is proven.

## Definition of Done for each milestone

- Scope and exclusions are explicit.
- Requirements and acceptance criteria are testable.
- Architecture and decision records are updated.
- Migrations are reviewed and reversible where practical.
- Automated tests pass.
- Security and privacy checks pass.
- Synthetic fixtures are used.
- Documentation matches code.
- CI evidence is linked.
- Known limitations and unresolved decisions are recorded.
- Owner acceptance is obtained for product or policy decisions.
