# devops-scripts

## Description

devops-scripts is a comprehensive collection of modular automation scripts designed to simplify and accelerate DevOps workflows. This project provides production-ready, reusable scripts with robust error handling and logging capabilities to automate repetitive tasks across the development lifecycle.

## Features

* **Automated deployment**: Multi-cloud deployment scripts with rollback support (AWS, GCP, Azure)
* **Infrastructure management**: Terraform modules for provisioning cloud resources with drift detection
* **CI/CD pipelines**: Pre-configured Jenkins/GitHub Actions workflows with security scanning
* **Monitoring and observability**: Integrated scripts for Prometheus, Grafana, ELK, and OpenTelemetry
* **Security automation**: CIS benchmark compliance checks, secret scanning, and IAM policy generators
* **Kubernetes operations**: Helm chart templates, cluster scaling, and backup/restore utilities

## Technologies Used

* **Languages**: Python 3.9+, Bash 5.0+, Go 1.18+
* **Cloud**: AWS, GCP, Azure, DigitalOcean
* **Containers**: Docker, Podman, containerd
* **IaC**: Terraform, Pulumi, Crossplane
* **Configuration**: Ansible, SaltStack
* **Monitoring**: Prometheus, Grafana, Loki, Tempo
* **Security**: Trivy, Checkov, OPA Gatekeeper

## Installation

### Prerequisites

- Python 3.9+ with pipx
- Docker Engine 20.10+
- Terraform 1.3+
- Ansible Core 2.12+
- Git 2.35+

### Quick Start

```bash
git clone https://github.com/username/devops-scripts.git --depth 1
cd devops-scripts
python -m pipx install --python python3.9 .
make setup
```

### Advanced Setup

1. Install dependencies:
```bash
brew install terraform ansible docker
pipx install pre-commit
```

2. Configure environment:
```bash
cp .env.example .env
./scripts/setup.sh --configure
```

3. Verify installation:
```bash
./scripts/verify_environment.py
```

## Usage

### Core Commands

```bash
# Infrastructure
./infra/apply.sh --env prod --plan

# Deployments
./deploy/rollout.py --app frontend --version 1.2.0 --canary 10%

# Monitoring
./monitoring/alert_manager.py --setup --slack-webhook $SLACK_URL

# Security
./security/compliance_check.sh --cis-level 2 --report html
```

### Automation Examples

```bash
# Scheduled backup
0 2 * * * /opt/devops-scripts/backup/etcd_backup.sh --retention 7d

# Auto-remediation
./security/auto_remediate.py --finding unauthorized-ports
```

## Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feat/amazing-feature`)
3. Commit changes (`git commit -am 'Add amazing feature'`)
4. Push branch (`git push origin feat/amazing-feature`)
5. Open Pull Request

**Development Requirements:**
- Pre-commit hooks installed (`pre-commit install`)
- All tests passing (`make test`)
- Documentation updated (`./docs/generate_docs.py`)

## License

Apache License 2.0 - See [LICENSE](LICENSE) for details.

## Credits

* [Your Name] - Project Maintainer
* [Contributors](CONTRIBUTORS.md) - Complete list of contributors
* [CNCF](https://cncf.io) - For inspiration and best practices