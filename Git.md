### Git


Initialize Git 

syntax: git init 

A git repository is a folder that git tracks for changes.

Tracked file - is a file that git is watching for changes, to make a file tracked, you need to add it to the staging area.

Untracked file - is any file in your project folder that git is not yet tracking. these are files created and copied into the folder but haven't told git to watch.

### Staging Environment

Staging Environment- is like a waiting room for your changes.

syntax: 
- git add (filename) - Stage a file.
- (git add -- all) or (git add -A) - Stage all changes.
- git status - Check which files are tracked.
- git restore -- staged (filename) - Unstage a file.

### Commit

A commit is a save point in your project it records a snapshot of your files at a certain time, with a message describing what changed.


syntax:
- git commit -m "message"
- git commit -a -m "message" - Commit all tracked changes (skip staging)
- git log - See commit history.

## Push

When we have made changes locally, we want to update our remote repository with the changes.

Transferring our local changes to our remote is done with a push command.

Syntax:

- git push origin - This command pushes your current branch to the remote repository named origin.

## Gitignore

The .gitignore file tells Git which files and folders to ignore (not track).

This is useful for keeping log files, temporary files, build artifacts, or personal files out of your repository.

### Create a gitignore file
syntax: 

- touch .gitignore

### When to use gitignore

- When you want to keep sensitive, local, or unnecessary files out of your repository.
- When sharing a project with others and want to avoid cluttering Git history.
- When working with build tools or editors that create extra files.


### Ignore Folders

- Use a trailing slash e.g. temp/

### Wildcards and Patterns

- (*) matches any number of characters e.g. *.txt - all .txt files
- ? matches a single character e.g. my?ile.txt - myfile.txt, mygile.txt, myhile.txt.

## Cloning
A clone is a full copy of a repository, including all logging and versions of files.

syntax:
- git clone url

## Branching

A branch is like a separate workspace where you can make changes and try new ideas without affecting the main project.

### Common Reasons 

- Developing a new feature
- Fixing a bug
- Experimenting with ideas

Syntax:

- git branch branch_name
- git branch - Lists all branches.
- git checkout branch_name - Switch between branches.
- git branch -d - Deletes a branch.
- git checkout -b - Creates an emergency branch.

## Merging

Merging in Git means combining the changes from one branch into another.

Syntax: 

- git merge - merge a branch into your branch.

## Forking and Pull Request

A fork is a copy of a repository.

This is useful when you want to contribute to someone else's project or start your own project based on theirs.

Fork is not a command in Git, but something offered in GitHub and other repository hosts.

After the changes have been committed, we can send a pull request to the original repository.

## Other Useful Git Commands

- git help --all -  List all possible git commands.




