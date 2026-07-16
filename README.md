# ai-inference-platform

> Enterprise-grade AI model serving platform — multi-environment AWS infrastructure built with Terraform.

This repository is a hands-on Terraform learning project structured around a real-world AI product infrastructure use case. It is built incrementally across 8 phases, each representing a distinct infrastructure concern that any production AI team would own.

---

## What We Are Building

A multi-environment (dev / staging / prod) cloud platform that hosts an AI inference API. All infrastructure is managed as Terraform code targeting AWS — running locally via **MiniStack** (LocalStack-compatible AWS simulator).

### Architecture Overview

```
┌─────────────────────────────────────────────────────┐
│                   AI Inference Platform              │
│                                                     │
│  ┌──────────┐   ┌──────────┐   ┌─────────────────┐ │
│  │  dev env │   │ staging  │   │   prod env      │ │
│  └──────────┘   └──────────┘   └─────────────────┘ │
│                                                     │
│  Networking → Compute → Storage → Security          │
│  Observability → CI/CD → Cost Governance            │
└─────────────────────────────────────────────────────┘
```

---

## Project Phases

| Phase | Title | Focus |
|---|---|---|
| 1 | Foundation | Remote state, locking, provider config, folder structure |
| 2 | Networking | VPC, subnets, route tables, NAT, security groups |
| 3 | Compute | EC2/ECS cluster, launch templates, autoscaling |
| 4 | Storage | S3 buckets, policies, lifecycle rules |
| 5 | Security | IAM roles, instance profiles, KMS, secrets |
| 6 | Observability | CloudWatch logs, metrics, alarms, dashboards |
| 7 | CI/CD Integration | Pipeline backend, plan output as PR artefact |
| 8 | Cost & Governance | Tagging strategy, budget alarms |

---

## Local Development

This project uses **MiniStack** as a local AWS simulator. See [`LOCALSTACK_NOTES.md`](./LOCALSTACK_NOTES.md) for known behavioural differences between MiniStack and real AWS.

---

## Standards

- All resources must be tagged with: `Environment`, `Project`, `Owner`, `ManagedBy=terraform`
- No credentials or `.tfstate` files are ever committed
- Each phase is reviewed via a Pull Request before merging
- IAM follows least-privilege — every `*` must be justified in a comment
