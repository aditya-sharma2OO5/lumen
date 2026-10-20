# Contributing to Lumen

Thank you for your interest in contributing to Lumen! This document outlines the development workflow, setup process, and commit conventions required for this project.

## Local Setup

Lumen is primarily a Python-based project (AWS Lambda, Strands Agents, PySpark ETL). To set up your local environment:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/lumen.git
   cd lumen
   ```

2. **Set up a Python Virtual Environment:**
   Always use a virtual environment to isolate dependencies.
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install Dependencies and Pre-commit Hooks:**
   We use `pre-commit` to enforce formatting (`black`) and linting (`ruff` or `flake8`) before every commit.
   ```bash
   pip install -r requirements.txt
   pre-commit install
   ```

## AWS Credentials & Security (CRITICAL)

Lumen interacts heavily with AWS. **Never commit AWS credentials to this repository.**
* Do not commit `.env` files.
* Do not commit `*.pem` or `.csv` files containing access keys.
* The `.gitignore` is configured to catch these, but always review your staging area.
* For local development, rely on `aws configure sso` or local `~/.aws/credentials` profiles outside the project directory.

## Commit Conventions

We strictly follow [Conventional Commits](https://www.conventionalcommits.org/). This allows us to auto-generate our changelog and maintain a readable history.

Please prefix your commit messages with one of the following:
* `feat:` A new feature (e.g., `feat: add Bedrock Vision fast-path router`)
* `fix:` A bug fix (e.g., `fix: resolve DynamoDB TTL deletion latency`)
* `docs:` Documentation only changes
* `chore:` Routine tasks, dependency updates, or infra changes (e.g., `chore: update Terraform AWS provider`)
* `test:` Adding missing tests or correcting existing tests
* `refactor:` Code changes that neither fix a bug nor add a feature

## Pull Request Process

1. Create a feature branch from `main`.
2. Ensure your code passes all `pre-commit` checks and `pytest` suites.
3. Open a Pull Request.
4. `main` is a protected branch. Even if you are the sole developer, open a PR and let the GitHub Actions CI pipeline (linting, tests, Trivy scans) pass before merging.