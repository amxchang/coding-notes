# Git and Github

### Git

Git is the most popular version control system.
It is a distributed source control system. 
Git is free and open source.
It can scale massively.
Most operations are local, which makes it very fast.

### Key Concepts

- Repositories contain files, history, and configurations that are managed by Git
- Three States of Git: Working directory, staging area (pre-commit holding area), and commit (Git repository)
  - The working directory is the directory on your computer that holds project and application files.
  - The staging area is a holding area that contains the files that haven't been committed yet.
  - The Git repository manages the commits and history that have been finalized.
  - The three states of Git are specific to local Git repositories.
- Remote repositories (ex: Github) are similar to a fourth state. They are the last step in the Git workflow and most people use a remote repository.
- Branches are timelines with changes. In Git, branches contain commits. 
  - The default branch is the master branch.
  
### Command Line

Using the command line...

- gives a strong history.
- gives you new features faster.
- gives you online help, since most people online use the command line.
- gives you more power.
- is more consistent among different operating systems.

### Git Installation

- Windows: Git for Windows [git-scm.com](https://git-scm.com/).
  - Go to [https://gitforwindows.org/](https://gitforwindows.org/) and click the download button.
  - To check that it was installed correctly, double click on the shortcut and type `git version`. It should respond with the version.
- Mac OS X: Yosemite or later, easy path: "git version"
  - Type `git version` in the command prompt. If you get a response that asks if you want to install command line developer tools, click the install button.

### Github

Github is the most popular Git hosting service.

### New Repository

To make a new repository, click the plus sign in the upper right corner area. Then, click the button that says "New repository."
Fill out the information, and then a repository will be created.

### New Local Repository

- You can also create a new repository on your computer.
```
cd folder-name
git init new-project
cd new-project
```
- `ls -al` lists all files and folders
- `cd .git/` goes into the Git folder

### Setup Project Folder

- In the terminal program, `mkdir` creates a folder.
- `cd` changes the directory to that folder.
- `pwd` tells you where you are

### Git Configuration

- `git version` asks for the version number. It can be used to test if Git is installed.
- Git requires the name and email. It may be able to figure it out itself, but this might not be reliable.
- To set the name and email, type: 
```
git config --global user.name "First Last"
git config --global user.email "email@email.com"
```
- To confirm, use `git config --global --list`.

### Cloning a Repository

- In Github, clone the repository by copying the HTTPS clone URL.
- Go to the terminal and type `git clone https://github.com/username/repository-name.git` and enter. This clones the repository to the local computer.
- Type `ls` to confirm that it works. ls lists the contents of the current directory.
- Type `cd repository-name` to go into the folder. Type `ls` again to see the contents of the repository.

### The First Commit

- To create a file, type `echo "content stuff" >> file-name.txt`.
- `cat file-name.txt` command displays contents of the file.
- `git status` gives a status.
- untracked file = file in working directory that hasn't been added to Git yet.
- To add a change to Git, use `git add file-name.txt`
- After this, `git status` will say that there's a new file.
- `git commit -m "Adding file commit message"` commits a change

### Pushing Changes

- `git push origin master` pushes the commits to the original Github copy.
- Git will ask for the username and password.
- After this, the commits should be on the Github repository. 

### Adding Git to an Existing Project

```
cd projects
unzip ~/Downloads/zip-name.zip
ls
mv name new-name
ls
cd new-name
git init
ls -al
git status
git add .
git status
git commit -m "commit message"
git status
```

To delete Git from a project:

```
cd project-name
rm -rf .git
```

## Resources Used

[Git Started With Github](https://www.udemy.com/course/git-started-with-github/) is a free Udemy course by Jason Taylor. If you don't know much about Git or Github, I would recommend this.
