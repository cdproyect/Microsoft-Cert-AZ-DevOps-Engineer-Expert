# Explore branch workflow types

[Workflow types](https://docs.microsoft.com/en-gb/learn/modules/manage-git-branches-workflows/2-explore-branch-workflow-types)

## Trunk-based development

Trunk-based development is a logical extension of Centralized Workflow.

The core idea behind the Feature Branch Workflow is that all feature development should take place in a dedicated branch instead of the main branch.

This encapsulation makes it easy for multiple developers to work on a particular feature without disturbing the main codebase.

It also means the main branch should never contain broken code, which is a huge advantage for continuous integration environments.

## [GitFlow workflow](https://nvie.com/posts/a-successful-git-branching-model/)

The Gitflow Workflow defines a strict branching model designed around the project release.

This workflow doesn't add any new concepts or commands beyond what's required for the Feature Branch Workflow.

Instead, it assigns particular roles to different branches and defines how and when they should interact.

The overall flow of Gitflow is:

- A develop branch is created from the main.
- A release branch is created from develop.
- Feature branches are created from develop.
- When a feature is complete, it's merged into the develop branch.
- When the release branch is done, it's merged into develop and main.
- If an issue in the main is detected, a hotfix branch is created from the main.
- Once the hotfix is complete, it's merged to both develop and main.

## Forking workflow

The Forking Workflow is fundamentally different than the other workflows discussed in this tutorial.

Instead of using a single server-side repository to act as the "central" codebase, it gives every developer a server-side repository.

It means that each contributor has two Git repositories:

- A private local one.
- A public server-side one.

The following is a step-by-step example of this workflow:

- A developer 'forks' an 'official' server-side repository. It creates their server-side copy.
- The new server-side copy is cloned to their local system.
- A Git remote path for the 'official' repository is added to the local clone.
- A new local feature branch is created.
- The developer makes changes to the new branch.
- New commits are created for the changes.
- The branch gets pushed to the developer's server-side copy.
- The developer opens a pull request from the new branch to the 'official' repository.
- The pull request gets approved for merge and is merged into the original server-side repository.

To integrate the feature into the official codebase:

- The maintainer pulls the contributor's changes into their local repository.
- Checks to make sure it doesn't break the project.
- Merges it into their local main branch.
- Pushes the main branch to the official repository on the server.

The contribution is now part of the project, and other developers should pull from the official repository to synchronize their local repositories.
