# Protocol Roadmap & TODOs

This document outlines the tasks required to fully bootstrap and launch the protocol repository. 

**Priority Levels:**
* **[P0] Critical:** Must be completed before the repository is made public or shared with early adopters.
* **[P1] High:** Essential for accepting community contributions and establishing a standard.
* **[P2] Medium:** Important for developer experience (DX) and tooling.
* **[P3] Low:** Enhancements, automations, and scaling processes.
* **[P4] Backlog:** Long-term goals and "nice-to-haves."

---

## [P0] Critical Setup (Pre-Launch)
- [ ] **[P0]** Update `README.md` with protocol overview and structure.
- [ ] **[P0]** Add the `LICENSE` file (e.g., Apache 2.0 or MIT).
- [ ] **[P0]** Draft the `CODE_OF_CONDUCT.md` to ensure a safe, welcoming environment.
- [ ] **[P0]** Define the initial core protocol specification in `specification/core.md`.
- [ ] **[P0]** Create the initial data schemas (e.g., JSON schemas) in `specification/schemas/`.

## [P1] Governance & Community (Launch Phase)
- [ ] **[P1]** Draft `CONTRIBUTING.md` (environment setup, PR process, commit standards).
- [ ] **[P1]** Draft `GOVERNANCE.md` (online-meetings, decision-making process, roles, voting mechanisms).
- [ ] **[P1]** Add `SECURITY.md` detailing the vulnerability disclosure and patching process.
- [ ] **[P1]** Set up official community channels (e.g., Discord server, Slack workspace, or GitHub Discussions).
- [ ] **[P1]** Create a `MAINTAINERS.md` or an `OWNERS` file listing core teams(protocol-admins, site-maintainers).

## [P2] Developer Experience & Tooling
- [ ] **[P2]** Set up GitHub Issue and Pull Request templates (`.github/ISSUE_TEMPLATE/`, `pull_request_template.md`).
- [ ] **[P2]** Initialize the documentation site framework (e.g., MkDocs, Mintlify, or Docusaurus) in a `/docs` directory.
- [ ] **[P2]** Create a `CHANGELOG.md` file and define the Semantic Versioning (SemVer) strategy for the specification.
- [ ] **[P2]** Establish a formal proposal process for protocol changes (e.g., Architecture Decision Records (ADRs) or Enhancement Proposals).

## [P3] Automation & CI/CD
- [ ] **[P3]** Set up a linter and formatter for markdown and schema files (e.g., Prettier) via GitHub Actions.
- [ ] **[P3]** Create a CI workflow to automatically validate/test the schema files against standard payloads.
- [ ] **[P3]** Add a spell-checker and broken-link checker to the CI pipeline for the `/docs` and `/specification` folders.
- [ ] **[P3]** Set up automated deployment for the documentation site to GitHub Pages or a similar host.

## [P4] Ecosystem Expansion (Long-Term)
- [ ] **[P4]** Design a formal logo and branding assets for the protocol.
- [ ] **[P4]** Set up a custom domain for the official protocol documentation.
- [ ] **[P4]** Develop a reference implementation SDK in Python.
- [ ] **[P4]** Develop a reference implementation SDK in TypeScript/Node.js.
- [ ] **[P4]** Develop a reference implementation SDK in Go.
