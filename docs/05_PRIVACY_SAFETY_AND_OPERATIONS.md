# Privacy, Safety and Operations

## 1. Release principle

Privacy, consent, minor protection and safeguarding are release requirements, not later polish. The current repository provides domain records and workflow guards, but it does not establish a legally complete or operationally staffed participant service.

Do not onboard real participants until the owner has approved the required policies and the technical controls have been implemented and tested.

## 2. Minors and guardians

The audience includes students who may be minors. Current code can represent guardian relationships and unknown minor status, but it does not implement a production age threshold, legal consent flow, guardian identity verification, guardian communication or data sharing policy.

Required before live minor participation:
- Obtain jurisdiction specific legal review for the operating model.
- Approve age classification and consent rules.
- Define acceptable guardian verification.
- Define participant assent and guardian consent separately.
- Define what information is shared with guardians.
- Define how disagreement between participant and guardian is handled.
- Define safe contact hours and communication channels.
- Define safeguarding escalation and responsible staff.
- Test withdrawal and deletion implications.

The current state machine guardian acknowledgement is a development workflow marker only. It is not legal consent.

## 3. Consent

Consent must be informed, specific, understandable, recorded and revocable. The participant must understand purpose, information collected, use, retention, human review and communication channels.

Required records should include the consent version, purpose, status, time, method and actor. Withdrawal must stop further contact where applicable and trigger the approved data handling process.

The production wording and exact legal flow are unresolved. Do not invent them in code or public copy.

## 4. Data classification

| Class | Examples | Handling |
|---|---|---|
| Public | Published career information, public product pages | May be public after review |
| Internal | Roadmaps, system configuration, non sensitive operations | Restricted team access |
| Personal | Participant profile and education details | Least privilege access and purpose limitation |
| Sensitive | Private conversations, guardian details, financial context, safeguarding records, assessment evidence | Strict access, encryption, retention and audit controls |
| Secret | Credentials, API tokens, signing keys | Secret manager or secure environment, never source control |

GitHub must contain no identifiable participant records, real WhatsApp messages, phone numbers, addresses, guardian details, payment details, voice recordings or sensitive personal histories.

## 5. Security controls required before production

- Production authentication for participants and staff where applicable.
- Role based access control and least privilege.
- MFA for privileged operator accounts.
- Encryption in transit and at rest.
- Field level encryption or equivalent protection for high sensitivity identifiers where justified.
- Secure key management and rotation.
- Access logging and periodic access review.
- CSRF, session, webhook signature and rate limit controls.
- Secure secret injection and environment separation.
- Backup encryption and restore testing.
- Incident response and breach handling.
- Dependency and vulnerability management.
- Database permission controls for append only and publication boundaries.
- Monitoring and alerting for failures and suspicious access.

These are required future controls, not claims about the current deployment.

## 6. Retention and deletion

The current repository records deletion boundaries as an architecture concern, but no approved hard deletion graph or retention executor exists.

The owner and legal reviewer must define retention by data class, including raw messages, voice notes, derived evidence, consent records, payment records, audit records and backups. Define deletion, anonymisation, legal holds, backup expiry and proof of completion.

Do not choose arbitrary retention periods in code.

## 7. AI and speech safety

AI and speech processing are not currently implemented. Before enabling them:
- Approve which data classes may be sent to each provider.
- Minimise and de identify content where possible.
- Review provider retention and training terms.
- Version prompts and structured output schemas.
- Validate outputs against deterministic rules.
- Preserve source evidence and uncertainty.
- Require human review for sensitive or high consequence cases.
- Provide a safe failure path when confidence is low or provider service is unavailable.
- Evaluate Urdu dialect, code switching and transcription error rates.
- Obtain appropriate consent for audio processing and define audio deletion.

AI must not independently make irreversible decisions about minors, approve fee concessions, permanently reject participants or resolve safeguarding cases.

## 8. Human operations

Before a pilot, identify named operational owners for:
- Participant support.
- Minor and guardian handling.
- Safeguarding escalation.
- Career content review.
- Recommendation review.
- Fee and access decisions.
- Privacy requests.
- Security incidents.
- WhatsApp account and message template administration.

Define service hours, escalation thresholds, response expectations, handover and absence coverage. A human review model without available reviewers is not a safety control.

## 9. Fees and access

The source documents describe PKR 500 standard access, PKR 200 reduced access and free access after human review. These values require owner confirmation and operational costing before implementation. No automated poverty classifier is permitted. Eligibility and exceptions require an explicit human decision and reason. Payment collection and reconciliation are not implemented.

## 10. Go live gates

A live pilot is blocked until all P0 controls below pass:
1. Approved participant and guardian consent policy.
2. Staffed safeguarding playbook and escalation.
3. Production authentication, roles and MFA.
4. Approved privacy notice and retention/deletion schedule.
5. Encryption and secret management.
6. Access logging and incident response.
7. Safe opt out and pause workflow.
8. Approved assessment and Urdu validation plan.
9. Human review capacity and decision rubric.
10. Production database, backup and restore test.
11. Verified WhatsApp provider/account and webhook security if WhatsApp is used.
12. Pilot cohort and success criteria approved by the owner.

A synthetic demo or successful CI run does not satisfy these operational gates.
