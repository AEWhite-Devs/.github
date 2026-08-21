# Contributing to AEWhite Devs

Thank you for contributing to AEWhite Devs projects.

This document defines the general development and contribution standards used across AEWhite Devs repositories.

Repository-specific instructions may override or extend these guidelines when necessary.

## Development Workflow

All development work should follow the standard repository workflow:

1. Determine whether the change requires an Issue or can use a self-contained PR.
2. Create a branch for the work.
3. Implement and test the changes.
4. Push the branch to GitHub.
5. Open a Pull Request.
6. Complete the required reviews and automated checks.
7. Resolve all review comments.
8. Merge only after all requirements have been satisfied.

Direct changes to protected branches are not permitted unless explicitly authorized.

## Issues

An Issue is required for new behavior, bugs that need investigation, security or
data changes, breaking changes, coordinated work, incidents, significant debt,
or anything that needs planning in the organization Project.

A separate Issue may be omitted for a small, low-risk, localized maintenance
change. In that case, the Pull Request is the unit of work and must explain the
problem, scope, validation, risk, and rollback. If the work grows, create an
Issue before continuing.

Issues should include enough information for another contributor to understand:

* What needs to be done.
* Why the change is necessary.
* Expected behavior.
* Relevant context.
* Acceptance criteria when applicable.
* Dependencies or blockers.

Use the appropriate Issue Type:

* `Feature`
* `Task`
* `Bug`

Use a parent Issue with sub-issues for an epic. Use the `security` label with a
Bug or Task for security work until an additional organization type is approved.

When available, also complete the relevant organizational fields such as:

* Priority
* Area
* Effort
* Start date
* Target date
* Release

Security vulnerabilities must not be reported through normal public issues. Follow `SECURITY.md`.

## Branches

Create a dedicated branch for each piece of work.

Recommended naming format:

```text
<type>/<issue-number>-<short-description>
<type>/<short-description>
```

Examples:

```text
feature/142-business-registration
fix/283-payment-validation
task/314-update-api-documentation
security/412-token-validation
refactor/517-provider-service
docs/fix-broken-links
```

Common branch prefixes:

```text
feature/
fix/
task/
security/
refactor/
docs/
test/
chore/
```

Keep branch names:

* Short.
* Descriptive.
* Lowercase.
* Hyphen-separated.
* Related to the corresponding issue whenever possible.

## Protected Branches

The `main` branch represents the protected integration branch of the repository.

Contributors should not push directly to `main`.

Changes should reach `main` through Pull Requests.

Depending on repository configuration, merging may require:

* At least one approval.
* Successful automated tests.
* Successful builds.
* Security checks.
* Code owner approval.
* Resolution of review conversations.
* Signed commits.

Repository rulesets are authoritative when they define stricter requirements.

## Commits

Commits should be clear, focused, and understandable.

Avoid commits such as:

```text
fix
changes
stuff
update
final
final2
works now
```

Prefer descriptions such as:

```text
Add business registration validation
Fix duplicate provider assignment
Improve authentication token refresh handling
Update deployment documentation
```

A commit should ideally represent one logical change.

Avoid combining unrelated modifications into the same commit.

## Commit Messages

Recommended structure:

```text
<type>: <short description>
```

Examples:

```text
feat: add provider availability endpoint
fix: prevent duplicate business registration
docs: document staging deployment process
test: add payment validation tests
refactor: simplify order status handling
security: validate webhook signatures
```

Common types:

```text
feat
fix
docs
test
refactor
security
perf
build
ci
chore
```

Commit messages should be written in English unless a repository explicitly defines otherwise.

## Signed Commits

Repositories may require cryptographically signed commits.

When required, contributors must configure Git to sign commits using an approved mechanism such as:

* SSH signing.
* GPG signing.
* GitHub-supported signing mechanisms.

Do not bypass signing requirements.

## Pull Requests

Every Pull Request should:

* Have a clear title.
* Explain what changed.
* Explain why the change was necessary.
* Reference the relevant Issue when required, or justify why the PR is
  self-contained.
* Describe how the change was tested.
* Identify important risks or limitations.
* Include screenshots or recordings for visual changes when appropriate.
* Mention migrations, configuration changes, or deployment requirements.

Pull Requests should remain focused.

Avoid combining multiple unrelated features or fixes into one PR.

## Draft Pull Requests

Use a Draft Pull Request when:

* Work is still in progress.
* Early feedback is needed.
* The implementation is incomplete.
* Automated checks are expected to fail temporarily.

Convert the PR to ready for review only when the change is reasonably complete.

## Code Review

Code review is part of the development process and should not be treated as a formality.

Reviewers should evaluate:

* Correctness.
* Security.
* Maintainability.
* Architecture.
* Performance.
* Error handling.
* Testing.
* Compatibility.
* Documentation.
* Impact on existing functionality.

Review feedback should remain technical, specific, and constructive.

Authors are expected to address review comments or explain why a suggested change should not be applied.

## Review Approval

An approval means the reviewer believes the change is suitable for integration.

Do not approve Pull Requests that:

* Have not been properly reviewed.
* Contain known critical problems.
* Fail required tests.
* Include unrelated unexplained changes.
* Introduce known security weaknesses.
* Contain secrets or credentials.
* Do not satisfy the requested functionality.

