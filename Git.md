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
