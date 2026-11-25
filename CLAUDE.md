# Homelab Monitoring

DevOps learning project: monitor the home network and devices on a single-node k3s cluster,
designed to mirror AWS concepts (k3s≈EKS, GHCR≈ECR, Prometheus/Grafana≈CloudWatch, etc.).

## Language
- Always reply to the user in Thai. Keep commands, code, file names and technical terms in English.

## Hard rules
- Budget is 0 baht: free / open-source tools only. Do not suggest paid services.
- Public repo: NEVER write secrets, passwords, tokens, real IPs, MAC addresses or hostnames into committed files.
  Use placeholders (e.g. `192.168.x.x`, `<ROUTER_IP>`) and Sealed Secrets for anything sensitive.
- Homelab must not depend on AWS. AWS (Phase 6) is a throwaway sandbox: Terraform only, destroy the same day.
  Never use EKS, NAT Gateway, unattached Elastic IPs or large instances.
- Only scan / monitor the user's own home network.

## How to help
- Phase 1 (Kubernetes basics): the user types kubectl commands themselves. Explain, don't run.
- Read-only commands (`get`, `describe`, `logs`, `terraform plan`) are fine to run.
- `apply`, `delete`, `destroy`, `helm install/upgrade/uninstall` always need user confirmation.
- From Phase 4 on, changes go through Git + ArgoCD — no manual `kubectl apply`.
- Teach while doing: briefly explain the "why" and the AWS equivalent.

## Layout
- `k8s/` manifests & Helm values (argocd/, monitoring/, apps/, data/)
- `services/lan-scanner/` Python app + Dockerfile + tests
- `terraform/aws-sandbox/` Phase 6 only
- `docs/` architecture, aws-vs-homelab, runbooks/, postmortems/

## Environment
- ASUS TUF laptop, Ubuntu 24.04, 16GB RAM, k3s server (single node). Keep Helm values memory-light.
