# GitHub Defaults

This repository centralizes GitHub defaults for repositories under `colin-tndof`.

Use it for shared community health files, issue and pull request templates, organization profile content, and reusable workflow templates. Repository-specific files always take precedence over the defaults here.

## What This Provides

| Path | Purpose |
| --- | --- |
| [profile/README.md](profile/README.md) | Public organization profile content |
| [CONTRIBUTING.md](CONTRIBUTING.md) | Default contribution guide |
| [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) | Default participation expectations |
| [SECURITY.md](SECURITY.md) | Default vulnerability reporting guidance |
| [SUPPORT.md](SUPPORT.md) | Default support and contact guidance |
| [GOVERNANCE.md](GOVERNANCE.md) | Default project stewardship notes |
| [.github/ISSUE_TEMPLATE](.github/ISSUE_TEMPLATE) | Default issue forms |
| [.github/PULL_REQUEST_TEMPLATE.md](.github/PULL_REQUEST_TEMPLATE.md) | Default pull request template |
| [workflow-templates](workflow-templates) | GitHub Actions workflow templates |

## How Defaults Work

GitHub uses these files for repositories that do not define their own versions. If a repository needs different instructions, add the file directly to that repository and GitHub will use the repo-local version.

Good candidates for repo-local overrides:

- Project-specific setup steps.
- Sensitive data handling rules.
- Deployment or operational procedures.
- Custom issue labels, owners, or review requirements.

## Profile README Note

The public profile shown for an organization comes from [profile/README.md](profile/README.md) in this repository.

For a personal GitHub profile README, create a separate public repository named exactly `colin-tndof` and put a root `README.md` there.
