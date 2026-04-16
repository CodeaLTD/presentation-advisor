## Presentation Advisor

Research-focused repository for machine-learning components related to presentation analysis and recommendation.

Current state: this repository is in active development and includes notebooks, experiments, and datasets. It is not yet a stable package release.

## Supported Scope

- **Supported now:** research notebooks, exploratory model experiments, and local reproducibility improvements.
- **Partially supported:** containerized serving experiments in `models/recommender_system`.
- **Not supported as stable API:** production-grade SDK/library contracts, backward compatibility guarantees, or long-term model serving SLAs.
- **Contribution target:** prioritize reproducibility, data hygiene, and documentation over feature expansion.

## Repository Layout

- `models/recommender_system`: recommendation experiments, notebooks, Docker and monitoring assets.
- `models/presentation_checker`: slide/presentation-checking experiments and supporting data.
- `models/pstyle_checker`: style-checking experiments.
- `.github/workflows`: CI workflow definitions.

## Prerequisites

- Python 3.10+
- pip
- Docker (optional, for serving/CI experiments)

## Quick Start

1. Create and activate a Python virtual environment.
2. Install dependencies:

   `pip install -r requirements.txt`

3. For recommender-system notebook work:

   `pip install -r models/recommender_system/requirements.txt`

4. Open notebooks under `models/*/notebooks` and run experiments.

## Reproducibility Notes

- This repository currently contains large data and notebook artifacts.
- Results may depend on local GPU/CPU environment and package versions.
- Prefer pinning environments and recording exact dataset sources for published benchmarks.

## CI/CD

- Active CI workflow: `.github/workflows/recommender_system.yml`.
- Notebook Black checks use the allowlist `.ci/notebook-format-check.txt`.
- Legacy `.txt` workflow files are templates/reference artifacts and are not executed by GitHub Actions.

## Security and Responsible Use

- Do not commit credentials, API keys, or private datasets.
- Report vulnerabilities using the process documented in `SECURITY.md`.

## Contributing

See `CONTRIBUTING.md` for development workflow and pull-request expectations.

## License

This project is licensed under the MIT License. See `LICENSE`.
