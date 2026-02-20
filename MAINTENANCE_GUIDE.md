# Codebase Maintenance and Development Guide

## For AI Coding Agents

This guide outlines the standards and procedures for maintaining and developing the prompts.chat codebase, with special emphasis on guidelines for AI coding agents.

### Branching Strategy

Adopt GitHub Flow for simplicity:

- **`main`**: Primary branch for production-ready code. All releases originate here.
- **`dev`**: Branch for ongoing development and integration of features.
- **`staging`**: Branch for testing and quality assurance before release.
- **`release`**: Branch for final release preparation and hotfixes.
- **Feature branches**: Created from `main` as `feature/feature-name` for individual features.

Workflow:
1. Create feature branch from `main`.
2. Develop and commit changes.
3. Open PR to merge into `main`.
4. After review, merge and delete branch.

Naming: `feature/descriptive-name`, commits imperative mood.

### Code Organization

Follow strict directory structure:

- Core logic: `src/core/`
- Utilities: `src/utils/`
- Configuration: `src/config/`
- Backend: `server/cascade_engine/`, `server/cascade_api/`, `server/cascade_tasks/`
- Frontend: `frontend/components/`, `frontend/styles/`
- Data: Vector store in `server/data/vector_store/`, sessions in `server/data/sessions/`
- Logs: `server/logs/`

### Code Style

- Variables/functions: camelCase
- Components/classes: PascalCase
- Constants: UPPER_SNAKE_CASE
- Files: kebab-case.tsx for components, camelCase.ts for utilities
- Max line length: 100 characters
- JSDoc/TSDoc for public APIs
- No comments unless specified

### Development Rules

- Lint before commit: `npm run lint`
- Use existing UI components from `src/components/ui/`
- Add i18n for user-facing text
- Follow established patterns
- No hardcoded secrets; use env vars
- Validate and sanitize inputs
- Optimize performance in hot paths
- Proper error handling and logging

### Testing Requirements

- Unit tests for all new features
- E2E tests in `tests/e2e/`
- Mocks in `tests/mocks/`
- Update documentation for tests

### Version Control

- Clear, descriptive commit messages
- Feature branches for development
- PRs reviewed before merge
- Atomic, focused commits

### Security

- Never commit secrets or API keys
- Validate all inputs
- Principle of least privilege

### Performance

- Optimize hot code paths
- Use appropriate data structures
- Monitor database queries

### Dependencies

- Keep updated
- Document addition reasons
- Prefer focused libraries

### Review Process

- All code reviewed
- Address review comments
- Keep PRs focused and reasonable size

### Deployment

- Follow deployment checklist
- Test in staging before production
- Maintain rollback procedures

### Monitoring and Maintenance

- Monitor logs for errors
- Set alerts for issues
- Regularly update dependencies
- Periodic security audits

### Agent-Specific Guidelines

For AI coding agents working on this project:

- Always adhere to AGENTS.md
- Do not overstep bounds; pair program with user
- Use tools appropriately; no random files
- Be terse and direct
- Implement changes rather than suggest
- Add necessary imports and dependencies
- No ungrounded assertions
- Use citation format for code references
- End conversations with task summaries

### Git Tagging

Use semantic versioning for tags (e.g., v1.0.0 for major.minor.patch).

- Tag releases on the main branch after successful testing and merging.
- Create an annotated tag: `git tag -a v1.0.0 -m "Release version 1.0.0"`
- Push tags to remote: `git push origin --tags`
- List tags: `git tag`
- Delete tags if needed: `git tag -d v1.0.0` and `git push origin --delete v1.0.0`

### Commands

- Development: `npm run dev`
- Build: `npm run build`
- Database: `npm run db:migrate`, `npm run db:seed`
- Type check: `npx tsc --noEmit`
- Linting: `npm run lint`

This guide ensures consistent, maintainable development of the prompts.chat codebase.
