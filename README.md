# GIT CHEET SHEET

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

- `git init`: Creates a new Git repository in a directory. It initializes a ".git" directory in the root of the project, which manages the repository's history, branches, and commits.
- `git clone`: Creates a local copy of a remote Git repository. For example, to clone a remote repository called "my-repo" from GitHub, you can run:
```
git clone git@github.com:username/my-repo.git
```
- `git fetch`: Downloads new changes from a remote Git repository, but does not apply them to your local repository. For example, to fetch new changes from the "origin" remote repository, you can run:
```
git fetch origin
```
- `git pull`: Downloads new changes and updates your local repository with them. For example, to pull new changes from the "origin" remote repository into your current branch, you can run:
```
git pull origin
```
- `git push`: Uploads local changes to a remote Git repository. For example, to push the current branch to the "origin" remote repository, you can run:
```
git push origin
```
- `git status`: Shows the current status of your local repository. It displays information such as which branch you are currently on, which files have been modified or added, and which files are staged and ready to be committed. This command is useful to check the status of your changes before committing them.