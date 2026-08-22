# Git

Git is a distributed **version control system (VCS)** used to track changes to files and collaborate with other developers.

Git allows you to:

- Track changes to a project
- Create versions of your code
- Work on features independently
- Collaborate with other developers
- Revert changes when something goes wrong
- Connect local repositories to remote repositories such as GitHub or GitLab

## 1. Git Repository

A **Git repository** is a directory that Git tracks for changes.

##  Initialize a Repository

To turn an existing project folder into a Git repository:

```
git init

```

Check the repository status:
```
git status
```
## Useful Concept

**Working directory → Staging area → Repository**

```
Make changes
    ↓
git add
    ↓
Staging area
    ↓
git commit
    ↓
Local repository
    ↓
git push
    ↓
Remote repository
```

## 2. Tracked vs Untracked Files

Tracked file - A tracked file is a file that Git already knows about and monitors for changes.
For example, after adding a new file:
```
git add filename
```
Git begins tracking that file.
Once a file is tracked, modifying it does not make it untracked again.

Untracked file - An untracked file is a new file in your project directory that Git does not yet know about.

## 3. Staging Environment

Staging Environment- The staging area is a waiting area where you select which changes will be included in your next commit.

### Stage A File

```
git add filename
```
### Stage All Changes
```
git add .

or 

git add -A
```
### Unstage A File
```
git restore --staged filename
```

## 4. Commit

A commit is a save point in your project it records a snapshot of your files at a certain time, with a message describing what changed.

### Create a Commit
```
- git commit -m "message"
```
### Commit All Tracked Changes
```
- git commit -a -m "message" 
```
### View Commit History
```
- git log - See commit history.
```
## 5. Remote Repository

A remote repository is a version of your Git repository stored somewhere else, usually on a platform such as GitHub or GitLab.
A remote allows you to:

- Back up your code
- Collaborate with other developers
- Share your project
- Push and pull changes
- A common remote name is:
**origin**

### View Remotes 
```
git remote -v
```
### Add a remote 
```
git remove add origin <repository-url>
```

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




