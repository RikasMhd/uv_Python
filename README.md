# uv-python

A small Python project managed with [uv](https://docs.astral.sh/uv/). It currently
includes a starter command and dependencies for data analysis, visualization,
and machine learning.

## What is uv?

`uv` is a fast Python package and project manager. It can manage Python versions,
create virtual environments, install and update packages, and keep project
dependencies reproducible with a lockfile. In this project:

- `pyproject.toml` describes the project and its direct dependencies.
- `uv.lock` records the resolved dependency versions for repeatable installs.
- `.venv` is the project environment created and managed by uv.

## Install uv

On Windows, install uv from Command Prompt with:

```cmd
winget install --id=astral-sh.uv -e
```

Open a new terminal afterward and check the installation:

```cmd
uv --version
```

See the [official installation guide](https://docs.astral.sh/uv/getting-started/installation/)
for other operating systems and installation methods.

## Set up this project

Clone the repository, change into its folder, and install the project and its
dependencies:

```cmd
git clone https://github.com/RikasMhd/uv_Python.git
cd https://github.com/RikasMhd/uv_Python.git
uv sync
```

`uv sync` creates `.venv` if needed and installs the dependencies from
`pyproject.toml` and `uv.lock`. You usually do not need to activate the
environment when using `uv run`.

## Run the project

Run the configured project command:

```cmd
uv run uv-python
```

The starter command prints `Hello from uv-python!`. You can also run a Python
file in the managed environment with:

```cmd
uv run python path\to\your_script.py
```

To open an interactive Python prompt in the environment:

```cmd
uv run python
```

## Common uv operations

| Operation | Command | Purpose |
|---|---|---|
| Install/synchronize dependencies | `uv sync` | Create or update `.venv` from the project and lockfile |
| Add a dependency | `uv add pandas` | Add a package to `pyproject.toml` and update `uv.lock` |
| Add a development dependency | `uv add --dev pytest` | Add a package used for development or testing |
| Remove a dependency | `uv remove pandas` | Remove a package from the project |
| Update locked versions | `uv lock --upgrade` | Resolve and write newer compatible versions to `uv.lock` |
| Run a command in the environment | `uv run <command>` | Run a command with the project's environment |
| Show dependency tree | `uv tree` | Display installed project dependencies |
| Show uv version | `uv --version` | Check the installed uv version |

After changing dependencies, commit both `pyproject.toml` and `uv.lock` so
others can reproduce the environment. Avoid editing `uv.lock` by hand; use uv
commands to update it.

## Current dependencies

- NumPy
- pandas
- Matplotlib
- Seaborn
- scikit-learn
- python-dotenv

Add or remove packages with `uv add` and `uv remove` so that
`pyproject.toml` and `uv.lock` stay in sync.
