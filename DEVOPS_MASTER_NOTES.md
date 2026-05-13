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

Note:
Initially notes.txt was used for practice.
Later it was renamed to DEVOPS_MASTER_NOTES.md as a professional master notes file.
 
Commands:
git add DEVOPS_MASTER_NOTES.md  
git commit -m "Day 1: Git initialized and first notes added"
 
Learning:
- git add moves changes to the staging area, allowing selective commits instead of committing all modified files at once.
- git commit saves a snapshot of changes

***Important Concept:

Each commit in Git is a snapshot of the project at a specific point in time,
not just a difference or patch. 


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

Merge Command Example:
git switch main
git merge feature-day3
 
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

-------------------------------------------------

Difference between git add . and git add -A

git add .

-Stages new and modified files
-Does NOT stage deleted files in some cases

git add -A

-Stages new, modified, and deleted files
-Recommended for complete staging

**Real-World Note:**

In production environments, `git add -A` is preferred because it ensures all changes
(new, modified, deleted) are tracked, preventing accidental omission of deleted files.


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

### Removing a Remote Repository

Commands:
git remote remove origin

Use Case:

-Wrong remote URL added
-Clean reconfiguration required

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
- -u sets the upstream branch, allowing future pushes using only `git push` without specifying remote and branch.
 
--------------------------------------------------
 
