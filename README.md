# Template Initialization
Welcome to your new repository. *First* clone the repository to your local machine.

## Branch protection
To ensure code quality, branch protection rules are used to make sure PRs are checked before being merged. To enable protection, in GitHub, go to:
`Settings - Rules - Rulesets`

Click `New ruleset` and choose `Import a ruleset`. Select the `.github/workflows/ruleset.json` file from this repository.

This will setup a good *default* protection ruleset, it can be edited if applicable. Press save when done.


### Signed commits
One of the *default* branch protection rules are the need for **signed commits**. They will ensure that commits are from a reliable source. Follow the [instructions](https://docs.github.com/en/authentication/managing-commit-signature-verification/signing-commits) to see more.

## Recommended extensions
In the `.vscode/extensions.json` is a list of recomended extensions for VS code. When opening the repo in VS code it automatically asks and installs the extensions.