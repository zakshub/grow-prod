# GROW Production Workspace

**Purpose:** The working repository for all new GROW deliverables, production implementation, design assets, prototypes and developer handoff material.

## Repository authority

| Repository | Authority | Rule |
|---|---|---|
| [zakshub/grow](https://github.com/zakshub/grow) | Source of truth | Read and verify product intent, existing implementation, architecture, decisions, tests and history. Do not modify without explicit owner approval. |
| [zakshub/grow-prod](https://github.com/zakshub/grow-prod) | Production workspace | Store all new documentation, designs, presentations, prototypes, code, assets, exports and delivery records. |

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
11. [Technical Implementation Reference](docs/10_TECHNICAL_IMPLEMENTATION_REFERENCE.md)
12. [Testing and Release Gates](docs/11_TESTING_AND_RELEASE_GATES.md)
13. [Glossary and Traceability](docs/12_GLOSSARY_AND_TRACEABILITY.md)
14. [Architecture and workflow diagrams](docs/diagrams/)

## Status discipline

Every capability must be labelled as one of:

- **Implemented:** verified in source code and relevant tests.
- **Partially implemented:** some code or records exist, but the complete workflow is incomplete.
- **Planned:** included in an approved direction or roadmap, not implemented.
- **Proposed:** a recommendation awaiting owner approval.
- **Blocked:** must not proceed until named conditions are met.
- **Unknown:** evidence is insufficient to make a claim.
- **Retired:** no longer intended.

A planning document is not proof of implementation. A model or database table is not proof of a complete user facing feature.

## Design direction

The approved GROW identity uses a folded geometric G symbol, dark forest green and bright lime green, with the line Discover • Learn • Build. Do not redraw or alter the approved logo. The original logo asset and exact colour/font tokens were not available in the inspected repositories during this documentation pass, so the PDF uses a restrained typographic treatment and does not fabricate a replacement mark.

The document system uses a light, editorial technical-report layout: warm neutral paper, forest-green section hierarchy, restrained lime accents, clear tables, legible body text and diagram-first explanation where useful. The UX method is informed by the inspected Designer decision protocol. Studio was inspected for scope boundaries but not used for image production because this package does not require generated artwork.

## Change control

- Do not modify `zakshub/grow` as part of ordinary production work.
- Record owner decisions in the decision register before changing product rules.
- Update affected requirements, architecture, roadmap and implementation status together.
- Keep synthetic fixtures only. Never commit identifiable participant data, real conversations, contact details, credentials or private records.
- Every delivery must include a verification report and known limitations.

**Documentation baseline:** 25 November 2026  
**Source repository snapshot:** `zakshub/grow` main, tree SHA `80fb54fdb6bd37848c4f201bdeb643a876ca8e3c`  
**Destination snapshot before this update:** `zakshub/grow-prod` main, tree SHA `9e54e2130fc57ad15da81fe7e1ce2b7b9fb52373`  
**Document status:** Expanded developer handoff package, pending owner review.

---

## Project Operating System

For public contributor guidance, local verification commands, and AI assistant rules, see [AGENTS.md](./AGENTS.md) and the repository documentation.  
Internal maintainer governance and portfolio tracking use the owner's private `zakshub/project-os` repository and private `Zakshub Portfolio` board (owner access only).
