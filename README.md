# Distributed Container Orchestrator

`orch` is a Docker-first control plane for small clusters. It includes a server, worker agents, a CLI, scheduling and reconciliation logic, rollouts, and operational tooling.

**Repository:** [miriyala1818/Distributed-Container-Orchestrator](https://github.com/miriyala1818/Distributed-Container-Orchestrator)

[![CI](https://github.com/miriyala1818/Distributed-Container-Orchestrator/actions/workflows/ci.yml/badge.svg)](https://github.com/miriyala1818/Distributed-Container-Orchestrator/actions/workflows/ci.yml)

## Project status

This is an MVP. The local development control plane is in-memory; although database migrations and a PostgreSQL store exist, production database wiring and restart-safe state are not complete. Review the current boundaries before relying on it in a deployment.

## Requirements

- Go 1.25 or newer
- Docker Engine and Docker Compose v2
- Bash, `curl`, and permission to access the Docker Engine

## Quick start

```sh
git clone https://github.com/miriyala1818/Distributed-Container-Orchestrator.git
cd Distributed-Container-Orchestrator
./scripts/dev-up.sh
./scripts/migrate-up.sh
```

Configure the CLI to use the local server:

```sh
export ORCH_SERVER_URL=http://localhost:8080
orch node ls
```

