# 🏠 homelab-monitoring

Home network & device monitoring on **k3s** — built to learn DevOps with an AWS-equivalent design.

> Status: 🚧 Phase 0 — setting up

## Goals
- Know immediately when the internet is slow/down, disks are filling up, the machine is overheating, or an unknown device joins the network
- Practice Kubernetes, Helm, GitOps (ArgoCD), CI/CD and observability
- Total cost: **0 THB** — free & open-source only

## Stack (homelab → AWS equivalent)
| Homelab | AWS |
|---|---|
| k3s | EKS |
| Traefik Ingress | ALB |
| GHCR | ECR |
| Garage / SeaweedFS | S3 |
| PostgreSQL (StatefulSet) | RDS |
| Prometheus + Grafana | CloudWatch Metrics |
| Loki | CloudWatch Logs |
| Alertmanager → Discord/Telegram | CloudWatch Alarms + SNS |
| Sealed Secrets | Secrets Manager |
| Namespace + RBAC | IAM |
| NetworkPolicy | Security Group |

## Roadmap
- [ ] Phase 0 — Repo & AWS fundamentals
- [ ] Phase 1 — Kubernetes basics on k3s
- [ ] Phase 2 — Monitoring stack with Helm
- [ ] Phase 3 — Custom service: LAN scanner
- [ ] Phase 4 — CI/CD + GitOps
- [ ] Phase 5 — Logs, security, backup & restore
- [ ] Phase 6 — AWS sandbox with Terraform (optional)

## Repo layout
```
docs/        architecture, runbooks, postmortems
k8s/         manifests & Helm values
services/    custom apps (lan-scanner)
terraform/   AWS sandbox (Phase 6)
```
