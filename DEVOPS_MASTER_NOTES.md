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

## DAY 4: GIT RECOVERY & REMOTE BASICS
 
### git restore
Used to discard uncommitted changes from the working directory.
 
Command:
git restore <file>
 
Learning:
Safely undo changes before commit.
 
--------------------------------------------------
 
### git reset --soft
Used to undo the last commit while keeping changes staged.
 
Command:
git reset --soft HEAD~1
 
Learning:
- Commit is removed
- Code remains safe
- Useful for fixing commit messages
 
--------------------------------------------------
 
### Local vs Remote Repository
 
Local Repository:
- Exists on developer’s machine
- Used for daily work
 
Remote Repository:
- Hosted on platforms like GitHub
- Used for sharing and backup
 
--------------------------------------------------
 
### git fetch vs git pull
 
git fetch:
- Downloads changes from remote
- Does NOT merge automatically
- Safe for review
 
git pull:
- Downloads + merges changes
- Updates working directory
 
--------------------------------------------------
 
### Interview Questions (Day 4)
 
Q: What does git restore do?
A: Discards uncommitted changes.
 
Q: Difference between git fetch and git pull?
A: fetch downloads changes; pull downloads and merges.
 
================================================== 

## DAY 5: GITHUB & REMOTE WORKFLOW
 
### What is GitHub?
GitHub is a cloud platform used to host and share Git repositories.
 
### Why GitHub is Important?
- Central storage
- Backup of work
- Collaboration
- Multi-system workflow
 
--------------------------------------------------

### Creating a Clean Repository
A new repository was created without README, .gitignore, or license to avoid conflicts with the local repository.

--------------------------------------------------
 
### Creating a Remote Repository
A new repository was created on GitHub without README, .gitignore, or license.
 
--------------------------------------------------
 
### Adding Remote to Local Repository or Connecting Local Repo to GitHub
 
Commands:
git branch -M main
git remote add origin https://github.com/<USERNAME>/future-proof-devops.git
git remote -v
 
Learning:
Remote connects local repository to GitHub.
 
--------------------------------------------------
 
### Default Branch (main vs master)
 
- master: old default branch
- main: new industry standard
 
Command used:
git branch -M main
 
--------------------------------------------------
 
### First Push to GitHub
 
Command:
git push -u origin main
 
Learning:
- Push uploads commits to GitHub
- -u sets upstream for future pushes
 
--------------------------------------------------
 
### Multi-System Workflow (Home + Office)
GitHub enables seamless multi-system development using clone,pull and push. 
Steps:
1. git clone (new system)
2. Work and commit
3. git push
4. git pull on other system
 
--------------------------------------------------
 
### Interview Questions (Day 5)

Q:What is a remote in Git?
A: A remote is a reference to a repository hosted elsewhere(e.g., GitHub)
 
Q: What is a remote repository?
A: A repository hosted on a platform like GitHub.
 
Q: How do you sync work between two systems?
A: Using git clone, pull, and push.

Q: Why archive instead of delete?
A: Archiving preserves history while preventing further changes, which is useful for reference and clean restarts.

Q:Why GitHub worked yesterday but not today?
A: Proxy, VPN, or network settings may change and block Git traffic even when the internet works.

Q:Why ping works but git doesn't?
A:Ping tests ICMP;Git uses HTTPS(TCP 443), which may be blocked or proxied.

--------------------------------------------------
 
### GitHub Authentication using HTTPS (Personal Access Token)
 
Scenario:
While pushing code to GitHub using HTTPS, Git asked for username and password.
 
Observation:
GitHub no longer supports password-based authentication for Git operations.
 
--------------------------------------------------
 
### Why Password is Not Used?
 
For security reasons, GitHub requires a Personal Access Token (PAT)
instead of account password when using HTTPS.
 
--------------------------------------------------
 
### Authentication Flow (HTTPS)
 
Command:
git push -u origin main
(-u make future pushes in simple)

Q:What does git push -u do?
A:Sets upstream so future pushed can be done with git push.

Q:What is a remote in Git?
A:A remote is a reference to a repository hosted elsewhere(e.g., GitHub)n
 
Steps:
1. Enter GitHub username
2. Enter Personal Access Token as password
 
Note:
While pasting the token, nothing appears on screen.
This is normal behavior.
 
--------------------------------------------------
 
### Personal Access Token (PAT)
 
What is PAT?
A Personal Access Token is a secure token used to authenticate
Git operations instead of a password.
 
Token Creation Path:
GitHub → Settings → Developer settings →
Personal access tokens → Tokens (classic)
 
Required Scopes:
- repo
 
--------------------------------------------------
 
### Successful Push Result
 
After providing username and token:
- Push completed successfully
- Local repository synced with GitHub
 
--------------------------------------------------
 
### Learning:
- HTTPS authentication uses username + token
- Password authentication is deprecated
- PAT is required for secure GitHub access
 
--------------------------------------------------
 
### Interview Questions
 
Q: Why does GitHub not allow password authentication?
A: For better security, GitHub uses Personal Access Tokens instead of passwords.
 
Q: What is a Personal Access Token?
A: A token used to authenticate Git operations over HTTPS.
 
================================================== 
