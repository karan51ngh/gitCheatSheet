# GIT CHEET SHEET

## BASICS OF GIT

- **Git** is a distributed version control system that allows developers to track changes in their code and collaborate on projects.
- **Repository**: A repository is a directory where all the files for a project are stored, along with a history of all the changes made to the files.
- **Commit**: A commit is a snapshot of all the files in the repository at a certain point in time. Each commit has a unique ID and a message describing the changes made.
- **Branch**: A branch is a separate line of development within a repository. By default, there is a "master" branch, but developers can create new branches to work on new features or bug fixes without affecting the main codebase.
- **Merging**: Merging is the process of taking the changes made in one branch and applying them to another branch.
- **Clone**: Clone is the command used to copy a repository from a remote server to your local machine.
- **Add & Commit**: The "add" command stages changes, and the "commit" command saves those changes with a message describing what was done.
- **Push & Pull**: The "push" command uploads your commits to a remote repository, and the "pull" command downloads any new commits from the remote repository.


## THREE-STAGE  ARCHITECTURE OF GIT

Git has a three-stage architecture for managing changes to files in a repository.
The three stages are: Working Directory, Staging Area, and Git Repository.
- The **Working Directory** is where you make changes to files in your repository.
- The **Staging Area** is an intermediate stage where you select which changes to include in your next commit.
- The **Git Repository** is where Git permanently stores your files and the history of changes made to them. 

Git tracks changes in your Working Directory and displays them as "unstaged changes".
- Use git add to stage changes for the next commit.
- Use git commit to permanently save changes to the Git Repository.