New commits may invalidate previous approvals depending on repository rules.

## Testing

Changes should include appropriate testing.

Depending on the repository, this may include:

* Unit tests.
* Integration tests.
* API tests.
* End-to-end tests.
* UI tests.
* Regression tests.
* Security tests.
* Manual verification.

Bug fixes should include a regression test whenever practical.

Do not remove or weaken tests merely to make a Pull Request pass.

## Automated Checks

Repositories may use GitHub Actions or other CI/CD systems.

Required checks may include:

```text
lint
format
test
build
security
dependency-check
e2e
```

A Pull Request should not be merged while required checks are failing.

If a check is incorrect or unreliable, fix the check rather than bypassing it without justification.

## Code Quality

Contributors should prefer:

* Clear code over clever code.
* Reusable components where appropriate.
* Explicit error handling.
* Small and understandable functions.
* Consistent naming.
* Appropriate abstractions.
* Minimal unnecessary complexity.

Avoid premature optimization and unnecessary architectural complexity.

Do not introduce new dependencies without considering:

* Maintenance status.
* Security.
* Licensing.
* Package size.
* Performance.
* Long-term support.
* Whether the dependency is actually necessary.

## Documentation

Changes that affect architecture, APIs, configuration, deployment, development processes, or user-visible behavior should update the relevant documentation.

Documentation should be updated as part of the same work whenever practical.

A task should not be considered complete when its required documentation is missing.

## Infrastructure Changes

Infrastructure changes require additional care.

Changes involving:

* Production deployments.
* Networking.
* DNS.
* Databases.
* Backups.
* Secrets.
* CI/CD.
* Monitoring.
* Authentication infrastructure.
* Cloud providers.
* Firewalls.

should be documented and reviewed by the appropriate infrastructure owner or team.

Production configuration should be reproducible whenever practical.

Manual changes that cannot be reproduced should be documented immediately.

## Secrets and Credentials

Never commit:

* Passwords.
* API keys.
* Access tokens.
* Private keys.
* Database credentials.
* Authentication secrets.
* Production environment files.
* Recovery codes.

Secrets must be stored using approved secret-management systems.

If a secret is accidentally committed:

1. Treat it as compromised.
2. Notify the appropriate maintainer immediately.
3. Rotate or revoke the secret.
4. Remove it from the repository where appropriate.
5. Document the incident if necessary.

Simply deleting a secret from the latest commit is not sufficient.

## Dependencies

Dependencies should be kept reasonably current.

Before introducing a new dependency, consider:

* Whether it is actively maintained.
* Known vulnerabilities.
* License compatibility.
* Community adoption.
* Long-term maintenance risk.

Major dependency upgrades should be reviewed carefully and tested before production deployment.

## Security

Security is everyone's responsibility.

Contributors should consider:

* Authentication.
* Authorization.
* Input validation.
* Data exposure.
* Injection vulnerabilities.
* Access control.
* Sensitive logging.
* Secrets management.
* Dependency vulnerabilities.
* Abuse and rate limiting.

Security-sensitive changes may require additional review.

See `SECURITY.md` for vulnerability reporting.

## Breaking Changes

Breaking changes must be clearly identified in the Pull Request.

The PR should explain:

* What is breaking.
* Which consumers are affected.
* Migration requirements.
* Deployment considerations.
* Rollback strategy when relevant.

Use the `breaking-change` label when applicable.

## Database Changes

Database migrations should:

* Be reviewed.
* Be reproducible.
* Avoid unnecessary destructive operations.
* Consider rollback requirements.
* Consider existing production data.
* Be tested before production deployment.

Large or destructive migrations require additional planning.

## Generated Code

Generated code should not be manually modified unless explicitly documented.

Changes to generated files should normally originate from their source definitions.

Generated artifacts should only be committed when the repository's workflow requires it.

## AI-Assisted Development

AI tools may be used to support development, review, documentation, testing, or analysis.

The contributor remains responsible for all submitted work.

AI-generated code must be:

* Reviewed.
* Understood.
* Tested.
* Compatible with project standards.
* Free of unauthorized secrets or confidential information.
* Evaluated for security and licensing concerns.

Do not merge code solely because an AI system generated or approved it.

AI review does not replace required human review.

## Confidential Information

Private repository contents and internal project information must remain confidential.

Do not share:

* Private source code.
* Internal documentation.
* Credentials.
* Unreleased features.
* Infrastructure information.
* User data.
* Business information.

outside authorized AEWhite Devs systems or personnel.

## Definition of Done

Work should normally be considered complete only when:

* The required functionality has been implemented.
* Acceptance criteria are satisfied.
* Relevant tests pass.
* Required code review is complete.
* Required documentation is updated.
* No known critical defect remains.
* Security implications have been considered.
* Required CI checks pass.
* The change is ready to be integrated or deployed.

Individual repositories may define additional completion requirements.

## Questions

When requirements are unclear, ask before making significant assumptions.

Technical questions should normally be discussed in the relevant Issue or Pull Request so decisions remain documented.

For general matters:

**[contact@aewhitedevs.com](mailto:contact@aewhitedevs.com)**

For security matters:

**[security@aewhitedevs.com](mailto:security@aewhitedevs.com)**

---

© AEWhite Devs
