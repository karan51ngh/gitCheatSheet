# GIT CHEAT SHEET

- [Basics Of Git](#basics-of-git)
- [Three-Stage Architecture of Git](#three-stage-architecture-of-git)
- [Git File Status Lifecycle](#git-file-status-lifecycle)
    - [status](#git-status)
    - [add](#git-add)
    - [commit](#git-commit)
- [Git Configuration](#git-configuration)
- [Managing Git Repositories](#managing-git-repositories)
    - [init](#git-init)
    - [clone](#git-clone)
    - [fetch](#git-fetch)
    - [pull](#git-pull)
    - [push](#git-push)
- [Origin, Remote and Upstream](#origin-remote-and-upstream)
- [Git Branching](#git-branching)
- [Miscellaneous](#miscellaneous)


## BASICS OF GIT

- **Git** is a distributed version control system that allows developers to track changes in their code and collaborate on projects.
- **Repository**: A repository is a directory where all the files for a project are stored, along with a history of all the changes made to the files.
- **Commit**: A commit is a snapshot of all the files in the repository at a certain point in time. Each commit has a unique ID and a message describing the changes made.
- **Branch**: A branch is a separate line of development within a repository. By default, there is a "master" branch, but developers can create new branches to work on new features or bug fixes without affecting the main codebase.
- **Merging**: Merging is the process of taking the changes made in one branch and applying them to another branch.
- **Clone**: The `clone` command is used to copy a repository from a remote server to your local machine.
- **Add & Commit**: The `add` command stages changes, and the `commit` command saves those changes with a message describing what was done.
- **Push & Pull**: The `push` command uploads your commits to a remote repository, and the `pull` command downloads any new commits from the remote repository.

## THREE-STAGE  ARCHITECTURE OF GIT

Git has a three-stage architecture for managing changes to files in a repository.
The three stages are: Working Directory, Staging Area, and Git Repository.
- The **Working Directory** is where you make changes to files in your repository.
- The **Staging Area** is an intermediate stage where you select which changes to include in your next commit.
- The **Git Repository** is where Git permanently stores your files and the history of changes made to them. 

Git tracks changes in your Working Directory and displays them as "unstaged changes".
- Use `git add` to stage changes for the next commit.
- Use `git commit` to permanently save changes to the Git Repository.

## GIT FILE STATUS LIFECYCLE

The Git file status lifecycle describes the different states a file can be in when it is being tracked by Git. There are four main states in the Git file status lifecycle:

1. **Untracked**: A file is untracked when it is not yet being tracked by Git. Git is unaware of the file's existence.
2. **Modified**: A file is considered modified when changes have been made to it since the last commit.
3. **Staged**: A file is staged when it has been marked to be included in the next commit. The changes made to the file are included in the staging area.
4. **Committed**: A file is committed when the changes made to it have been saved to the Git repository.

- ##### `git status`: 
    >Shows the current status of your local repository. It displays information such as which branch you are currently on, which files have been modified or added, and which files are staged and ready to be committed. This command is useful to check the status of your changes before committing them.

- ##### `git add`: 
    >Used to add changes to the staging area. The git add command can be used to add individual files, multiple files, or even entire directories to the staging area.
    
    - `git add <filename>`: Stages the changes made to the specified file for the next commit.
    - `git add .` or `git add --all`: Stages all changes made to tracked files in the current directory and its subdirectories. It also stages any new untracked files that have been added to the repository.
- ##### `git commit`:
    >Used in Git to record changes to the local repository. Once changes have been added to the staging area using `git add`, they can be commited. This creates a new snapshot of the repository at the current state, and this snapshot is saved in the Git history.
    
    - `git commit`: If you enter `git commit` without any additional options, Git will open your default text editor and allow you to enter a commit message.
    - `git commit -m "commit message"`: Allows you to specify the commit message directly on the command line.
    - `git commit -a`: Automatically stages all modified and deleted files before creating the commit.

## GIT CONFIGURATION

The `git config` command is used to configure various settings and preferences for Git. This command can be used to set Git configuration at different levels, including system, global, and local.

- Set user name and email: Git username and email are used to identify the author of a commit. Git uses the username and email associated with your Git configuration to record the author of the commit. Git hosting services (such as GitHub) may use your email address to verify your identity for security purposes.
```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```
- Set default text editor:
```
git config --global core.editor nano
```
- Check current configuration:
```
git config --list
```
- To edit your global Git configuration file:
```
git config --global --edit
```

## MANAGING GIT REPOSITORIES

Git repositories are used to store and manage your Git projects. A Git repository contains all the files and folders in your project, as well as the revision history of each file.

- ##### `git init`:
    >Creates a new Git repository in a directory. It initializes a ".git" directory in the root of the project, which manages the repository's history, branches, and commits.

- ##### `git clone`: 
    >Creates a local copy of a remote Git repository. For example, to clone a remote repository called "my-repo" from GitHub, you can run:

```
git clone git@github.com:username/my-repo.git
```
- ##### `git fetch`: 
    >Downloads new changes from a remote Git repository, but does not apply them to your local repository. For example, to fetch new changes from the "origin" remote repository, you can run:

```
git fetch origin
```
- ##### `git pull`: 
    >Downloads new changes and updates your local repository with them. For example, to pull new changes from the "origin" remote repository into your current branch, you can run:

```
git pull origin
```
- ##### `git push`: 
    >Uploads local changes to a remote Git repository. For example, to push the current branch to the "origin" remote repository, you can run:

```
git push origin
```

## ORIGIN, REMOTE AND UPSTREAM

- In Git, "origin" is a default name for the remote repository where the local repository was cloned from. When you clone a Git repository, the remote repository you clone from is automatically assigned the name "origin". 
- You can use the name "origin" to refer to the remote repository when executing Git commands, such as pushing or pulling changes to and from the remote repository.
- `git remote` Allows you to manage the connections to remote Git repositories. With this command, you can list, add, rename, and remove remote repositories.
    - List all the remote repositories connected to your local repository:
    ```
    git remote -v
    ```
    - Add a new remote repository with the name <name>:
    ```
    git remote add <name> <remote_url>
    ```
    -  Rename a remote repository from <oldname> to <newname>.
    ```
    git remote rename <oldname> <newname>
    ```
    -  Display information about a specific remote repository, including it's branch mappings and the last time the remote repository was fetched.
    ```
    git remote show <name>
    ```
    - Remove the connection to a remote repository with the name <name> from your local Git repository.
    ```
    git remote remove <name>
    ```
- In Git, upstream refers to the original repository that a forked repository was created from. When you fork a repository on GitHub, the original repository is automatically added as a remote called "upstream".
- You can use the upstream repository to synchronize your forked repository with any changes made to the original repository. This is done by fetching the changes from the upstream repository and merging them into your local repository.
```
git fetch upstream
git merge upstream/<branch_name>
```
- To set the upstream repository for your local branch, you can use the following command:
```
git push --set-upstream <remote> <branch>
```

## GIT BRANCHING

Git branching is a feature that allows developers to work on different versions of a project simultaneously. You can create multiple branches, each with its own set of changes, and switch between them to work on different features or bug fixes. This helps to isolate changes and prevents conflicts between different parts of the project.

- Create a new branch:
```
git branch <branch-name>
```
- Switch to an existing branch:
```
git checkout <branch-name>
```
- Create a new branch and switch to it:
```
git checkout -b <branch-name>
```
- List all branches:
```
git branch
```
- Merge a branch into the current branch:
```
git merge <branch-name>
```
- Delete a branch:
```
git branch -d <branch-name>
```
- Delete a branch (even if it has unmerged changes):
```
git branch -D <branch-name>
```
- Rename a branch:
```
git branch -m <old-branch-name> <new-branch-name>
```

## MISCELLANEOUS

1. ##### `git diff`:  
    >Used to view the differences between the working directory and the staging area, or between the staging area and a previous commit.

    - By default, `git diff` shows the changes that are not yet staged.
    - use `--staged` or `--cached` for seeing the changes that have already been staged.
    - use the `--color` option to highlight the changes with colors.
2. ##### `git rm`: 
    >Used to remove files from the Git repository. It removes the file from the working directory and stages the removal of the file in the next commit.
    
    - `git rm <filename>`: Removes the file from the working directory and stages the removal of the file in the next commit.
    - `git rm --cached <filename>`: Removes the file from the staging area, but not from the working directory.
    - `git rm -r <directory>`: This removes a directory and its contents from the repository.
3. ##### `git mv`: 
    >Used to move or rename a file or a directory in your Git repository and stages the change automatically.