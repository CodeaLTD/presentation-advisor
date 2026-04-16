# Security Policy

## Supported Versions

This project is pre-1.0 and under active development. Security fixes are best-effort on the `main` branch.

## Reporting a Vulnerability

Please do not open public issues for security vulnerabilities.

Use GitHub's private vulnerability reporting for this repository (Security Advisories).

Include:

- Affected component and file path.
- Reproduction steps or proof of concept.
- Expected impact.
- Suggested remediation (if available).

If private reporting is unavailable in your fork, open a draft private advisory in the upstream repository. You can expect an initial acknowledgement within 5 business days.

## Disclosure Process

- We confirm receipt and triage severity.
- We work on a fix and coordinate disclosure timing.
- We publish mitigation guidance once a fix is available.

## Secrets and Sensitive Data

- Never commit credentials, API tokens, private keys, or private datasets.
- Use environment variables and local `.env` files excluded by `.gitignore`.
