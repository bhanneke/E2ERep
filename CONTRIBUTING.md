# Contributing to E2ERep

Thank you for your interest in improving E2ERep. Contributions are welcome across all areas: pipeline stages, data source coverage, documentation, and reproducibility methodology.

## What we welcome

- **Bug reports** — reproducible issues with specific papers or datasets
- **Methodology improvements** — better stage designs or comparison algorithms
- **Data source coverage** — new dataset repositories, journal data archives
- **Documentation** — setup instructions, worked examples, stage documentation

## Before you start

For anything beyond a trivial fix, open an issue first to discuss the approach. This saves time if a proposed change doesn't fit the project's direction.

## How to contribute

1. Fork the repository
2. Create a branch (`git checkout -b feat/your-change`)
3. Make your changes with clear, focused commits
4. Ensure your change doesn't embed API keys or credentials in any form
5. Open a pull request against `main` with a description of what changed and why

## Pipeline stage conventions

Each stage lives in `stages/<n>_<name>/`. Stages must:
- Accept structured JSON input from the prior stage
- Write structured JSON output consumed by the next stage
- Be independently testable with a fixture input
- Log decisions at INFO level (not DEBUG by default)

## Reporting security issues

Do **not** open public issues for security vulnerabilities. Email security@redo.rocks instead.

## License

By contributing, you agree your contributions are licensed under Apache 2.0, the same as the project.
