# Participant and Operator Journeys

## Journey design principles

The journey adapts to education stage, experience, language and needs. It must not assume that every participant knows their interests or preferred career. It must not treat a fixed age band as the only audience definition.

The journeys below describe the intended product experience. Only the data foundation and portions of the assessment and career reference layers are currently implemented. Participant facing screens, WhatsApp operation, recommendations, experiments and production human operations remain future work.

## 1. New participant

1. Discover GROW through an approved referral or public information channel.
2. Receive a plain language explanation of purpose, limits, data use and expected effort.
3. Choose a language and interaction mode when supported.
4. Provide minimum context needed for the journey.
5. Complete applicable consent steps.
6. If minor status or guardian handling applies, pause until the approved guardian policy is satisfied.
7. Begin open discovery.
8. Continue into structured assessment and practical exploration.
9. Review evidence and emerging patterns.
10. Receive explainable guidance after required review.
11. Agree on a next action and follow up plan.
12. Pause, resume, complete or opt out.

## 2. School discovery: Grade 8 to Grade 10

Primary need: explore interests and developing abilities before subject or stream choices.

Experience requirements:
- Use age appropriate, concrete Urdu language.
- Avoid pressure to choose a permanent career.
- Use examples from school, home, hobbies and everyday problem solving.
- Provide short, phone friendly tasks.
- Explain that interests and abilities can develop.
- Involve a guardian only under a confirmed consent and safeguarding policy.
- Preserve the participant voice when family preferences differ.

The product should return exploration directions and next experiments, not a deterministic career verdict.

## 3. College direction: Intermediate, A Levels and diploma

Primary need: compare degrees, skills and training routes.

Experience requirements:
- Connect interests and evidence to multiple plausible fields.
- Explain admission prerequisites and route differences.
- Show time, cost and location constraints separately from capability.
- Identify what should be tested before a major admission decision.
- Do not invent current admission or labour market data.

## 4. University and graduate direction

Primary need: connect education and demonstrated interests to realistic entry routes.

Experience requirements:
- Capture existing projects, coursework, internships and transferable skills.
- Identify gaps without treating them as fixed inability.
- Compare entry roles, further education and skill routes.
- Show source dates for market information.
- Recommend low cost experiments before expensive commitments.

## 5. Adult career reset

Primary need: explore a better direction without ignoring current responsibilities.

Experience requirements:
- Capture current role, transferable skills, income dependency, time and retraining constraints.
- Distinguish dissatisfaction with a workplace from mismatch with an occupation.
- Compare transition paths with different levels of risk.
- Do not recommend quitting employment as a default action.
- Show what can be tested while preserving current income.

## 6. Guardian journey

Intended responsibilities:
- Understand the service and its limitations.
- Provide required consent where applicable.
- Understand what information may be shared and what remains private.
- Receive a clear escalation route for safeguarding concerns.
- Support practical decisions without replacing the participant voice.

Guardian identity verification, legal consent rules, data sharing boundaries and conflict handling are unresolved and block live minor participation.

## 7. Human reviewer journey

Future workflow:
1. Open assigned review case.
2. Confirm participant stage and consent status.
3. Inspect source evidence, confidence, missing dimensions and contradictions.
4. Review practical experiment submissions when available.
5. Inspect candidate directions and feasibility constraints.
6. Record approve, return for more evidence, escalate or override.
7. Provide a reason and retain the original system output.
8. Ensure the participant receives only an approved explanation.
9. Schedule or record follow up.

Reviewer authentication, roles, queue, case assignment and production UI are not implemented.

## 8. Career content editor journey

1. Prepare a source backed career update.
2. Identify geography, source date, methodology and limitations.
3. Submit a staged import.
4. Inspect new, changed and removed records.
5. Request human review.
6. Approve or reject with reason.
7. Publish a new immutable version.
8. Monitor freshness and expiry.

The registry and staged import contracts exist. Real research operations and approved Pakistan career content remain incomplete.

## 9. Pause, opt out and safeguarding states

The journey must make pause and opt out understandable and easy to execute. A safeguarding concern must move to a staffed human process, not an automated career recommendation. The operational playbook, staffing, response time and escalation contacts must be approved before live operation.

## 10. Journey completion

Completion should not mean that the system has assigned a career. It should mean the participant has a documented current understanding, an explainable set of options or an explicit statement that more evidence is needed, and a reasonable next step. Guidance can be revised as new evidence appears.
