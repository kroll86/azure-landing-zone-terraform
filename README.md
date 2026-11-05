# Azure Landing Zone — Terraform

[![terraform-ci](https://github.com/kroll86/azure-landing-zone-terraform/actions/workflows/terraform-ci.yml/badge.svg)](https://github.com/kroll86/azure-landing-zone-terraform/actions/workflows/terraform-ci.yml)
![Terraform](https://img.shields.io/badge/terraform-~%3E1.17-7B42BC)
![License](https://img.shields.io/badge/license-MIT-blue)

Opinionated Azure Landing Zone built with Terraform — management groups,
policy, network, identity and monitoring as code. Designed for small teams:
few moving parts, everything delivered through a pipeline, security and cost
guardrails on by default.

> **Status:** early development. Only what is marked ✅ exists and runs.

## What's included

- 🚧 Remote state backend (Entra ID auth, no access keys)
- 📋 Management group hierarchy
- 📋 Governance: Azure Policy, tags, cost guardrails
- 📋 CI/CD with GitHub Actions + OIDC (no secrets)
- 📋 Hub-and-spoke network, Private DNS, private endpoints
- 📋 Identity: RBAC, managed identities, PIM
- 📋 Monitoring: Log Analytics, diagnostic settings, alerts, budgets

✅ done · 🚧 in progress · 📋 planned

## Project structure

```text
.
├── bootstrap/          # remote state backend (local state first, then migrated)
├── modules/            # reusable modules
├── environments/
│   ├── dev/            # root module per environment, own state file
│   └── prod/
├── docs/adr/           # architecture decision records
└── .github/workflows/  # CI/CD
```

## Prerequisites

- Terraform ~> 1.17, Azure CLI, an Azure subscription
- Or just open a GitHub Codespace: the devcontainer installs everything

## Design decisions

Every non-obvious choice is recorded as an ADR in [`docs/adr`](docs/adr).

## Author

Guilherme Kroll de Lima — [LinkedIn](https://www.linkedin.com/in/guilherme-kroll-de-lima/)
