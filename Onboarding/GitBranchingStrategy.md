# Git Branching Strategy

## Main Branches

### `master`
The `master` branch should be considered the main branch where the source code of Project100 always reflects a state with the latest delivered development changes for the next release.

### `stable`
The `stable` branch always represents the latest code deployed to production. This branch is only updated when a new release is ready to be deployed and does not have day-to-day interaction.

When the source code in `master` is stable and has been deployed, all of the changes will be merged into `stable` and tagged with a release number.

## Supporting Branches
Supporting branches are used to facilitate parallel development, track features, and quickly fix live production problems. These branches have a limited lifespan and are removed after merging.

### Branch Types:
- `feature-*`
- `hotfix-*`
- `bug-*`
- `refactor-*`

### Feature Branches
Feature branches are used when developing a new feature or enhancement that may take longer than a single deployment cycle. These branches are merged back into `master` upon completion.

**Rules:**
- Must branch from: `master`
- Must be merged back into: `master`
- Naming convention: `feature-<feature-name>`

**Workflow:**
```sh
$ git checkout -b feature-id master   # Create a new feature branch
$ git push origin feature-id          # Push the feature branch remotely
$ git merge master                    # Merge updates from master periodically
$ git checkout master                 # Switch to master for merging
$ git merge --no-ff feature-id         # Merge feature branch with commit tracking
$ git push origin master               # Push merge changes to master
$ git push origin :feature-id          # Delete the remote feature branch
```

### Bug Branches
Bug branches are created to explicitly track fixes for issues found in production. These branches last no longer than one deployment cycle.

**Rules:**
- Must branch from: `master`
- Must be merged back into: `master`
- Naming convention: `bug-<bug-name>`

**Workflow:**
The workflow is identical to feature branches.

### Hotfix Branches
Hotfix branches address urgent issues in production and must be applied immediately without waiting for a scheduled deployment. They always branch from a tagged `stable` branch.

**Rules:**
- Must branch from: tagged `stable`
- Must be merged back into: `master` and `stable`
- Naming convention: `hotfix-<hotfix-name>`

**Workflow:**
```sh
$ git checkout -b hotfix-id stable     # Create a new hotfix branch
$ git push origin hotfix-id            # Push the hotfix branch remotely
$ git checkout stable                  # Switch to stable branch
$ git merge --no-ff hotfix-id          # Merge hotfix into stable
$ git tag -a <tag>                     # Tag the fix (Semantic Versioning)
$ git push origin stable --tags        # Push stable branch with tags
$ git checkout master                  # Switch to master
$ git merge --no-ff hotfix-id          # Merge hotfix into master
$ git push origin master               # Push merge changes to master
$ git push origin :hotfix-id           # Delete the remote hotfix branch
```

### Refactor Branches
Refactor branches are used for optimizations and restructuring. These are typically handled by @DistractedGames unless delegated.

**Rules:**
- Must branch from: `master`
- Must be merged back into: `master`
- Naming convention: `refactor-<refactor-name>`

**Workflow:**
The workflow is identical to feature and bug branches.

---
This branching strategy ensures an organized and efficient development workflow, minimizing disruptions while maintaining production stability.
