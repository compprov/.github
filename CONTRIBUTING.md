# Contributing to compprov

Thank you for your interest in contributing to the compprov framework.
This document covers how to report issues, propose changes, and submit pull requests.

## Code of Conduct

By participating in this project you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md).

## Reporting Issues

Before opening an issue, please search existing issues to avoid duplicates.

**Bug reports** should include:
- A clear and concise description of the problem
- Steps to reproduce the behavior
- Expected vs actual behavior
- Java version and OS

**Feature requests** should describe:
- The problem you are trying to solve
- Your proposed solution or API idea
- Any alternatives you considered

## Development Workflow

1. Fork the repository and create a branch from `main`
2. Branch naming: `feature/short-description`, `fix/short-description`, `docs/short-description`
3. Write code following the project's style (classic Java, thorough Javadoc, no over-engineering)
4. Add or update tests for any behavior change
5. Ensure all tests pass before submitting
6. Open a pull request against `main` with a clear description of the change

## Pull Request Guidelines

- Keep PRs focused — one logical change per PR
- Write a clear PR description explaining the *why*, not just the *what*
- All public classes and methods must have Javadoc
- Do not add speculative features or premature abstractions
- Squash commits if the history is noisy — we merge with squash

## Code Style

- Standard Java conventions (no checkstyle fanatism, but be consistent)
- Javadoc on all public API
- Inline comments for non-obvious logic only
- Prefer clear, explicit code over clever one-liners
- No framework-within-framework designs — keep it simple

## License

By contributing, you agree that your contributions will be licensed under the
[Apache License 2.0](LICENSE).
