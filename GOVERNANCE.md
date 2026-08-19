# Governance

This document defines the general governance model used across AEWhite Devs repositories and development activities.

Repository-specific governance rules may extend these guidelines where necessary.

## Organization Ownership

AEWhite Devs organization owners are responsible for:

* Organization-wide configuration.
* Repository creation and deletion.
* Repository visibility.
* Organization security settings.
* Team structure.
* Organization-level permissions.
* GitHub Apps and integrations.
* Rulesets and protected branches.
* Access to sensitive organizational resources.
* Final escalation of administrative disputes.

Organization ownership should be limited to individuals who require full administrative control.

## Project Management

Project management is responsible for coordinating development activities across AEWhite Devs projects.

Responsibilities may include:

* Roadmap management.
* Prioritization.
* Scope management.
* Milestones and releases.
* Assignment of work.
* Cross-team coordination.
* Risk management.
* Tracking blockers and dependencies.
* Acceptance criteria.
* Release readiness.
* Project documentation.

Project management decisions should consider technical feasibility, business requirements, available resources, risk, and project priorities.

## Technical Ownership

Technical areas may have designated teams or maintainers.

Examples include:

* Backend
* Frontend
* Mobile
* Infrastructure
* QA
* Security

Technical owners are responsible for maintaining quality and consistency within their area.

Responsibilities may include:

* Reviewing Pull Requests.
* Maintaining technical standards.
* Identifying technical risks.
* Reviewing architectural changes.
* Maintaining documentation.
* Supporting contributors.
* Escalating significant issues.

Technical ownership does not automatically grant organization-wide administrative privileges.

## Repository Ownership

Repositories should have clearly defined responsible teams.

Examples:

```text
backend-api        → Backend
client-app         → Mobile
provider-app       → Mobile
business-app       → Mobile
web-app            → Frontend
admin-panel        → Frontend / Backend
infrastructure     → Infrastructure
qa-automation      → QA
docs               → Project Management / Technical Leads
.github            → Organization Administration
```

Repository access should follow the principle of least privilege.

Contributors should receive only the level of access necessary for their responsibilities.

## Decision Making

Decisions should be made at the lowest appropriate level.

### Routine Technical Decisions

Routine implementation decisions may be made by the responsible developer or technical team when they:

* Remain within approved requirements.
* Do not introduce significant architectural changes.
* Do not create substantial operational risk.
* Do not introduce significant new costs.
* Do not affect unrelated systems.

### Significant Technical Decisions

Significant decisions should be reviewed by the appropriate technical owner and project management.

Examples include:

* Major architectural changes.
* New infrastructure platforms.
* New databases or storage technologies.
* Major framework changes.
* Introduction of critical third-party services.
* Breaking API changes.
* Authentication or authorization changes.
* Significant changes to deployment architecture.
* Changes affecting security boundaries.
* Large-scale data migrations.

Important architectural decisions should be documented when appropriate.

## Product Decisions

Product requirements and priorities should be coordinated through project management.

Developers should not introduce major user-facing functionality outside the approved scope without review.

Ideas and improvements are encouraged but should be proposed through the appropriate issue or planning process before significant implementation begins.

## Pull Requests

Protected branches should normally be modified through Pull Requests.

Pull Requests may require:

* Human review.
* Code owner approval.
* Automated tests.
* Security checks.
* Build verification.
* Conversation resolution.
* Additional approvals for sensitive changes.

Repository rulesets define the authoritative merge requirements.

## Review Responsibility

Reviewers are responsible for evaluating changes carefully.

Approval should indicate that the reviewer believes the change:

* Meets its requirements.
* Is technically reasonable.
* Does not introduce known critical defects.
* Meets applicable project standards.
* Has appropriate testing.
* Does not introduce unacceptable security risk.

Reviewers should not approve changes they have not adequately reviewed.

## Emergency Changes

Emergency changes may occasionally require an accelerated process.

Examples include:

* Critical production outages.
* Active security incidents.
* Severe data integrity problems.
* Critical authentication failures.

Emergency changes should:

1. Be limited to the minimum necessary change.
2. Be reviewed whenever reasonably possible.
3. Be documented after deployment.
4. Receive retrospective review.
5. Include follow-up work when necessary.

Emergency procedures must not become a normal development workflow.

## Infrastructure Governance

Infrastructure changes should be controlled and documented.

The Infrastructure team is responsible for areas such as:

* Deployment systems.
* CI/CD.
* Networking.
* Servers.
* Cloud resources.
* Monitoring.
* Backups.
* DNS.
* Infrastructure security.
* Operational reliability.

Critical infrastructure should be reproducible whenever practical.

Important infrastructure knowledge must be documented and must not depend exclusively on a single individual.

## Security Governance

Security-sensitive decisions may require additional review.

Examples include:

* Authentication.
* Authorization.
* Cryptography.
* Secrets management.
* Payment systems.
* Personal data.
* Administrative access.
* Infrastructure exposure.
* External integrations.

Security requirements should not be bypassed solely for convenience or development speed.

Potential vulnerabilities should be handled according to `SECURITY.md`.

## Access Control

Access should follow the principle of least privilege.

AEWhite Devs may restrict:

* Repository administration.
* Repository creation.
* Repository deletion.
* Visibility changes.
* GitHub App installation.
* Team creation.
* CI/CD administration.
* Secrets management.
* Production access.

Access should be reviewed whenever a contributor's responsibilities change.

Access that is no longer required should be removed promptly.

## Documentation

Important decisions should be documented.

Documentation should explain:

* What was decided.
* Why it was decided.
* Significant alternatives considered.
* Important risks or trade-offs.

Architecture Decision Records may be used for significant technical decisions.

Documentation that contains sensitive internal information should be stored in private repositories rather than the public `.github` repository.

## Conflicts and Escalation

Technical disagreements should first be resolved through discussion between the contributors and responsible technical owner.

If agreement cannot be reached, the issue should be escalated to project management.

Organization-wide administrative or governance disputes may be escalated to organization owners.

Decisions should prioritize:

1. Security and data integrity.
2. Product requirements.
3. Reliability.
4. Maintainability.
5. Technical quality.
6. Delivery requirements.
7. Cost and operational impact.

## Changes to Governance

This governance model may evolve as AEWhite Devs grows.

Changes to this document should be reviewed carefully because they may affect organization-wide development practices.

---

© AEWhite Devs
