
# Git Worktrees and Multi-Agent Development

## Purpose

Allow multiple AI coding agents to implement independent
tasks safely while preserving review and quality gates.

## Before Creating Worktrees

1. Start from an updated main branch.
2. Define the feature specification and acceptance criteria.
3. Identify independent tasks and dependencies.
4. Agree on shared interfaces before parallel implementation.
5. Assign each agent a branch, worktree, and ownership boundary.

## Worktree Rules

- One active task and branch per worktree.
- Each agent works only in its assigned directory.
- Agents must not modify another agent's worktree.
- Avoid overlapping file ownership where possible.
- Never share writable production resources.
- Use isolated test data and development services.
- Do not commit credentials or local environment files.

## Agent Responsibilities

Each agent must:
- Read AGENTS.md and relevant specifications.
- Confirm task scope and ownership.
- Implement only assigned changes.
- Add or update relevant tests.
- Run applicable checks.
- Report results and limitations.
- Prepare changes for human review.

## Integration

1. Commit changes using Conventional Commits.
2. Push the feature branch.
3. Open a pull request targeting main.
4. Run required CI and security checks.
5. Review changes and resolve conflicts.
6. Merge only after required gates pass.
7. Update other worktrees before dependent work.

## Conflict Prevention

- Define shared contracts before parallel implementation.
- Prefer independent features over overlapping edits.
- Avoid concurrent modifications to shared configuration.
- Assign one owner for migrations and shared interfaces.
- Resolve conflicts deliberately; never overwrite work.

## Cleanup

After a branch has been merged:
- Verify no uncommitted work remains.
- Remove its worktree.
- Delete obsolete branches when appropriate.

Never force-remove a worktree containing valuable changes.
