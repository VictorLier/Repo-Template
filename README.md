# Template Initialization
Welcome to your new repository. **First** clone the repository to your local machine.

## Branch protection
To ensure code quality, branch protection rules are used to make sure PRs are checked before being merged. To enable protection, in GitHub, go to:
`Settings - Rules - Rulesets`

Click `New ruleset` and choose `Import a ruleset`.
Select the `.github/ruleset.json` file from this repository.

This will setup a good *default* protection ruleset, it can be edited if applicable.
Press save when done.


### Signed commits
One of the *default* branch protection rules are the need for **signed commits**.
They will ensure that commits are from a reliable source.
Follow the [instructions](https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification) to see more.

## Project Structure
This template follows a standard Python project structure:
```
.
├── .github/              # GitHub configuration
│   ├── workflows/        # CI/CD workflows (pytest, ruff, mypy, codeql)
│   ├── ruleset.json      # Branch protection rules
│   └── dependabot.yml    # Automated dependency updates
├── .vscode/              # VS Code configuration
│   ├── extensions.json   # Recommended extensions
│   └── settings.json     # Editor settings
├── src/                  # Source code
├── tests/                # Test files
├── pyproject.toml        # Project configuration and dependencies
└── README.md             # This file
```

## Recommended extensions
In the `.vscode/extensions.json` is a list of recommended extensions for VS code.
When opening the repo in VS code it automatically asks and installs the extensions.

## uv package manager
This template is setup to work with the `uv` package manager.
It however does not have to be used, if you prefere another way feel free to use it.

### Installation
To install the `uv` package manager, open a terminal and run:
```
# On Windows.
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"

# On macOS and Linux.
curl -LsSf https://astral.sh/uv/install.sh | sh
```
No other dependancies are neccessary.


### Initialization
With `uv` installed open a terminal in VS code within the desired repository.
Then simply type:
```
uv sync
```
Thats it.
A virtual environment is now setup in the repo.
VS code should ask wheter this `.venv` should be used.
Otherwise select it as the python interpreter.

### Package management
To install a package into the environment run:
```
uv add <package_name>
```
To remove a package run:
```
uv remove <package_name>
```
Notice that the `uv.lock` file is updated to reflect the new changes.
The `uv.lock` file should be included in git, so be aware of which branch/commit the changes are included in.

The packages and python version can also be edited directly in the `pyproject.toml` file.
To update the virtual environment and `uv.lock` file with the changes run:
```
uv sync
```

### Advantages of uv
`uv` greatly simplifies the management of virtual environments.
You do not need to keep track of python versions, base and virtual environments and so on.
You don't even need a python version on your machine, `uv` is all you need.
In fact changing the python version is as simple as editing the `pyproject.toml`.

The `uv.lock` file also ensures that all developers are using the **exact** same python and package version to run the code.

## CI/CD
This template includes GitHub Actions workflows that automatically run on pull requests:

- **CI Workflow** (`ci.yml`): Runs tests, linting (ruff), and type checking (mypy)
- **CodeQL** (`codeql.yml`): Performs security analysis
- **Dependabot** (`dependabot.yml`): Automatically creates PRs for dependency updates

All checks must pass before a PR can be merged (enforced by the ruleset).


## README
This `README.md` file should be changed to reflect the need of the repository.
The `README.md` is critical for understanding of the development side of the tool.
This is also the fundamental difference between the userguide and the readme.
Where the userguide is for how the user should use the tool, the readme is for how the developer should develop the tool.