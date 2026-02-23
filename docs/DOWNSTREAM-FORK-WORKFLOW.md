# Downstream Fork Workflow

This project is designed to support downstream organizational forks.

## Recommended Repository Pattern

1. Public upstream repo:
   - `joshphillipssr/github-issue-email-parser`
2. Org fork for organization-owned code changes:
   - `<org>/github-issue-email-parser`
3. Optional private deployment/operations repo:
   - `<org>/<deployment-repo>`

## Branching Pattern

1. Keep fork `main` close to upstream `main`.
2. Use short-lived feature branches for generic improvements.
3. Submit PRs from fork branches back to upstream for reusable changes.

## Sync Pattern

1. Fetch upstream.
2. Merge or rebase upstream `main` into fork `main`.
3. Validate tests and deployment.
4. Promote into your deployment repository/workflow.

## Boundary Guidance

Put these in upstream/fork code:

1. Parser behavior
2. Retry/queue logic
3. API integration logic
4. Generic docs/tests

Keep these in private deployment repo:

1. DNS/hostnames
2. Org-specific mailbox addresses
3. Secrets/runtime environment management
4. Internal runbooks and access policies
