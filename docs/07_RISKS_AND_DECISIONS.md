# Risk and Decision Register

## 1. Critical risks

| ID | Risk | Likelihood | Impact | Mitigation | Owner / gate |
|---|---|---|---|---|---|
| R-001 | Assessment appears more scientifically valid than evidence supports | High | Critical | Label pilot heuristics, validate instruments and Urdu adaptations, avoid deterministic labels | Product owner and assessment researcher |
| R-002 | Minor participates without valid consent or safeguarding coverage | Medium | Critical | Block live minor participation until legal policy, guardian verification and staffed escalation exist | Owner and legal/safeguarding lead |
| R-003 | Recommendations overstate career fit or market opportunity | High | High | Multi signal evidence, unknown states, source freshness, practical trials and human review | Product owner and career reviewer |
| R-004 | Sensitive participant data is exposed through repositories, logs or AI providers | Medium | Critical | Data classification, minimisation, encryption, access controls, retention and provider review | Security/privacy owner |
| R-005 | Human review is promised but reviewer capacity is unavailable | Medium | High | Name reviewers, service hours, queue limits and escalation coverage before pilot | Operations owner |
| R-006 | Career content is synthetic or stale but shown as Pakistan market fact | High | High | Keep synthetic label, require sources and freshness, approve publication | Career content owner |
| R-007 | Product scope expands into mobile, voice, games and institutional tooling before core value is validated | High | High | Milestone gates and explicit exclusions | Product owner |
| R-008 | WhatsApp provider, templates or account are not ready | Medium | High | Confirm account, platform route, template requirements and opt out before integration | Channel owner |
| R-009 | SQLite behaviour is mistaken for production PostgreSQL validation | Medium | High | Run PostgreSQL CI and production like concurrency tests | Technical lead |
| R-010 | Application level append only rules are bypassed by privileged writes | Medium | High | Database roles, restricted write paths and tamper evidence | Technical lead |
| R-011 | Urdu copy or tasks disadvantage participants with limited literacy or device access | Medium | High | User research across education stages, phone testing and language review | UX and research lead |
| R-012 | Fees are set without validating operating cost or access policy | Medium | Medium | Confirm unit economics, concessions and human approval policy | Product and operations owner |

## 2. Open owner decisions

| ID | Decision | Why it matters | Suggested owner action |
|---|---|---|---|
| D-001 | Public service name and brand naming | Repository name and participant facing name may differ | Confirm final public naming and usage |
| D-002 | Assessment snapshot contract | Milestone 4 input integrity | Review and approve versioned contract |
| D-003 | Career snapshot contract | Recommendation reproducibility | Review and approve versioned contract |
| D-004 | Career taxonomy granularity for Pakistan | Candidate quality and explainability | Approve taxonomy scope for first pilot |
| D-005 | Minimum evidence and review thresholds | Prevent false confidence | Approve with research and reviewer input |
| D-006 | Practical experiment rubric | Task quality affects evidence validity | Approve first experiment families and scoring rules |
| D-007 | Minor age threshold and guardian verification | Live minor participation is blocked | Obtain legal review and approve policy |
| D-008 | Guardian information sharing | Participant privacy and trust | Define participant and guardian views |
| D-009 | Safeguarding owner and escalation | Safety response must be staffed | Name responsible person and procedure |
| D-010 | Retention and deletion schedule | Data lifecycle and legal obligations | Approve per data class |
| D-011 | Production authentication and staff roles | Sensitive data access | Approve roles, MFA and access review |
| D-012 | WhatsApp account and provider | Integration cannot be completed without it | Confirm account, number and integration path |
| D-013 | AI and speech provider terms | Data exposure and quality | Review provider terms and permitted data |
| D-014 | Fees, concessions and payment methods | Access and financial operations | Confirm policy and reconciliation |
| D-015 | First pilot cohort and success criteria | Determines whether the method works | Define cohort, reviewer capacity and measurable outcomes |
| D-016 | VPS, backups and recovery objectives | Production operation | Select provider and approve recovery requirements |

## 3. Research required

- Validated assessment instruments that can be lawfully adapted.
- Urdu cognitive and cultural validation.
- Age appropriate methods for Grade 8 participants.
- Pakistan career taxonomy and education pathway sources.
- Salary and labour demand sources with dates and geography.
- Fairness of practical tasks across language, gender and device access.
- Voice transcription quality for Pakistani Urdu and code switching.
- Applicable legal requirements for minors, privacy, consumer payments and messaging.

Do not turn these into assumed facts. Record source, access date, methodology, limitations and product implication.

## 4. Decision record template

For each approved decision, record:
- Decision ID and date.
- Decision owner.
- Context and options considered.
- Selected option.
- Rationale and evidence.
- Consequences and tradeoffs.
- Affected requirements and documents.
- Review trigger or expiry.

## 5. Release blockers

The following remain blockers for real participant operation: minor and guardian policy, safeguarding playbook and staffing, production privacy and encryption, retention and deletion, production operator authentication and RBAC, validated assessment and Urdu adaptation, confidence calibration, approved Pakistan career content, fee/payment rules, WhatsApp provider and pilot readiness.

Do not bypass a blocker because a prototype appears complete.
