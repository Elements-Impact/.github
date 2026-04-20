# Elements Impact — Global GitHub Configuration

Org-wide standards, reusable workflows, and Copilot guidance for Elements Impact repositories — designed for consistency, quality, and sustainability.

## How GitHub uses this repository

This special repository, named `.github`, can provide “default” community health files and the organization profile:

- Organization profile: `profile/README.md` renders on the org page.
- Default community health files (used when a repo doesn’t define its own):
  - `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `SECURITY.md`, `SUPPORT.md`, `pull_request_template.md`, and files in `.github/ISSUE_TEMPLATE/`.
- GitHub Actions workflows are not auto-applied org-wide. To share automation, publish reusable workflows here and reference them from each repository (see “Reusing workflows”).

References: [About default community health files](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file) • [Reusing workflows](https://docs.github.com/en/actions/writing-workflows/reusing-workflows)

## What’s included

- AI-assisted development
  - Global Copilot guidance in `.copilot-instructions.md` (referenced by projects)
  - Organization-wide coding principles with sustainability in mind
- Issue & PR templates
  - Bug/feature/documentation templates with environmental considerations
  - Pull request template with review and sustainability checks
- Community guidelines
  - Contributing guidelines, Code of Conduct, Security policy
- Automation & workflows
  - Reusable CI/CD and auto-assignment workflows (opt-in per repo)
  - Dependabot baseline configuration examples (opt-in per repo)
- Organization profile
  - `profile/README.md` with our mission and links

## Quick start

### For repository maintainers

1. Community health defaults

- If your repo doesn’t define its own templates/policies, GitHub will use the defaults from this `.github` repository automatically.

1. Reusing workflows (recommended)

- Reference shared workflows from your repo’s `.github/workflows/*.yml`:

```yaml
name: CI
on: [push, pull_request]

jobs:
  ci:
    uses: Elements-Impact/.github/.github/workflows/ci-cd.yml@main
    secrets: inherit
    with:
      # Example inputs your reusable workflow may support
      node-version: '20'
```

1. Dependabot

- Copy or adapt the example `dependabot.yml` here and commit it to your repo.

1. Copilot instructions

- In your project, create a `.copilot-instructions.md` that links to the global guidance and adds project-specific rules. Example:

```markdown
# Project-Specific Copilot Instructions

Follow the global instructions: [Elements Impact Copilot](https://github.com/Elements-Impact/.github/blob/main/.copilot-instructions.md)

Additional rules for this project:
- Language/framework specifics
- Architecture patterns
- Sustainability metrics to observe
```

### For contributors

- Review our global Copilot guidance: [Global Instructions](https://github.com/Elements-Impact/.github/blob/main/.copilot-instructions.md)
- Use the issue/PR templates and follow the Contributing guidelines
- Consider environmental impact in design, performance, and infrastructure choices

## Repository layout (current and planned)

Current:

```text
.github/
├── profile/
│   └── README.md     # Organization profile (published on the org page)
└── README.md         # This file
```

Planned additions (examples):

```text
.github/
├── .copilot-instructions.md
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   ├── feature_request.md
│   │   └── documentation.md
│   ├── workflows/
│   │   ├── ci-cd.yml
│   │   └── auto-assign.yml
│   ├── CONTRIBUTING.md
│   ├── CODE_OF_CONDUCT.md
│   ├── SECURITY.md
│   ├── dependabot.yml
│   └── pull_request_template.md
```

Note: Workflows in this repository act as reusable workflows and must be referenced from each repo’s own workflows.

## Quality and sustainability

- Write secure, well-tested code (target high coverage where practical)
- Optimize for performance and resource efficiency
- Support accessibility and internationalization where applicable
- Evaluate environmental impact in architecture and runtime choices

## Contributing to this repository

We welcome improvements to our org-wide configuration:

1. Open an issue describing the change and its org-wide impact
2. Keep backward compatibility when possible
3. Update docs and examples accordingly
4. Submit a PR for review and rollout

## Helpful resources

- [GitHub Organization configuration](https://docs.github.com/en/organizations)
- [GitHub Copilot best practices](https://docs.github.com/en/copilot)
- [Default community health files](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file)
- [Reusing GitHub Actions workflows](https://docs.github.com/en/actions/writing-workflows/reusing-workflows)
- [Principles of Sustainable Software](https://principles.green/)

—

Questions? Open an issue or reach out to the maintainers. Let’s build sustainable technology together. 🌍
