# Contributing

## Scope

This repository is currently research-heavy. Contributions that improve reproducibility, documentation quality, testing, and safety are preferred.

## Ground Rules

- Keep pull requests focused and small.
- Do not commit secrets, credentials, or private/proprietary data.
- Do not add large binary artifacts unless explicitly required and discussed first.
- Prefer deterministic scripts over ad-hoc notebook-only changes.

## Development Setup

1. Create a virtual environment.
2. Install root dependencies:

   `pip install -r requirements.txt`

3. Install module-specific dependencies when needed:

   `pip install -r models/recommender_system/requirements.txt`

## Branching and Commits

- Use a feature branch from `main`.
- Write clear commit messages that explain why a change is needed.
- Keep unrelated refactors out of feature/fix pull requests.

## Pull Request Checklist

- [ ] Changes are scoped and documented.
- [ ] README/docs updated when behavior or setup changed.
- [ ] No secrets were introduced.
- [ ] Notebook outputs are cleaned when outputs are not required.
- [ ] Basic local validation completed (run scripts/notebooks touched by the change).

## Testing

There is no unified test harness yet. At minimum, validate affected notebooks/scripts locally and include exact commands in the PR description.

## CI notebook format allowlist

CI runs `nbqa black --check` on paths listed in `.ci/notebook-format-check.txt`. Add a notebook path there when you want formatting enforced for it; remove paths you are not ready to enforce yet.

## Code of Conduct

By participating, you agree to follow `CODE_OF_CONDUCT.md`.
