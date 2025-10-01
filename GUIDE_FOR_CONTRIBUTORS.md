# Contribution Guidelines for NysaClan Projects

This document defines how contributions are made across all repositories under the `nysa-garage` GitHub organization.  
It applies to both internal and external collaborators where access is granted.


## Principles

- Follow the **GitFlow branching model** for all repositories.  
- Contributions must be traceable, reviewable, and testable.  
- Security, reliability, and maintainability are priorities.  
- CI/CD pipelines enforce standards; contributions must pass before merge.


## Git Strategy

We use **GitFlow** across all projects.

### Branch Types
- **main** — Always production-ready. Every commit here is deployable.  
- **develop** — Integration branch. Features and fixes are merged here before release.  
- **feature/*** — For new features. Branch off `develop`.  
- **bugfix/*** — Small fixes branched from `develop`.  
- **hotfix/*** — Urgent fixes branched from `main`, merged back into both `main` and `develop`.  
- **release/*** — Preparation for a release; branched from `develop`, merged into both `main` and `develop`.  

### Workflow
1. Branch from `develop` (or `main` for hotfixes).  
2. Make commits with clear messages.  
3. Open a Pull Request into the correct target branch.  
4. After approval and CI/CD checks, merge using **squash and merge**.


## Branch Naming

Branches must follow this convention:


Examples:
- feature/navan/update-arc-reactor
- bugfix/anita/fix-login-race
- hotfix/team/rollback-api-endpoint
- release/1.2.0


## Commit Messages

Commit messages should follow this format:


Examples:
- feature: add arc reactor module  
- fix: correct null pointer in auth service  
- docs: update API usage instructions


## Code Review

All code changes must go through **Pull Requests**.

### PR Guidelines
- Reference the Issue being resolved.  
- Keep PRs small and focused(no commits with more than 300 lines of code won't be merged)
- Add/update documentation and tests where relevant.  
- Include context on *why* changes were made, not just *what*.  

### Review Expectations
- At least one reviewer must approve before merge.  
- Reviews check for:
  - Code correctness and maintainability  
  - Security and reliability  
  - Alignment with style guides and architecture principles  
- Suggested changes must be addressed before approval.


## CI/CD ( if any)

in some projects we enforece CI/CD pipelines.

### Continuous Integration (CI)
- Linting, formatting, and static analysis must pass.  
- Unit and integration tests must run and succeed.  
- Security scans may be enforced depending on repo.  

### Continuous Delivery/Deployment (CD)
- Merges to `develop` trigger staging builds/deployments.  
- Merges to `main` trigger production deployments.  
- Release branches are tested, tagged, and merged into both `main` and `develop`.  

### Failure Policy
- PRs cannot be merged if CI fails.  
- Hotfixes follow the same checks but may be expedited with maintainer approval.


## Scope of Contributions

Contributions typically include:
- Code (features, fixes, refactors)  
- Documentation (setup, APIs, onboarding)  
- CI/CD improvements (workflows, automation, observability)  
- Updates to standards or security practices  

---

## Alignment

All contributions must align with:
- The [NysaClan Developer Handbook](./README.md)  
- Project-specific rules defined in individual repos  

---

This process ensures consistency across NysaClan projects and protects production stability.  
Repositories may extend these rules, but never relax them.



