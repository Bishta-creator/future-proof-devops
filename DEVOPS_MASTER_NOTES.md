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
 
=============================================================================================
