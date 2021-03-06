# First commands

### Usage

```bash
$ git
```

### Help

```bash
$ git <command> --help
$ git <command> -h
```

### git version

```bash
$ git --version
```

# Configurations

- [Customizing Git - Git Configuration](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration)
- [git-config docs](https://git-scm.com/docs/git-config)
### Config levels

- ```---project``` = project specific
- ```---global``` = user specific (git.config file in home directory)
- ```---system``` = system wide

### Global configs

```bash
$ git config --global user.name "name"
$ git config --global user.email "a@a.com"Working with 
$ git config --global color.ui auto
$ git config --global core.editor vim
```

# Repositories

## Create bare repository - not a 'working copy'

### Notice that the files structure contains file normally found in the .git folder of a working repository

```bash
$ git init --bare myapp.git
```

### Clone bare respository to create a working copy

```bash
$ git clone --local myapp.git myapp
```

## Tracking files

### Add file to repository

```bash
$ touch README.md
```

### Stage changes - Add file to staging area

```bash
# Add single file
$ git add README.md

# Add all files
$ git add -A
```

### Unstage changes

```bash
$ git reset
```

### View status message

```bash
$ git status
```

### Commit changes

```bash
# commit single file fromt he staging area
$ git commit README.md -m "Added README.md" 

# commit (and stage) all changes
$ git commit -a --message "Added stuff" # or -m to add commit message
```

### View Git logs

```bash
$ git log
```

### View unstaged edits

```bash
$ git diff
```

# Remotes

- If you create a repository on Github and clone it locally, the repository on Github will be named 'origin'
- If you create a bare respository locally and clone that to create a working copy, the bare repository will be named 'origin'

### Common operations on remotes

- Add
- Remove
- Show
- Rename

### Show list of remotes

```bash
$ git remote show
```

### Show information for a specific remote

```bash
$ git remote show origin
```

### Pull (fetch/merge) changes from remote

#### To pull changes use ```git pull <remote_name>```

- This will 'fetch' and 'merge' changes from the remote to the local repository
- If you use ```git fetch <remote_name>``` then you are have to run ```git merge <remote_name>``` separately

```bash
$ git pull origin
```

### Push changes to remote

#### Use ```git push <remote_name> <branch>```

- ```master``` specifies the branch you are pushing
- if you do not specify a branch, and just use ```git push <remote_name>```, then all branches will be pushed to the remote

```bash
$ git push origin master
```

### Add new remote

#### Syntax: ```git remote add <remote_name> <path to repository>```

```bash
$ git remote add github https://github.com/christopherstavros/myapp.git
```

# Branching and Merging

### Documentation

- [Basic Branching and Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

### Adopt or develop a branching workflow that fits your needs.  Some examples include:

- [Git Feature Branch Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)
- [Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
- [Github Flow Workflow](https://guides.github.com/introduction/flow/)

### Create new branch

```bash
# Create and checkout branch with songle command
$ git checkout -b 1234

# This is shorthand for:
$ git branch 1234
$ git checkout 1234
```

### Switch branches

```bash
$ git checkout master
```

### Merge branches

First switch to (checkout) master branch (or target branch for the merge)

```bash
$ git merge 1234
```

### Delete local branch

```bash
$ git branch -d 1234
```

### Delete remote branch

```bash
$ git push origin --delete 1234
```

# More things to learn

- Conflict resolution
- Reverting changes
- Tags and releases
- Hooks

# Resources for further learning

- [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials)
- [Atlassian Git Cheat Sheet - PDF](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)
- [Git Feature Branch Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)
- [Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
- [Github Flow Workflow](https://guides.github.com/introduction/flow/)

