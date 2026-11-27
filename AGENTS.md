# AGENTS.md — Operating Rules for `zakshub/grow-prod`

> **Governance & Access Note:** This is a **public** repository. Public contributors should follow this `AGENTS.md`, `README.md`, and `docs/`. Internal maintainer governance and portfolio tracking follow the owner's **private** `zakshub/project-os` repository (`antigravity/OPERATING_INSTRUCTIONS.md`) and **private** `Zakshub Portfolio` board (owner access only).

---

## 1. Repository Identity & Strict Authority Boundaries
- **Purpose:** Working production repository for all new **GROW** career discovery deliverables, specifications, designs, prototypes, implementation, and developer handoff material.
- **Classification:** Active Substantial Product
- **Default Branch:** `main` (use short-lived feature branches + Pull Requests; never rewrite history)
- **Strict Source-of-Truth Protection:** **`zakshub/grow` is a protected, read-only source-of-truth baseline.** Never modify `zakshub/grow` without Zak's explicit separate approval. All new GROW work belongs here in `zakshub/grow-prod`.
- **Privacy & Synthetic Data Rule:** Use synthetic fixtures only. Never commit real participant data, real conversations, personal contact details, credentials, or private records.
- **Identity & Status Discipline:** Never fabricate or redraw the approved GROW logo. Label every capability honestly (`Implemented`, `Partially implemented`, `Planned`, `Proposed`, `Blocked`, `Unknown`, `Retired`).

## 2. Mandatory Reading Order
1. [README.md](./README.md)
2. [docs/00_DEVELOPER_HANDOFF_INDEX.md](./docs/00_DEVELOPER_HANDOFF_INDEX.md)
3. [docs/01_PRODUCT_AND_SCOPE.md](./docs/01_PRODUCT_AND_SCOPE.md) and [docs/02_REQUIREMENTS_CATALOGUE.md](./docs/02_REQUIREMENTS_CATALOGUE.md)
4. [docs/03_ARCHITECTURE_AND_DOMAIN_BOUNDARIES.md](./docs/03_ARCHITECTURE_AND_DOMAIN_BOUNDARIES.md) and [docs/05_PRIVACY_SAFETY_AND_OPERATIONS.md](./docs/05_PRIVACY_SAFETY_AND_OPERATIONS.md)
5. [docs/06_ROADMAP_AND_MILESTONES.md](./docs/06_ROADMAP_AND_MILESTONES.md) and [docs/07_RISKS_AND_DECISIONS.md](./docs/07_RISKS_AND_DECISIONS.md)
6. [docs/11_TESTING_AND_RELEASE_GATES.md](./docs/11_TESTING_AND_RELEASE_GATES.md)

## 3. Milestone & Owner Approval Gates
- Check active GitHub Issues (`gh issue list -R zakshub/grow-prod`)—and for the repository owner, the private `Zakshub Portfolio` board—before starting work.
- Do not begin implementation of Milestone 4 or new product features before owner approval of input contracts and acceptance criteria (see issue `#1` and `#2`).

## 4. Design & Visual Intelligence
- **UX/UI decisions:** Consult canonical UX/UI intelligence (`zakshub/designer`, via your configured local intelligence workspace when available) before designing screens or interaction flows.
- **Visual / photographic assets:** Consult canonical visual-production intelligence (`zakshub/studio`, under the Designer–Studio Contract) whenever imagery is required.

## 5. Verification & Safety Rules
- Run documentation/YAML/link checks (`ci.yml`) and any added test suites before opening a Pull Request.
- Never deploy to production, enable paid services, or commit secrets without Zak's explicit approval.
- Never claim completion without verified command output.
