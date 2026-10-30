
# Run from the main repository directory.

# 1. Update main
git checkout main
git pull --ff-only origin main

# 2. Create independent worktrees
git worktree add ../project-api -b feature/api
git worktree add ../project-ui -b feature/ui

# 3. List active worktrees
git worktree list

# 4. Work independently
cd ../project-api
git status

# Start a separate Codex session here.
# Repeat in ../project-ui for another agent.

# 5. After PRs are merged, return to main
cd ../ai-sdd-workflow
git pull --ff-only origin main

# 6. Verify worktrees are clean, then remove
git worktree remove ../project-api
git worktree remove ../project-ui

# 7. Delete merged local branches
git branch -d feature/api
git branch -d feature/ui
