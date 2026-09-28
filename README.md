# Dragonleech Code organization defaults

This public repository provides defaults for repositories in the `dragonleech-code` organization.

## Pull requests

`.github/PULL_REQUEST_TEMPLATE.md` supplies the default pull request description when a repository has no template of its own. A repository-specific template takes precedence.

## AI review

The reviewer implementation lives in [`dragonleech-code/ai-review`](https://github.com/dragonleech-code/ai-review). Organization-wide automation is configured in GitHub's repository rulesets. A workflow file in this repository is the central caller; placing a workflow here alone does not install it in other repositories.

The `AI_REVIEW_API_KEY` organization secret is available to the repositories and the reviewer reads pull request diffs through the GitHub API. Fork pull requests, drafts, and Dependabot pull requests follow the reviewer's existing skip policy. Findings are first-pass suggestions for a human reviewer.
