## **\*\*\*\*\*Day-02:\*\*\***

*What is GIT?*\*\*
Git is a distributed version control system that tracks changes in source code and files, allowing multiple developers to collaborate and maintain the complete history of a project.

&#x20;Example



Suppose I develop a login feature.



Commit 1 → Login page created



Commit 2 → Password validation added



Commit 3 → OTP feature added



If Commit 3 introduces a bug, Git allows me to compare changes or restore a previous working version.



***Why Do we use Git?***
we use git for the tracking purpose of our files and project. Git acts like an single source of entire project.
All the files related to project can be found in the git, files like
Automation Scripts
Data
Application Code
Docker files
Kubernetes YAML file
Terraform Code files
Jenkins pipelines

shell Scripts

Infrastructure configuration



***What is version control?***

Version Control is the process of tracking changes made to files over time. Each saved state is called a version, allowing us to compare, restore, or collaborate on changes.



***Explain the Git architecture.***
Work Directory - the repository where you are working currently
Staging area - is the area where all the changes u made are waiting to be saved after git add, as they wont get added or merged until u commit

Local Repository  - This is the local location in your device
Remote Repository - This the repository where your all changes will get saved in the GitHub



***Difference between Git and GitHub.***

Git is a version control system that tracks the changes in code where GitHub is the workspace or remote repo where all the changes are saved. in simply we can say git is a tool and GitHub is a cloud platform that hosts git repos
Git	                                              GitHub

Version Control System	                  Cloud platform for hosting Git repositories

Installed on your computer	          Accessible through the internet

Tracks code changes	                  Stores and shares repositories

Works offline	                          Requires internet for syncing



## **\*\*\*Day-03:\*\*\***



Todays Learnings-

\- git status

\- git add

\- git commit

\- git log

\- git diff

Working architecture:

Edit File

&#x20;    │

&#x20;    ▼

Working Directory

&#x20;    │

git add

&#x20;    ▼

Staging Area

&#x20;    │

git commit

&#x20;    ▼

Local Repository

&#x20;    │

git push

&#x20;    ▼

GitHub Repository

**git Status-** Says the current status of the repository, whether the changes exist to be committed.
It tells you:

Current branch

Modified files

Untracked files

Staged files

Whether your branch is up to date

**When do we use it?** - Almost every time before committing.



**git Diff-** says the exact difference between the last commit and the current file

\- changed or replaced or removed line

\+ New Lines added

In real time, devs use this comment before each commit

**git add-**  moves the changes from working directory to the staging area

**git commit-** makes the snapshot of staged changes and stores in the local git repository.
\*\*git log --oneline -\*\*shows all the history of commits, displays the commit id and commit msg in one line

**git log -** shows all the history of commits in detail.
**git show-**  shows the details of commits, we can give the commit id to get the details of specific commit
It displays:

Commit ID

Author

Date

Commit message

Files changed

Exact lines added and removed

if we dont give commit id, git log and git show might works the same.

**git Push-** Pushes the changes (snaped changes) from local to the remote(GITHUB).





## **\*\*\*DAY-04\*\*\***

**# Branches**



**## What is a Branch?**



A branch is an independent line of development in Git. It allows developers to work on new features, bug fixes, or experiments without affecting the main project. Each branch has its own commit history.



\---



**## Why do We Use Branches?**



Branches are used to:

\- Develop new features safely.

\- Fix bugs without affecting the stable code.

\- Allow multiple developers to work on the same project simultaneously.

\- Test new changes before adding them to the main branch.



**---**



**## Difference Between `main` and a Feature Branch**



| Main Branch | Feature Branch |

|-------------|----------------|

| Contains stable and tested code. | Used to develop a specific feature or fix. |

| Represents the production-ready version of the project. | May contain unfinished work. |

| Developers usually avoid making direct changes. | Developers make changes and commit their work here. |

| Receives changes only after testing and code review. | Merged into `main` after the work is completed. |



**---**



**## Benefits of Branching**



\- Keeps the `main` branch stable.

\- Allows multiple developers to work independently.

\- Makes collaboration easier.

\- Prevents unfinished features from affecting production.

\- Makes testing and code reviews easier before merging.



**---**



**## Common Git Branch Commands**



\### View all local branches



```bash

git branch - will say which branch u r working

```



\### Create a new branch



```bash

git branch feature-login (only to switch to the already created branch)

```



\### Create and switch to a new branch



```bash

git switch -c feature-login (to create a branch for the first time)

```



\### Switch to an existing branch



```bash

git switch feature-login

```



\### (Older command) Switch branches



```bash

git checkout feature-login

```



\### Show commit history



```bash

git log --oneline  (shows the commit history in single line along with @Head and message)

```



\### Push a branch to GitHub



```bash

git push -u origin feature-login

```



\---



**## Practical Observation**



When I created the `feature-notes` branch, Git did not create another copy of the project. Instead, it created a new pointer to the current commit.



When I switched from `feature-notes` to `main`, the changes I made disappeared because `main` was pointing to an older commit.



When I switched back to `feature-notes`, the changes reappeared because that branch pointed to the newer commit containing my work.



This helped me understand that each branch has its own commit history, and Git updates the working directory based on the branch I switch to.


1. Git Merge

Git Merge is the process of combining changes from one branch into another branch.

Most commonly:

feature branch
        │
        ▼
      git merge
        │
        ▼
main branch

It is used after completing a feature.

2. Why do we use Merge?

Instead of every developer working directly on the main branch:

Developers create their own feature branches.
Work independently.
Test their changes.
Review the code.
Merge only after everything works correctly.

Benefits:

Keeps the main branch stable.
Prevents breaking the application.
Makes collaboration easier.
Makes code reviews possible.
3. Fast-Forward Merge

A Fast-Forward Merge happens when:

