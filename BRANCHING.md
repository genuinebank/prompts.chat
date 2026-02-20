# Git Branching Architecture

This project uses a simplified GitHub Flow for feature development.

## Branches

- **`main`**: The primary branch containing production-ready code. All releases come from this branch.

## Workflow

1. **Start a Feature**:
   - Create a new branch from `main`: `git checkout -b feature/your-feature-name`
   - Push the branch to origin: `git push origin feature/your-feature-name`

2. **Develop**:
   - Commit changes to your feature branch.
   - Keep commits focused and descriptive.

3. **Merge**:
   - Create a pull request (PR) from your feature branch to `main`.
   - Get code review if needed.
   - Merge the PR.
   - Delete the feature branch after merging.

## Naming Conventions

- Feature branches: `feature/descriptive-name` (e.g., `feature/add-user-auth`)
- Commits: Use imperative mood (e.g., "Add user authentication")

## Remotes

- `origin`: https://github.com/genuinebank/prompts.chat (primary remote)
- `source`: https://github.com/f/prompts.chat (upstream/source remote)

Always push to `origin` for new features in this repo.
