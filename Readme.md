init-git
===
 *Crash Course Git Tutorial*

Intro
---
The goal of this document is to provide a brief but thorough introduction to git. The first section focuses on how to setup git and make basic changes. The second section works though branches and how to merge them in a collaboratory enviorment. 

Initialization
---
The first step in using git is to create a repository. A repository (or repo) is a directory that includes all of the code that your project needs. A repo may also include additional project files or assets, but usually doesn't include compiled binaries or executables. 

To create a repo in the current directory use the command:

`git init ` 

This creates an empty repository

To copy a repository from a *remote*(from an external source) use the command:

`git clone https://URL.com/REPOSITORY`

This creates a directory that contains the repo with all associated files. 

> A GitHub repo usually exists at the URL: https://github.com/USERNAME/REPOSITORY 
> The URL for this repo would be https://github.com/eduxstad/init-git

Commiting Changes
---
When using git, all changes are stored in groups of modifications called "commits." A commit, therefore, is a group of changes to the repo, usually grouped by intent. For example, the changes necessary to add a feature would be stored in a commit. Commits also include a brief message about the contents of the change. (This message is usally specific but brief and some times in the form "this commit will `COMMIT_MESSAGE`")

There are two parts to commiting changes with git. The first is to add all the files associated with the change with the command:

`git add FILENAME `


`git rm FILENAME ` 

will remove that file from the commit.

Once you have added all the files necessary to commit, use the command

`git commit -m 'COMMIT_MESSAGE' `

This will output the number of changes created and more associated information about the commit. 

> Note: Use `git status ` to check which files have been added, created, or removed from the commit before commiting. 
> The command `git log` will list the commit history of the repository, along with the associated authors of the commits.

Uploading/Receiving Changes
---
To upload a repository to a remote url (such as GitHub) use the command

`git push REMOTE BRANCH `

Pushing uploads all local commits to the servers repository in essence syncing the servers repository to your machine. The remote is the server that you want to push to and the branch is the branch from which you are pushing (Usually "master").

To receive commits and update the local repository use the command

`git pull REMOTE BRANCH`

This recieves all commits from the remote specified and applies them to the branch specified. 
> In most cases, the branch would be "master" and the remote is "origin" which would make the command `git push origin master`

To set or remove a remote url use the command

`git remote add NAME URL `

or 

`git remote remove NAME URL `

Branches
---
Sometimes it is necessary to create a testing enviorment to try out different features, or to be free to make modifications without worrying about creating problems for other collaborators. Braches are copies of the repo that are independent from one another and which can be switched at will. 

To switch to a different branch

`git checkout BRANCHNAME `

To create a new branch 

`git checkout -b BRANCHNAME `

When creating a new branch, the state of the new branch will match the state of the branch where the new branch was created. When switching between branches, files that are commited (tracked) by git will change, while untracked files will remain the same, no matter which branch the repo is at. 

> Note: The default branch of a repo is "master"

Help
---
To list the documentation for any git command, or to view options and syntax use the command

`git help COMMAND `

This command pulls up the documentation for a command, use hjkl or the scroll wheel to navigate and press q once finished to return to the command line. (similar to man COMMAND on *nix) 

