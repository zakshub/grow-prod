# GROW Production Workspace

**Purpose:** The working repository for all new GROW deliverables, production implementation, design assets, prototypes, and developer handoff material.

## Repository authority

| Repository | Authority | Rule |
|---|---|---|
| zakshub/grow | Source of truth | Read and verify product intent, existing implementation, architecture, decisions, tests, and history. Do not modify without explicit owner approval. |
| zakshub/grow-prod | Production workspace | Store all new documentation, designs, presentations, prototypes, code, assets, exports, and delivery records. |

The source repository is authoritative for existing GROW facts. This repository is the destination for new work.

## Start here

1. [Developer Handoff Index](docs/00_DEVELOPER_HANDOFF_INDEX.md)
2. [Product and Scope Definition](docs/01_PRODUCT_AND_SCOPE.md)
3. [Requirements Catalogue](docs/02_REQUIREMENTS_CATALOGUE.md)
4. [Architecture and Domain Boundaries](docs/03_ARCHITECTURE_AND_DOMAIN_BOUNDARIES.md)
5. [Participant Journeys](docs/04_PARTICIPANT_JOURNEYS.md)
6. [Privacy, Safety and Operations](docs/05_PRIVACY_SAFETY_AND_OPERATIONS.md)
7. [Roadmap and Milestones](docs/06_ROADMAP_AND_MILESTONES.md)
8. [Risks and Decision Register](docs/07_RISKS_AND_DECISIONS.md)
9. [Developer Onboarding](docs/08_DEVELOPER_ONBOARDING.md)
10. [Source Verification Record](docs/09_SOURCE_VERIFICATION_RECORD.md)

## Status discipline

Every capability must be labelled as one of:

- **Implemented:** verified in source code and tests.
- **Partially implemented:** some code exists, but the end to end capability is incomplete.
- **Planned:** present in approved product or technical plans, not yet implemented.
- **Proposed:** a recommendation awaiting owner approval.
- **Blocked:** must not proceed until named conditions are met.
- **Unknown:** evidence is insufficient to make a claim.

A planning document is not proof of implementation. A model or database table is not proof of a complete user facing feature.

## Design and document direction

The GROW identity supplied by the owner uses a folded geometric G symbol, a dark forest green wordmark, a bright lime accent, and the line Discover • Learn • Build. Do not redraw or alter the approved logo. Exact brand colour values and typography tokens remain to be confirmed from the original brand asset.

For document and interface hierarchy, use the design decision methods in zakshub/designer. Use zakshub/studio only when a task requires visual artwork or image production. Do not claim either repository was used for a task unless its relevant guidance was actually inspected.

## Change control

- Do not modify zakshub/grow as part of ordinary production work.
- Record owner decisions in the decision register before changing product rules.
- Update affected requirements, architecture, roadmap, and implementation status together.
- Keep synthetic fixtures only. Never commit identifiable participant data, real conversations, contact details, credentials, or private records.
- Every delivery must include a verification report and known limitations.

**Documentation baseline:** 25 November 2026  
**Source repository snapshot:** zakshub/grow main, tree SHA 80fb54fdb6bd37848c4f201bdeb643a876ca8e3c  
**Document status:** Initial developer handoff package, pending owner review.
