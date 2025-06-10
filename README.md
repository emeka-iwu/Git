# Git
Repo on the essentials of Git

# User config
git requires user to set up an identity using these 2 commands
- git config --global user.name 'user_name ', and 
- git config --global user.email 'email_address'. 
These 2 commands are used to set up user identity in git. The email should be same as that on github account.

# initialising
git init initialises a repo on current directory. this is only to be ran once

# synchronising
to sync a local repo to an already created online repo, git remote add origin git@github.com:username/repo.git  is used. However to clone all the files and its contents, git clone git@github.com:username/repo.git is used.

# checking synchronisation
git remote -v is used to see the source url for push and pull  

# branch
a branch is like an office within a repo. the standard branch in a repo is Main or Master. to command to view available branch on local is git branch, while to view branchs on remote is git branch -r. The command to create a new branch is git checkout -b branch_nam, while to switch to a branch is git checkout branch_name.
To rename the current branch, the commands is git branch -M newbranchname, and to delete a local branch is git branch -D branchname. However deleting a branch locally doesnt delete it online, hence to delete a file online, the commands are;
- git push origin --delete branchname 
- git push origin :branchname

# staging
staging involves adding a file to an area before it is ready to be saved (commit) the command is git add . or git add file

# commiting
after files have been staged, they need to be commited (saved) using the commit command git commit -m 'message'. however to stage and commit a tracked files is git commit -am 'message'. this wont work for new files as new files need to be tracked first using the git add command.

# merging
merging incloves updating the current branch with a more updated branch. The command is git merge branchname

# log and status
to view the status of a branch like files to be staged/commited, the command to use is git status. Also, to view the log of a branch and see its activites and commit history, the commands are;
- git log
- git log --oneline (for a more readable/simple format)

# merge tools
during merging error can occur and to resolve this in the cli, the git merge tools is required, and my personal fav is meld. first to set and configure this tool, the command is;
- git config --global merge.tool meld
then when a merge error occurs, the command to examine and resolve it is git mergetool

# diff command
the git diff command is used to show the difference between elements in a repo. this can be files, branches, commits. the commands are;
- git diff --staged (this shows the difference between a files in a branch that has been eited and staged but not yet commited.
- git diff branchone branchtwo (shows the difference between two branches)

# .gitignore
certai files in a repo do not need tracking (staging and comiting). the gitignore file is used to manage these untracked files by listing theses files in separate lines in the .gitignore file. file can be created using touch .gitignore and opening the file and listing the untracked files in separate lines.

# Stashing
when working on files in a branch, errors might come up when tryig to checkout before staging and commiting an edited file. Stash allows a branch to be cached with all the edits before checking out to another branch. the commands are;
- git stash (to save the state of a branch before checking out)
- git stash pop (to resume on a branch)
- git --list (shows the list of stashes in a branch)

# Push / Pull Requests
Pull requests are used to pull files from an online repo branch. the command is 
- git pull origin branchname

Push requets are used to push branches to the online repo. It has a few commands;
- git push -u origin branchname (pushes a local branch to the online branch). the -u option is used to establish the destination branch. consequent push requests will not require a -u option as the destination branch has been established previously with -u
- git push -u origin localbranch:onlinebranch (this command is used if the loacl and online branches have different names)
- git push (this command is used when the -u orign branchname has been previously used to establish branch connection)
- git push --all origin (this is used to push all the branches in a repo) 

# Rebase
rebase is similar to merge but it is used to update a branch with another branch while keeping the commit history linear. this command is to be run with caution and should not be run fro the main or master branch. The command is git rebase branchname. 
