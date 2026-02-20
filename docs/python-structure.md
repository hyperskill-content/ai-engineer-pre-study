# Python Project Structure Basics

Python projects typically follow a conventional structure that separates source code, tests, configuration, and documentation.

A typical project contains a root directory with your project name, a `src/` or package directory for your application code, a `tests/` directory for test files, and configuration files at the root level.

You'll see two common patterns: either a `src/` directory containing your package (e.g., `src/myproject/`), or the package directly in the root (e.g., `myproject/`). The src/ layout is increasingly preferred as it prevents accidentally importing from the wrong location during development.

Unlike languages with strict conventions, Python is flexible, but following common patterns makes your project immediately recognizable to other developers.

Every Python project should have certain files at the root: `requirements.txt` lists all package dependencies, `.env` stores environment variables and secrets (never commit this!), `.gitignore` prevents committing unnecessary files like `__pycache__` and `.env` (always start with the [official Python .gitignore](https://github.com/github/gitignore/blob/main/Python.gitignore) and modify it as you go), and README.md explains what the project does and how to run it.

Here is a typical project structure:

```
sample-python-project/
├── .env.template
├── .gitignore
├── README.md
├── requirements.txt
├── docker-compose.yml
├── Dockerfile
│
├── app/
│   ├── __init__.py
│   ├── main.py    # typical application entry point
│   ├── config.py
│   │
│   ├── api/
│   │   ├── __init__.py
│   │   └── routes.py
│   │
│   └── other packages with the same structure as api/
│
└── tests/
    ├── __init__.py
    └── test_main.py
```

## Further on project structure

For more complex projects where you need to publish packages, manage multiple environments, or configure build systems, consult the [Python Packaging User Guide](https://packaging.python.org/en/latest/).

The guide is the official reference for everything related to packaging and distribution. It covers `pyproject.toml`, the modern standard that consolidates project metadata, dependencies, and tool configuration into a single file. Many newer projects use `pyproject.toml` instead of the traditional `setup.py` (`setup.py` tells Python how to install your package and what dependencies it needs) and `requirements.txt` combination. The guide also explains dependency management tools, virtual environments, and how to publish your packages to PyPI so others can install them with pip.

When you need to understand how Python packages are built and distributed, the guide is a good place to start.