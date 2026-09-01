# labo-devops

Lab DevOps/DevSecOps personnel — micro-infra d'entreprise sur VirtualBox.

## Objectif

Construire une infrastructure d'entreprise miniature, pilotée **100 % par Git** (Git = source de vérité, rien à la main sur les VMs, une brique validée avant la suivante).

## Architecture cible

| VM | IP (host-only 192.168.56.0/24) | RAM | Rôle |
|---|---|---|---|
| bastion | .10 | 1 Go | Point d'entrée admin |
| gitlab | .11 | 4 Go | GitLab CE (source de vérité CI/CD) |
| app1 | .21 | 2 Go | Application |
| app2 | .22 | 2 Go | Application |
| monitor | .31 | 2 Go | Prometheus / Grafana |

## Roadmap (phases 0-6)

- [ ] Phase 0 : VirtualBox — provisioning des 5 VMs
- [ ] Phase 1 : Durcissement Ansible
- [ ] Phase 2 : Prometheus / Grafana
- [ ] Phase 3 : GitLab CE
- [ ] Phase 4 : Traefik
- [ ] Phase 5 : Trivy / Checkov (sécurité)
- [ ] Phase 6 : Vault / k3s

## Organisation (prévu)

```
labo-devops/
├── ansible/        # playbooks, rôles, inventaires
├── docs/           # notes, procédures, Schémas
├── vagrant/        # Vagrantfiles si provisioning Vagrant
└── README.md
```

## Sécurité

- Commits et tags signés avec GPG (ed25519, clé 9C375FE898788F23)
- Authentification GitHub par clé SSH ed25519 dédiée
- Identité : efoures1@gmail.com
