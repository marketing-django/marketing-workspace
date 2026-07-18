# Contribution Guidelines

Thank you for considering to help this project.

## Project architecture

Check out the README for more info.

## Development

### Installation

> Requirements: [`uv`](https://github.com/astral-sh/uv), [just](https://github.com/casey/just), [prek](https://prek.j178.dev/)

Clone the repository, configure the git hooks, then initialize with `just init`.

```sh
git clone git@github.com:marketing-django/marketing-workspace.git
cd marketing-workspace/
# Install everything.
just init
```

### Commands

- `just help`: See what commands are available.
- `just init`: Install dependencies and initialise for development.
- `just lint`: Lint the project. Accepts optional paths to scope to, e.g. `just lint draftjs_exporter/dom.py`.
- `just format *paths="."`: Format project files.
- `just build-docs`: Build the documentation.
- `just docs`: Build the documentation and serve it locally.

## Coding style & conventions

We follow [PEP 8](https://peps.python.org/pep-0008/) for Python code style, enforced automatically by `ruff`:

- **Python**: formatted with `ruff format`, linted with `ruff check`. Configuration in `pyproject.toml`.
- **Other files**: formatted with `prettier` (see `prettier.config.js`).
- **Indentation**: 4 spaces, no tabs.
- **Type annotations**: required on all production code, checked by `mypy` with strict settings and by `ty` (experimental).
- **Naming**: `snake_case` for functions, methods, and variables; `PascalCase` for classes; `UPPER_CASE` for constants. Test modules follow `test_*.py`, test functions `test_*`, test classes `Test*`.
- **Performance**: core classes should use `__slots__` to reduce memory overhead.
- **Imports**: organized automatically by `ruff` (isort rules in `pyproject.toml`).
- **Error handling**: use specific exception types; avoid bare `except:` clauses (BLE rules).
- **Comments**: avoid hard-wrapping lines, except at full stops, or other punctuation like commas if must be.

## Documentation

Good documentation helps users and contributors understand the project without reading source code. We aim for docs that are accurate, discoverable, and maintainable.

For prose style, tone, terminology, headings, and linking conventions, follow the [documentation style guide](contributing/style-guide.md).

### Prose documentation

- User-facing docs live in `docs/`; the README is the entry point.
- Keep language concise and in **Sentence case** (no Title Case).
- Follow the [documentation style guide](contributing/style-guide.md) for tone, terminology, headings, and linking conventions.
- Run `just format` before committing so prettier formats Markdown files consistently.

## Pull request workflow

1. Create a branch from `main` with a descriptive name.
2. Make your changes, following the coding style and testing guidelines above.
3. Run `just lint` locally to verify everything passes.
4. Open a pull request with a clear description of what the change does and why. Include relevant test evidence (commands and their output) and links to related issues.
5. CI will run linting (ruff, mypy, ty, prettier). All checks must pass before merging.
6. Squash merge when approved. Keep the commit message concise, in the imperative mood, and using Sentence case (no Title Case).

## Support guidelines

### Static typing

All project code should pass static type checking by [mypy](https://mypy.readthedocs.io/en/latest/index.html), with as strict of a configuration as possible, and tentatively also pass type checks with the [ty](https://docs.astral.sh/ty/) checker.
