==================================================

## STANDARD TROUBLESHOOTING STRUCTURE (USE FOR EVERY ISSUE)

==================================================

## ISSUE: Push Rejected (fetch first)

### Error Message

! [rejected] main -> main (fetch first)

error: failed to push some refs

--------------------------------------------------

### Root Cause

Remote repository contained commits that were not present locally.

Git blocked push operation to prevent accidental overwrite of remote history.

--------------------------------------------------

### Resolution

Commands Used:

git pull origin main --rebase
git push

Explanation:

git pull --rebase downloaded remote commits and replayed local commits on top of latest history.

--------------------------------------------------

### Learning

- Remote and local repositories must stay synchronized
- Rebase creates cleaner history than merge
- Push can fail if remote contains newer commits

--------------------------------------------------

### Dangerous Commands / Actions to Avoid

Command:
git push --force

Why Dangerous:
Can overwrite remote history and permanently remove commits.

--------------------------------------------------

### When It Can Be Used Safely

- Personal branches
- Controlled repositories
- After verifying remote impact

Better Alternative:
git push --force-with-lease

--------------------------------------------------

### Real-World Production Insight

Incorrect force push can remove teammates' commits and break CI/CD pipelines.

--------------------------------------------------

### Mentor Advice

Never use force push just to "make error disappear".
Always understand WHY Git rejected the push.

==================================================

## ISSUE: Merge Conflict During Rebase

### Error Message

CONFLICT (content): Merge conflict in DEVOPS_MASTER_NOTES.md

--------------------------------------------------

### Root Cause

Same file was modified in both local and remote repositories.

Git could not automatically decide which changes to keep.

--------------------------------------------------

### Resolution

Commands Used:

vim DEVOPS_MASTER_NOTES.md
git add DEVOPS_MASTER_NOTES.md
git rebase --continue

Explanation:

Conflict markers were manually resolved and rebase process was continued.

--------------------------------------------------

### Learning

- Merge conflict is not a Git failure
- Conflicts must be resolved manually
- git status gives next troubleshooting step

--------------------------------------------------

### Dangerous Commands / Actions to Avoid

Command:
git rebase --skip

Why Dangerous:
Skips conflicted commit entirely and may permanently lose important work.

--------------------------------------------------

### When It Can Be Used Safely

- Duplicate changes already exist
- Commit is unnecessary
- Changes intentionally discarded

--------------------------------------------------

### Dangerous Commands / Actions to Avoid

Command:
git rebase --abort

Why Dangerous:
Cancels entire rebase operation and discards temporary progress.

--------------------------------------------------

### When It Can Be Used Safely

- Rebase selected wrong branch
- Conflict resolution became too complex
- Want to restart rebase cleanly

--------------------------------------------------

### Real-World Production Insight

Merge conflicts are common in multi-developer environments where multiple engineers modify same files.

--------------------------------------------------

### Mentor Advice

Do not panic during conflicts.
Read conflict markers carefully and resolve logically.

==================================================

## ISSUE: Detached HEAD State During Rebase

### Error Message

fatal: You are not currently on a branch.

--------------------------------------------------

### Root Cause

git push was attempted before completing ongoing rebase process.

Repository was still in detached HEAD state.

--------------------------------------------------

### Resolution

Commands Used:

git rebase --continue
git push

Explanation:

Rebase process was completed successfully before pushing changes.

--------------------------------------------------

### Learning

- Detached HEAD state can occur during rebase
- Rebase must finish completely before push
- git status is critical troubleshooting command

--------------------------------------------------

### Dangerous Commands / Actions to Avoid

Command:
git push origin HEAD:<branch>

Why Dangerous:
May push incomplete or incorrect detached HEAD state to remote repository.

--------------------------------------------------

### When It Can Be Used Safely

- Advanced Git recovery operations
- Temporary experimental pushes
- Only after understanding detached HEAD properly

--------------------------------------------------

### Real-World Production Insight

Improper handling of detached HEAD state can create confusing repository history in enterprise environments.

--------------------------------------------------

### Mentor Advice

Always run git status before panic actions.
Git usually tells the exact next step required.

==================================================

## RECOVERY COMMANDS

### git reflog

Purpose:
Shows complete reference history including deleted or lost commits.

Use Case:
Recover accidentally deleted commits.

--------------------------------------------------

### git restore

Purpose:
Discard uncommitted file changes safely.

--------------------------------------------------

### git reset --soft

Purpose:
Undo commit while keeping changes staged.

--------------------------------------------------

### git reset --hard

Purpose:
Completely reset repository state.

Danger:
Permanently deletes uncommitted changes.

--------------------------------------------------

### git revert

Purpose:
Safely undo commit by creating new reverse commit.

Preferred in shared repositories.

==================================================
