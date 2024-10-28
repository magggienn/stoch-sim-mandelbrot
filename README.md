# Assignment 1 for Stochastic Simulations

See the [assignment details](https://github.com/magggienn/stoch-sim-mandelbrot/blob/main/Assignment%201%20-%20MANDELBROT.pdf). 

## Getting started

This repository uses _uv_ to manage Python and its dependencies, and _pre-commit_ to run
automatic code linting & formatting, and Jupyter notebook cleanup prior to git commits. More about UV [here](https://docs.astral.sh/uv/guides/projects/).

1. Install [uv](https://github.com/astral-sh/uv)

2. Install the project Python dependencies:

```zsh
uv sync
```

3. Start Jupyter

```zsh
# Jupyter lab
uv run jupyter lab

# Or Jupyter notebook (classic)
uv run jupyter notebook
```

4. Install pre-commit:

```zsh
# We can use uv to install pre-commit!
uv tool install pre-commit --with pre-commit-uv --force-reinstall

# Check that pre-commit installed alright (should say 3.8.0 or similar)
pre-commit --version

# After installing pre-commit, you'll need to initialise it.
# This installs all pre-commit hooks, the scripts which run before a commit.
pre-commit install

# It's a good idea to run pre-commit now on all files.
pre-commit run --all-files
```

## Adding new packages with uv

It's simple to add a Python package to the project with uv using `uv add`.
For instance, to install numpy and scipy, and add them to the dependency graph, run:

```zsh
uv add numpy scipy
```

## Pre-commit hooks

I've included two main pre-commit hooks, which will run before any code is commited, namely:
- [ruff](https://github.com/astral-sh/ruff) to automatically lint and format Python code, and
- [nbstripout](https://github.com/kynan/nbstripout) to remove cell output from Jupyter notebooks checked into git.

These should help to keep code clean, and avoid git conflicts with Jupyter notebooks.
If you've followed the instructions to [install pre-commit with uv](#getting-started), both of these should
just work automatically. We shouldn't need to think about them!
