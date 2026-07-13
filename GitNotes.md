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



