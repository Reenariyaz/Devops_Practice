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


##DAY05##

Git Merge - combining changes that implemented in one branch to other branch
syntax- git merge <branch name to be merged>

Why do we merge branches - as to avoid the breakage of application, allows multiple developers work independently on new features and bug fixes, helps reviewers in reviewing the code.

Fast-Forward Merge - when there is no commits on main branch, till the merging branch commits then the main branch points to the new branch instead of new branch combining to the main branch.

Merge Conflict-  this conflict occurs when changes are made on same file or feature differently by multiple developers 

We can resolve merge conflict- 
 merge the changes
 open conflicted file
 remove the conflict markers (<<<<<, ========, <<<<<<<)
 keep the required code
 save the file
 stage the file
 commit the changes

Common git merge commands:
git merge <branch name>
git status

git merge Architecture- 

create a new branch
work on the branch and commit
switch to main branch
merge the branch
resolve the merge conflict (if any)
commit 
push


Real-World Example

Imagine three developers working on an online banking application:

Developer A → Login feature
Developer B → Dashboard
Developer C → Loan module

Each developer creates a separate feature branch and works independently. Once a feature is complete, it is reviewed and merged into the main branch. If two developers modify the same part of a file, Git raises a merge conflict, which is resolved before deployment. After successful merging, the CI/CD pipeline builds, tests, and deploys the application.





