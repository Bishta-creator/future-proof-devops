#  DEVOPS MASTER NOTES  (A-Z)
## Absolute Beginner to Future-Proof DevOps Engineer

Author:  Arjun Singh Bisht
Level: Absolute Beginner  ->  Professional
Daily Time: 2.5 hours
Purpose: Achieve my goal of getting a new role.

==================================================

## PHASE 1: GIT & GITHUB (FOUNDATION)
 
==================================================
 
## DAY 1: INTRODUCTION TO GIT (ZERO LEVEL)
 
### What is Git?
Git is a version control system used to track changes in files over time.
 
### Why Git is Important?
- Keeps history of changes
- Allows rollback to previous versions
- Used by all IT companies
- Essential for collaboration and job readiness
 
### Real-Life Example:
Git works like a time machine for your files.
If something breaks, you can go back to a previous safe version.
 
--------------------------------------------------
 
### Git vs GitHub
 
Git:
- A tool/software
- Works on local system
- Tracks file changes
 
GitHub:
- Online platform
- Stores Git repositories
- Used for sharing and collaboration
 
--------------------------------------------------
 
### Git Installation (Linux)
 
Command:
yum install git -y
 
Verification:
git --version
 
--------------------------------------------------
 
### First Git Repository
 
Commands Used:
mkdir git-phase1  
cd git-phase1  
git init  
 
Result:
A `.git` directory is created, which makes the folder a Git repository.
 
--------------------------------------------------
 
### First Commit
 
Commands:
git add notes.txt  
git commit -m "Day 1: Git initialized and first notes added"
 
Learning:
- git add moves files to staging area
- git commit saves a snapshot of changes
 
--------------------------------------------------
 
### Interview Questions (Day 1)
 
Q: What is Git?  
A: Git is a version control system used to track changes in files.
 
Q: Difference between Git and GitHub?  
A: Git is a tool, GitHub is a hosting platform.
 
==================================================
 
## DAY 2: GIT CORE WORKFLOW
 
### Git Configuration
 
Commands:
git config --global user.name "Arjun Bishta"  
git config --global user.email "your_email@example.com"
 
Purpose:
Git uses this information to identify who made a commit.
 
--------------------------------------------------
 
### Git Log (History)
 
Commands:
git log  
git log --oneline  
 
Purpose:
Shows commit history with author, date, and message.
 
--------------------------------------------------
 
### Git Diff (Change Comparison)
 
Commands:
git diff  
git diff --staged  
 
Purpose:
- git diff → unstaged changes
- git diff --staged → staged changes
 
--------------------------------------------------
 
### .gitignore (Professional Practice)
 
File:
.gitignore
 
Example Content:
*.log  
*.tmp  
node_modules/
 
Purpose:
Tells Git which files should not be tracked.
 
--------------------------------------------------
 
### Interview Questions (Day 2)
 
Q: What is staging area in Git?  
A: It is an intermediate area where changes are prepared before commit.
 
Q: What is .gitignore?  
A: It tells Git to ignore specific files or folders.

==================================================
 
## DAY 3: GIT BRANCHING (ZERO → PROFESSIONAL)
 
### What is a Branch?

A Git branch is an independent line of development that allows developers to work on features or fixes without affecting the main codebase.
 
--------------------------------------------------
 
### Why Branches are Used?

- To work on new features safely

- To avoid breaking stable code

- To allow multiple developers to work in parallel

- To maintain clean and controlled development
 
--------------------------------------------------
 
### What is the Default Branch?
 
The default branch is the primary branch of a Git repository.

It usually contains stable and production-ready code.
 
--------------------------------------------------
 
### main vs master (IMPORTANT)
 
Earlier:

- `master` was the default branch name in Git
 
Now:

- `main` is the default branch name on most platforms (GitHub, GitLab)
 
Reason for change:

- To use more inclusive and clear terminology
 
Current industry practice:

- New repositories → `main`

- Old repositories → may still use `master`
 
--------------------------------------------------
 
### Commands Used for Branching
 
List branches:

git branch
 
Create a new branch:

git branch feature-day3
 
Switch to a branch (modern command):

git switch feature-day3
 
--------------------------------------------------
 
### checkout vs switch (VERY IMPORTANT)
 
git checkout:

- Older command

- Used for branch switching AND file restoration

- Confusing for beginners
 
git switch:

- Newer command

- Used only for switching branches

- Clear and safer
 
Interview Answer:

`git switch` is preferred for changing branches, while `git checkout` is an older multi-purpose command.
 
--------------------------------------------------
 
### Working on a Branch
 
Changes made on a branch do not affect the main branch

until they are merged.
 
--------------------------------------------------
 
### Merge in Git
 
Merge is the process of combining changes from one branch

into another branch.
 
Example:

- feature branch → merged into main branch
 
--------------------------------------------------
 
### Types of Merge (Basic)
 
Fast-forward merge:

- Happens when main branch has no new commits

- Branch pointer simply moves forward
 
--------------------------------------------------
 
### Deleting a Branch
 
After merging, branches should be deleted to keep

the repository clean.
 
Command:

git branch -d feature-day3
 
--------------------------------------------------
 
### Interview Questions (Day 3)
 
Q: What is a Git branch?  

A: A separate line of development used to work independently.
 
Q: What is the default branch in Git?  

A: The primary branch that contains stable code (usually main).
 
Q: Difference between main and master?  

A: master was the old default; main is the new standard.
 
Q: Difference between checkout and switch?  

A: checkout is older and multi-purpose, switch is modern and only for branches.
 
Q: Why do we delete branches after merge?  

A: To keep the repository clean and manageable.
 
==================================================
 
--------------------------------------------------
 
### Common Git Error: Changes not staged for commit
 
Error Message:

Changes not staged for commit  

deleted: notes.txt  

no changes added to commit
 
--------------------------------------------------
 
### Root Cause:

- A file (notes.txt) was renamed to DEVOPS_MASTER_NOTES.md

- Git detected the deletion and new file

- Changes were NOT staged using `git add`

- Git does not commit unstaged changes
 
--------------------------------------------------
 
### Resolution Steps:

1. Check current status:

   git status
 
2. Stage all changes (including deletions):

   git add -A
 
3. Commit changes:

   git commit -m "Meaningful message"
 
--------------------------------------------------
 
### Learning:

- git commit works only on staged changes

- File rename = delete + new file in Git

- Always run `git add` before commit

- Use `git add -A` to include deleted files
 
--------------------------------------------------
 
### Interview Question:

Q: Why does Git say "changes not staged for commit"?

A: Because files were modified, deleted, or created but not added to the staging area using `git add`.
 
==================================================

  
