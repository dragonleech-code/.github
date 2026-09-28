# Dragonleech Code organization defaults

This public repository provides defaults for repositories in the `dragonleech-code` organization.

## Pull requests

`.github/PULL_REQUEST_TEMPLATE.md` supplies the default pull request description when a repository has no template of its own. A repository-specific template takes precedence.

## AI review

The reviewer implementation lives in [`dragonleech-code/ai-review`](https://github.com/dragonleech-code/ai-review). The `AI review` organization ruleset requires `.github/workflows/ai-review.yml` from this repository for PRs to default branches and to `main` release branches. The rule makes the workflow run in each targeted repository without copying this file into it. A reviewer outage blocks merging until the workflow passes.

The `AI_REVIEW_API_KEY` organization secret is available to the repositories and the reviewer reads pull request diffs through the GitHub API. Fork pull requests, drafts, and Dependabot pull requests follow the reviewer's existing skip policy. Findings are first-pass suggestions for a human reviewer. `cvis` and `concordvanguard.com` use their shorter `.github/review-conventions.md` files; other repositories use `CLAUDE.md` when present.