No new commits were added to the main branch after creating the feature branch.

Instead of creating another commit, Git simply moves the main branch pointer forward.

Example:

Before

main
 │
A ---- B

feature
        │
        C

After

main
        │
A ---- B ---- C
Important Point

A Fast-Forward Merge does not create a new merge commit.

Git simply updates the branch pointer.

4. Merge Conflict

A Merge Conflict happens when:

Two branches modify the same line of the same file differently.

Git cannot decide which version is correct.

So Git stops the merge and asks the developer to resolve it manually.

5. Conflict Markers

Git inserts markers like:

<<<<<<< HEAD
Current branch changes
=======
Incoming branch changes
>>>>>>> feature_branch

Meaning:

HEAD

→ Current branch (main)

=======

→ Separator

>>>>>>> feature_branch

→ Incoming changes

The developer removes these markers after deciding what the final content should be.

Steps to Resolve a Merge Conflict
Merge the branch.
Git reports the conflict.
Open the conflicted file.
Find the conflict markers.
Decide which code to keep.
Remove all markers.
Save the file.
Stage the file.
git add hello.txt
Commit
git commit -m "Resolved merge conflict"
Commands Learned
git merge <branch>

Merge another branch into the current branch.

git switch main

Switch to the main branch.

git status

Shows merge status and conflicts.

git log --oneline --graph

Shows commit history as a graph.

git push origin main

Push local changes to GitHub.

Practical Knowledge I Gained Today
✅ I successfully performed a Fast-Forward Merge locally.

Git displayed:

Fast-forward

Meaning:

The merge happened successfully without creating another commit.

I learned why Git said
nothing to commit

Initially I thought I needed another commit.

Later I understood:

A Fast-Forward Merge does not create a new commit because the latest commit already exists in the feature branch.

Git only moves the branch pointer.

I got a Push Rejected Error

Git displayed:

Updates were rejected because the remote contains work that you do not have locally.
Why?

I had already merged the branch on GitHub using Compare & Pull Request.

GitHub created a merge commit.

My local repository did not yet have that commit.

Therefore Git rejected the push.

Important Lesson

There are two ways to merge branches.

Method 1

Local Merge

git switch main
git merge feature_branch
git push origin main

Everything happens on my computer.

Method 2

GitHub Pull Request

Push feature branch
      ↓
Create Pull Request
      ↓
Code Review
      ↓
Merge on GitHub
      ↓
git pull origin main

This is the workflow used by most companies because it supports:

Code Reviews
CI/CD
Team Approval
Merge History
Difference I Learned
Local Merge	GitHub Pull Request
Uses git merge command	Uses Compare & Pull Request
Happens on local machine	Happens on GitHub
Mostly for learning/small projects	Used in professional teams
No review process	Includes code review before merging

###DAY06###
1. What is a Remote Repository?

A remote repository is a Git repository hosted on a remote server (e.g., GitHub, GitLab, Bitbucket).

It allows developers to:

Share code
Collaborate with team members
Backup projects
Access the project from anywhere
Example
Local Repository (Laptop)
          │
      git push
          ▼
GitHub (Remote Repository)
          ▲
      git pull
          │
2. Local Repository vs Remote Repository
Local Repository	Remote Repository
Stored on your computer	Stored on GitHub
Used for development	Used for collaboration
Can work offline	Internet required to sync
Contains your local commits	Contains shared project history
3. What is origin?

origin is the default name Git gives to the remote repository.

Check your remote:

git remote -v

Example:

origin  https://github.com/username/Devops_Practice.git (fetch)
origin  https://github.com/username/Devops_Practice.git (push)
4. git push

Uploads your local commits to the remote repository.

Syntax
git push origin main

Example:

Laptop
     │
git push
     ▼
GitHub
5. git pull

Downloads the latest changes from the remote repository and merges them into your local branch.

Syntax
git pull origin main

Example:

GitHub
     │
git pull
     ▼
Laptop
6. git clone

Copies an existing remote repository to your computer.

Syntax
git clone <repository-url>

Example:

git clone https://github.com/reena/Devops_Practice.git

Git creates a complete copy of the repository, including its history.

7. Basic Git Collaboration Workflow
Developer
     │
Modify files
     │
git add
     │
git commit
     │
git push
     ▼
GitHub
     ▲
git pull
     │
Other Developers
8. Common Commands
git remote -v

Shows configured remote repositories.

git push origin main

Uploads local commits.

git pull origin main

Downloads latest changes.

git clone <url>

Copies a remote repository.

git remote show origin

Displays detailed information about the remote.

🌍 Real-Time Example

Suppose three developers are working on the same project:

Developer A → Login Module
Developer B → Dashboard
Developer C → Payment Module

Workflow:

Developer A
        │
git push
        ▼
GitHub
        ▲
git pull
        │
Developer B

This ensures everyone works with the latest version of the project.



###DAY06###
UNDO OPERATIONS

Sometimes, mistakes like below may happen:
1. Editing a wrong file
2. wrong file got staged
3. Bug creating work got pushed
4. Make a wrong commit

To Undo these there are multiple commands. each of these mistakes of different ways to undo them

Which Command Should You Use?
Situation	                                                 Command
Modified a file but don't want the changes	             git restore file.txt
Staged the wrong file	                                     git restore --staged file.txt
Wrong local commit (not pushed)	                             git reset HEAD~1
Undo a pushed/shared commit	                             git revert <commit-id>
See commit history	                                     git log --oneline
Inspect a commit	                                     git show <commit-id>
 
Reset vs Revert
Git Reset	                                         Git Revert
Moves branch backward                              Creates a new undo commit
Rewrites history	                           Preserves history
Best before pushing	                           Best after pushing/shared branches
Risky in team environments	                   Safe for collaboration