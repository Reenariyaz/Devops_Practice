## Interview Questions:

&#x20;

1. **What problem does Git solve?**

**Interview Answer**



Git solves the problem of tracking changes in source code and files. It helps developers collaborate, maintains the complete history of a project, allows reverting to previous versions if something goes wrong, and prevents code from being overwritten when multiple developers work on the same project.



Real-Time Example



Imagine three developers are working on the same application:



Developer A → Login Feature

Developer B → Payment Module

Developer C → Dashboard



Without Git, their changes could overwrite each other.



With Git, everyone's work is tracked and merged safely.



2\. **What is Version Control?**

**Interview Answer**



Version Control is a system that records changes made to files over time. Each saved state is called a version, allowing developers to compare changes, restore previous versions, and collaborate efficiently.



Example

Version 1

↓



Version 2



↓



Version 3



↓



Version 4



If Version 4 has a bug, Git allows you to go back to Version 3.



3\. **Difference between Git and GitHub?**

&#x20;   **Git**	                                             **GitHub**

Version Control System	                 Cloud platform for hosting Git repositories

Installed on your computer	         Accessible through the internet

Tracks code changes	                 Stores and shares repositories

Works offline	                         Requires internet for syncing

One-line Interview Answer



Git is a distributed version control system, whereas GitHub is a cloud platform used to host and collaborate on Git repositories.



**4. What is a Repository?**

**Interview Answer**



A repository (repo) is a storage location that contains a project's files, folders, and the complete history of changes tracked by Git.



It includes:



Source code

Configuration files

Commit history

Branches

Tags

Example

Devops\_Practice/



README.md



GitNotes.md



Docker/



AWS/



Terraform/



This entire folder is your repository.



**5. What is the Staging Area?**

**Interview Answer**



The Staging Area is an intermediate area where changes are prepared before being committed to the local repository. It allows developers to choose which changes should be included in the next commit.



**Workflow**

Working Directory

&#x20;       │

git add

&#x20;       ▼

Staging Area

&#x20;       │

git commit

&#x20;       ▼

Local Repository

Real-Time Example



Suppose you modified three files:



GitNotes.md

DockerNotes.md

README.md



But today you only want to save changes to GitNotes.md.



You run:



git add GitNotes.md

git commit -m "Updated Git notes"



Only GitNotes.md is committed. The other files remain unchanged until you're ready to commit them.



🎯 Interview Tip



Many interviewers ask:



**"Why can't Git commit directly without a staging area?"**



Answer:



The staging area gives developers control over what goes into a commit. It allows us to review and group only the relevant changes instead of committing every modified file.



1\. What is a remote repository?



A remote repository is a Git repository hosted on a server (such as GitHub) that allows developers to collaborate and share code.



2\. What is the difference between git push and git pull?

git push uploads local commits to the remote repository.

git pull downloads and merges the latest changes from the remote repository into the local repository.

3\. What is git clone?



git clone creates a complete copy of an existing remote repository on your local machine.



4\. What is origin?



origin is the default name given to the remote GitHub repository.



5\. Why do companies use GitHub?



Companies use GitHub to:



Collaborate on code

Store repositories

Review code through Pull Requests

Track issues

Integrate CI/CD pipelines

Maintain version history