### Multi-System Workflow (Home + Office)
GitHub enables seamless multi-system development using clone,pull and push. 
Steps:
1. git clone (new system(profilelinl like :- https:\\github.com\Bishta-creator\future-proof-devops.git)
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
A:A remote is a reference to a repository hosted on another system(e.g., GitHub)
 
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

## DAY 6: GIT PHASE FINAL (AUTHENTICATION, ERRORS, DAILY WORKFLOW)
 
==================================================
 
### GitHub Authentication Methods
 
There are two main ways to authenticate GitHub:
 
1. HTTPS
2. SSH

When to Use SSH Authentication?

-When working frequently with GitHub
-Avoid entering username/token repeatedly
-Preferred in professional environments

SSH uses key-based authentication instead of passwords or token.
 
--------------------------------------------------
 
### HTTPS Authentication (Used in This Phase)
 
In HTTPS authentication, GitHub requires:
- Username
- Personal Access Token (PAT) instead of password
 
Password-based authentication is deprecated by GitHub.
 
--------------------------------------------------
 
### Why GitHub Uses Personal Access Token (PAT)?
 
- Improves security
- Prevents password leakage
- Allows controlled access using scopes
 
--------------------------------------------------
 
### HTTPS Authentication Flow
 
Command:
git push -u origin main
 
Steps:
1. Enter GitHub username
2. Enter Personal Access Token as password
 
Note:
While pasting the token, nothing appears on terminal.
This is expected behavior.
 
--------------------------------------------------
 
### Creating Personal Access Token (PAT)
 
Path:
GitHub → Settings → Developer settings →
Personal access tokens → Tokens (classic)
 
Required Scope:
- repo
 
Important:
Token is shown only once. Save it securely.
 
--------------------------------------------------
 
### Common Git Error: Could Not Resolve Host
 
Error:
fatal: unable to access 'https://github.com/...':
Could not resolve host: github.com
 
--------------------------------------------------
 
### Root Cause:
- DNS issue
- Proxy misconfiguration
- Firewall / network restriction
- VPN or office network interference
 
--------------------------------------------------
 
### Resolution Steps:
1. Check internet connectivity:
   ping google.com
 
2. Check DNS resolution:
   getent hosts github.com
 
3. Check proxy configuration:
   git config --global --get http.proxy
   git config --global --get https.proxy
 
4. Remove proxy if set:
   git config --global --unset http.proxy
   git config --global --unset https.proxy
 
--------------------------------------------------
 
### Learning:
- Ping success does not guarantee HTTPS access
- GitHub uses HTTPS (TCP 443), not ICMP
- Network issues can change daily in office environments
 
--------------------------------------------------
 
### Credential Caching (Optional)
 
To avoid entering token repeatedly:
 
Command:
git config --global credential.helper store
 
Learning:
Credentials will be stored locally after next successful authentication.
 
--------------------------------------------------
 
### Daily Professional Git Workflow
 
On any system (Home / Office):
 
1. Pull latest changes:
   git pull
 
2. Work on files
 
3. Stage changes:
   git add .
 
4. Commit changes:
   git commit -m "Meaningful commit message"
 
5. Push changes:
   git push


Commit Message Best Practices

-Use present tense
-Be clear and specific
-Avoid generic messages like "update" or "fix"

Example:
"Add Git branching notes for Day 3"
 
--------------------------------------------------
 
### Multi-System Workflow (Single Source of Truth)
 
- GitHub acts as the central repository
- Home system and office system both sync using pull and push
- Prevents data loss and version conflicts
 
--------------------------------------------------
 
### Final Learning Summary (Git Phase)
 
- Git tracks file changes
- GitHub hosts repositories
- Branches enable parallel work
- Commits are snapshots
- Staging is mandatory before commit
- HTTPS authentication uses PAT
- GitHub is essential for multi-system workflow
 
--------------------------------------------------
 
### Interview Questions (Git Phase Final)
 
Q: Why does GitHub not support password authentication?
A: For security reasons, GitHub requires Personal Access Tokens.
 
Q: What is the difference between HTTPS and SSH in Git?
A: HTTPS uses username and token, SSH uses key-based authentication.
 
Q: What command stages all changes including deletions?
A: git add -A
 
Q: Why is GitHub important for DevOps engineers?
A: It acts as a single source of truth and collaboration platform.


--------------------------------------------------
 
### GitHub Authentication using SSH (KEY-BASED AUTHENTICATION)
 
SSH authentication is a secure method to connect to GitHub

without using username and password or Personal Access Token.
 
--------------------------------------------------
 
### Why SSH is Used?
 
- More secure than HTTPS

- No need to enter username or token repeatedly

- Industry-preferred authentication method

- Uses public-private key cryptography
 
--------------------------------------------------
 
### HTTPS vs SSH (CLEAR DIFFERENCE)
 
HTTPS:

- Uses username + Personal Access Token

- Token may be required repeatedly

- Easier for beginners
 
SSH:

- Uses SSH key pair (public + private)

- No password/token after setup

- Preferred in professional environments
 
--------------------------------------------------
 
### SSH Authentication Flow
 
1. Generate SSH key on local system

2. Add public key to GitHub account

3. Test SSH connection

4. Use SSH-based repository URL
 
--------------------------------------------------
 
### Step 1: Generate SSH Key
 
Command:

ssh-keygen -t ed25519 -C "your_email@example.com"
 
Explanation:

- ed25519 is a modern, secure algorithm

- Email is used as key label
 
Press Enter for:

- File location (default)

- Passphrase (optional)
 
--------------------------------------------------
 
### Step 2: Start SSH Agent
 
Command:

eval "$(ssh-agent -s)"
 
Purpose:

Starts SSH agent to manage keys securely.
 
--------------------------------------------------
 
### Step 3: Add SSH Key to Agent
 
Command:

ssh-add ~/.ssh/id_ed25519
 
Result:

Private key is loaded into SSH agent.
 
--------------------------------------------------
 
### Step 4: Copy Public Key
 
Command:

cat ~/.ssh/id_ed25519.pub
 
Purpose:

Public key will be added to GitHub account.
 
--------------------------------------------------
 
### Step 5: Add SSH Key to GitHub
 
Path:

GitHub → Settings → SSH and GPG keys → New SSH key
 
Steps:

- Title: Any meaningful name (e.g. office-linux)

- Key type: Authentication key

- Paste public key

- Save
 
--------------------------------------------------
 
### Step 6: Test SSH Connection
 
Command:

ssh -T git@github.com
 
Expected Output:

Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
 
Meaning:

SSH authentication is working correctly.
 
--------------------------------------------------
 
### Step 7: Use SSH Remote URL
 
Check current remote:

git remote -v
 
Change HTTPS to SSH:

git remote set-url origin git@github.com:<USERNAME>/future-proof-devops.git
 
Verify:

git remote -v
 
--------------------------------------------------
 
### Learning Summary (SSH)
 
- SSH uses key-based authentication

- Public key is stored on GitHub

- Private key stays on local system

- SSH is more secure and professional than HTTPS
 
--------------------------------------------------
 
### Common SSH Issues
 
Issue:

Permission denied (publickey)
 
Possible Causes:

- SSH key not added to GitHub

- Wrong key loaded in SSH agent

- Using HTTPS URL instead of SSH
 
--------------------------------------------------
 
### Interview Questions (SSH)
 
Q: Why is SSH preferred over HTTPS in Git?

A: Because SSH is more secure and does not require repeated authentication.
 
Q: Where is the private SSH key stored?

A: On the local system inside ~/.ssh directory.
 
Q: Can the same GitHub account be used on multiple systems with SSH?

A: Yes, by adding separate SSH keys for each system.


*** Production Insight:

In real-world DevOps environments, Git is not just used for code,
but also for managing infrastructure as code (IaC), CI/CD pipelines,
and configuration management.
 
==================================================

## PHASE 2: LINUX (ZERO -> ADVANCED)

==================================================
 
## DAY 1: LINUX FOUNDATIONS
 
### What is Linux?

Linux is an open-source operating system kernel used to manage system resources.
 
### Why Linux for DevOps?

- Most servers run Linux

- Stable and secure

- Automation-friendly
 
--------------------------------------------------
 
### Linux Filesystem Basics
 
/       → Root directory

/home   → User home directories

/root   → Root user home

/etc    → Configuration files

/var    → Logs and variable data

/bin    → Essential commands

/tmp    → Temporary files
 
--------------------------------------------------
 
### Basic Commands Practiced
 
pwd     → Show current directory

ls      → List files

ls -l   → Detailed listing

ls -a   → Show hidden files

cd /    → Go to root

cd ~    → Go to home directory
 
--------------------------------------------------
 
### Interview Questions (Day 1)
 
Q: What is Linux?

A: An open-source operating system kernel.
 
Q: Where are system configuration files stored?

A: /etc
 
==================================================

==================================================
 
## DAY 2: FILES & DIRECTORIES
 
### Creating Files and Directories
Commands:
mkdir <dir>
touch <file>
 
--------------------------------------------------
 
### Copying Files and Directories
Commands:
cp file target/
cp -r dir target/
 
--------------------------------------------------
 
### Moving and Renaming
Command:
mv oldname newname
 
--------------------------------------------------
 
### Deleting Files and Directories
Commands:
rm file
rm -r directory
 
Note:
Deletion in Linux is permanent.
 
--------------------------------------------------
 
### Absolute vs Relative Paths
Absolute path starts from /
Relative path starts from current directory
 
--------------------------------------------------
 
### Wildcards
*     → matches any string
*.log → matches all .log files
 
--------------------------------------------------
 
### Interview Questions (Day 2)
 
Q: How do you copy a directory?
A: Using cp -r
 
Q: How do you rename a file?
A: Using mv
 
Q: Difference between absolute and relative path?
A: Absolute starts from /, relative from current directory
 
================================================== 
=======
==================================================

## PHASE 2: LINUX FUNDAMENTALS (SYSTEM CORE)

==================================================

## DAY 1: INTRODUCTION TO LINUX

### What is Linux?

Linux is an open-source operating system kernel that manages hardware resources and allows software to run.

It acts as a bridge between hardware and applications.

--------------------------------------------------

### Why Linux is Important?

- Used in servers, cloud, DevOps, and enterprise systems
- Highly stable and secure
- Open-source and customizable
- Core skill for DevOps engineers

--------------------------------------------------

### Linux Distributions

Examples:
- Red Hat Enterprise Linux (RHEL)
- Ubuntu
- CentOS
- Oracle Linux

--------------------------------------------------

### Linux Architecture

User → Shell → Kernel → Hardware

- Shell: Command interface (bash)
- Kernel: Core system (process, memory, hardware control)
- Hardware: Physical resources

--------------------------------------------------

### Interview Questions (Day 1)

Q: What is Linux?  
A: Linux is an open-source operating system kernel that manages system resources.

Q: Why is Linux important in DevOps?  
A: Because most servers, cloud platforms, and DevOps tools run on Linux.

==================================================

## DAY 2: BASIC LINUX COMMANDS

### File & Directory Commands

Commands:

pwd  
ls  
ls -l  
ls -a  
cd  
mkdir  
rm -rf  
cp  
mv  

--------------------------------------------------

### Explanation

- pwd → shows current directory  
- ls → lists files  
- ls -l → detailed listing  
- ls -a → shows hidden files  
- cd → change directory  
- mkdir → create directory  
- rm -rf → remove files/directories  
- cp → copy files  
- mv → move/rename files  

--------------------------------------------------

### Interview Questions (Day 2)

Q: What does ls -l show?  
A: Detailed file information including permissions, owner, size, and date.

Q: Difference between cp and mv?  
A: cp copies files, mv moves or renames files.

==================================================

## DAY 3: FILE SYSTEM STRUCTURE

### Important Directories

| Directory | Purpose |
|----------|--------|
| / | Root directory |
| /home | User home directories |
| /etc | Configuration files |
| /var | Logs and variable data |
| /tmp | Temporary files |
| /usr | Applications |
| /bin | Basic commands |

--------------------------------------------------

### Real-World Understanding

- /var/log → used for troubleshooting  
- /etc → contains system configuration  
- /home → user data  

--------------------------------------------------

### Interview Questions (Day 3)

Q: What is /etc directory?  
A: It contains system configuration files.

Q: Where are logs stored in Linux?  
A: /var/log

==================================================

## DAY 4: USERS & GROUPS

### Create User

Command:
useradd username  
passwd username  

--------------------------------------------------

### Create Group

Command:
groupadd groupname  

--------------------------------------------------

### Add User to Group

Command:
usermod -aG groupname username  

Explanation:
- -a → append (do not remove existing groups)  
- -G → secondary group  

--------------------------------------------------

### Check User Info

Commands:
id username  
groups username  

--------------------------------------------------

### Real-World Note

Without -a option, usermod removes user from all existing groups.

--------------------------------------------------

### Interview Questions (Day 4)

Q: What is the difference between primary and secondary group?  
A: Primary group is default group; secondary groups are additional groups assigned to user.

==================================================

## DAY 5: FILE PERMISSIONS (CORE CONCEPT)

### Permission Structure

Example:
-rwxr-xr--

Breakdown:
- Owner (user)
- Group
- Others

--------------------------------------------------

### Permission Values

| Symbol | Value |
|--------|------|
| r | 4 |
| w | 2 |
| x | 1 |

--------------------------------------------------

### Octal Representation

| Number | Meaning |
|--------|--------|
| 7 | rwx |
| 6 | rw- |
| 5 | r-x |
| 4 | r-- |
| 0 | --- |

--------------------------------------------------

### chmod Command

Numeric:
chmod 755 file  

Symbolic:
chmod u+x file  
chmod g-w file  

--------------------------------------------------

### chown Command

chown user file  
chown user:group file  

--------------------------------------------------

### chgrp Command

chgrp group file  

--------------------------------------------------

### Directory Permission Logic

- Execute (x) → enter directory  
- Read (r) → list files  
- Write (w) → create/delete files  

--------------------------------------------------

### Interview Questions (Day 5)

Q: What does chmod 755 mean?  
A: Owner has full access, group and others have read and execute.

Q: Why is execute required on directory?  
A: To enter or traverse the directory.

==================================================

## DAY 6: SHARED DIRECTORY & SPECIAL PERMISSIONS

### Shared Directory Setup

Commands:

groupadd continues  

usermod -aG continues user1  
usermod -aG continues user2  

mkdir /shared  
chown :continues /shared  
chmod 2770 /shared  

--------------------------------------------------

### SGID (Set Group ID)

Command:
chmod 2770 directory  

Explanation:
New files inherit the directory’s group.

--------------------------------------------------

### Sticky Bit

Command:
chmod 1777 directory  

Explanation:
Users cannot delete other users' files.

Example:
/tmp directory  

--------------------------------------------------

### SUID (Set User ID)

Command:
chmod 4755 file  

Explanation:
File runs with owner's privileges.

Example:
/usr/bin/passwd  

--------------------------------------------------

### Real-World Mistake

Shared directory inside /home may fail due to parent directory permission.

--------------------------------------------------

### Interview Questions (Day 6)

Q: What is SGID?  
A: It ensures new files inherit the directory group.

Q: What is sticky bit?  
A: It prevents users from deleting others' files.

Q: Why is /tmp set to 1777?  
A: To allow all users to write but prevent deletion of others' files.

==================================================  
(Add Linux fundamentals and improve Git notes)
