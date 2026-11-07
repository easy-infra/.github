<p align="center">
  <img src="logo.png" alt="easy-infra logo" width="160">
</p>

<h1 align="center">easy-infra</h1>

<p align="center">
  <b>Ready-made, standardized AWS architectures for small and medium businesses.</b><br>
  In your own AWS account, from a few form fields or a chat with an AI assistant.<br>
  No infrastructure-as-code to learn. No DevOps team needed.
</p>

---

## Why

Small companies need the same basic infrastructure as everyone else: a website, a database, somewhere to run an app, a domain.
Setting up AWS *the right way* (networking, permissions, TLS, backups, sensible costs) takes expertise they usually don't have.
Tools like Terraform or Pulumi are powerful, but they are built for platform teams.

**Most SMB needs fit a handful of standard patterns.** easy-infra packages those patterns behind a simple, well-documented web app.

## How it works

1. **Sign in** to the web app.
2. **Connect your AWS account** with a guided, one-click IAM role. No long-lived keys.
3. **Pick an architecture** from the catalog, or ask the assistant which one fits.
4. **Fill in a few fields**: a name, a size (`small` / `medium` / `large`) and, when needed, a domain.
5. **Follow progress** on the dashboard: status, outputs (URLs, endpoints) and clear error messages with a link to the right guide.

Everything is created in **your** AWS account, and every account gets a budget with alerts from day one.

## Principles

- **Standard over custom.** A few opinionated architectures, not a generic IaC tool.
- **The simplest architecture that works.** Monoliths and modular monoliths first.
- **Lowest possible cost.** The estimated monthly cost is shown before anything is created.
- **Few inputs.** At most 5 required fields per architecture; everything else has safe defaults.
- **Secure by default.** TLS, encryption at rest, least-privilege IAM and backups are on.
- **Guided at every step.** Documentation is part of the product.
- **Budget protection by default.** Spending alerts are always on and always visible.

## Catalog

| Architecture | AWS services | Available |
| --- | --- | --- |
| Static site | S3 + CloudFront | Beta |
| Storage bucket | S3 | Beta |
| Public database | RDS PostgreSQL (IP allowlist, TLS) | Beta |
| Domain + site | Route 53 + ACM | v1.0 |
| Monolith app | ECR, ECS Fargate, ALB, API Gateway, RDS | v1.0 |

## Under the hood

```
React web app ──► Backend API (Java, Spring Boot) ──► Kubernetes controller (Go) ──Pulumi──► your AWS account
                         ├─► Amazon Cognito (login)
                         └─► Claude API (assistant)
```

| Repository | What it is |
| --- | --- |
| [`easy-infra-web`](https://github.com/easy-infra/easy-infra-web) | Web app (React, TypeScript, Vite) |
| [`easy-infra-api`](https://github.com/easy-infra/easy-infra-api) | Backend API (Java 25, Spring Boot, Spring Modulith) |
| [`easy-infra-builder-k8s`](https://github.com/easy-infra/easy-infra-builder-k8s) | Provisioning engine (Go, Kubebuilder, Pulumi Automation API) |
| [`easy-infra-docs`](https://github.com/easy-infra/easy-infra-docs) | Customer documentation (Markdown) |
| [`easy-infra-project`](https://github.com/easy-infra/easy-infra-project) | Project hub: scope, roadmap and decisions (ADRs) |

## Roadmap

| Milestone | Date |
| --- | --- |
| Closed beta (invited users) | 30/11/2026 |
| v1.0 | 21/12/2026 |

---

<p align="center"><sub>easy-infra · AWS infrastructure without the DevOps team</sub></p>
