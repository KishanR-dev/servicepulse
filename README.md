# ServicePulse — Transformation Engineering Portfolio Hub

**A Five-Project Journey through the Software Delivery Lifecycle**

Welcome to the **ServicePulse** repository. This repository serves as the central Portfolio Hub for my Transformation Engineering series—building a production-ready operations and engineering quality platform from the ground up.

[![Python 3.12+](https://img.shields.io/badge/python-3.12+-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115-009688.svg)](https://fastapi.tiangolo.com/)
[![Tests](https://img.shields.io/badge/tests-78%20passed-green.svg)](#local-development--quality-commands)
[![Coverage](https://img.shields.io/badge/coverage-95%25-brightgreen.svg)](#local-development--quality-commands)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

🔗 **[Live API Documentation & Demo](https://engineering-quality-cicd-dhlf.onrender.com/docs)**
*(Note: Hosted on Render's free tier. May take 30-50 seconds to spin up from sleep.)*

---

## The 5-Project Portfolio

This portfolio is divided into five distinct projects, moving from core platform development through CI/CD, performance optimization, automated traceability, and finally, unified operational dashboards.

### Projects in this Repository (P1, P3, P4, P5)
This repository contains the release progression for Projects 1, 3, 4, and 5:

| Project | Focus | Status |
|---|---|---|
| **#1 - ServicePulse Core** | **Production Operations & Incidents:** A robust REST API (FastAPI) demonstrating clean architecture, state machines, domain modeling, and observability. | ✅ Released |
| **#3 - Transformation Engineering** | **Concurrency & Scalability:** Profiling bottleneck identification, UUIDv4 performance optimizations, Root Cause Analysis (RCA), and load benchmarking. | ✅ Released |
| **#4 - Requirements Engineering** | **Traceability Framework:** A fully automated mechanism tracing functional requirements through design, codebase functions, and test cases via AST evaluation and Git hooks. | ✅ Released |
| **#5 - Command Center** | **Unified Dashboarding:** A visual Engineering & Operations Command Center (built with Gradio/Hugging Face Spaces) orchestrating metrics and portfolio controls. | ✅ Released |

### The Standalone CI/CD Implementation (P2)
**Project #2 - Engineering Quality & CI/CD** focuses heavily on automated QA, Docker containerization, static analysis (Ruff/Bandit/pip-audit), and GitHub Actions pipelines. 

> 📌 **Note:** Project 2 is structurally managed as a separate initiative. While its artifacts (Dockerfile, `.github/workflows`, `scripts/`) operate on this ServicePulse codebase to provide strict quality gating, P2 acts as an independent continuous delivery wrapper validating the structural integrity of all the projects.

---

## Core Capabilities Developed

Across the five projects, this portfolio showcases:

| Capability | Implementation |
|---|---|
| **Service & Incident Lifecycles** | State machine validation and clear separation of API, Service, Domain, and Repository layers. |
| **Testing & Quality** | 78 deterministic tests covering Unit, API, Integration, Failure, and Regression levels. |
| **Code Coverage** | **94.65%** statement coverage tightly enforced by CI quality gates (`--cov-fail-under=85`). |
| **Security & SAST** | Automated `pip-audit` dependency scanning and `bandit` AST vulnerability checks. |
| **Container & Smoke Testing** | Multi-stage Docker build with a non-root user and automated HTTP test verification. |
| **Pipeline Automation** | GitHub Actions workflows mapping code changes to rigorous static and dynamic confidence evaluations. |
| **Observability** | Structured JSON logging with correlation IDs and integrated Prometheus-compatible metrics. |

---

## Local Development & Quality Commands

A unified task runner reproduces the CI pipeline stages locally:

```bash
# 1. Clone & Setup
git clone https://github.com/KishanR-dev/engineering-quality-cicd.git
cd engineering-quality-cicd/servicepulse

python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements-dev.txt

# 2. Run all quality gates in sequence (full CI reproduction)
python scripts/run_checks.py all

# 3. Start development server
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

*Individual commands (e.g., `python scripts/run_checks.py test`) are also available for linting, security scanning, coverage, and Docker smoke testing.*

---

## Documentation Deep Dives

Explore detailed documentation tracing the evolution of these projects:

| Document | Purpose |
|---|---|
| [architecture.md](servicepulse/docs/architecture.md) | System architecture, layers, and data flow (P1) |
| [testing-strategy.md](servicepulse/docs/testing-strategy.md) | Test hierarchy, isolation, and coverage policy (P1/P2) |
| [traceability-matrix.md](servicepulse/docs/traceability-matrix.md) | Requirement → Implementation → Test CI mapping (P4) |
| [PROJECT3_TRANSFORMATION.md](servicepulse/docs/PROJECT3_TRANSFORMATION.md) | Concurrency RCA and Benchmark metrics (P3) |
| [PROJECT4_REQUIREMENTS_TRACEABILITY.md](servicepulse/docs/PROJECT4_REQUIREMENTS_TRACEABILITY.md) | Requirements Traceability Case Study (P4) |
| [PROJECT5_COMMAND_CENTER.md](servicepulse/docs/PROJECT5_COMMAND_CENTER.md) | Transformation Command Center Overview (P5) |
| [RCA_001_concurrent_id_generation.md](servicepulse/docs/RCA_001_concurrent_id_generation.md) | Resolving UUIDv4 concurrency bottleneck (P3) |

---

## License

MIT License — see [LICENSE](LICENSE) for details.
