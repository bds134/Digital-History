# Lesson Git Version Control System

## Lesson overview

This lesson provides instruction on how to connect Visual Studio Code (VSC) to GitHub and how to utilize GiHubs Version Control System (Git VCS) to edit within VSC and to make commits through Git and to GitHub, or in reverse, to edit and commit in GitHub, and to sync throuh Git back to VSC.

[The Pro Git Book](https://git-scm.com/book/en/v2 "The entire Pro Git book, written by Scott Chacon and Ben Straub and published by Apress") provides excellent documentation for Git.

## What is Git

Git is a powerful version control system that works by taking snapshots of your repository at every stage of development. It keeps a history of these snapshots that can be viewed at anytime. You can develop your projects on your local machine and then push these changes to either A. an 'upstream' repository that you own or manage or B. a branch of a repository that you do not own or manage and then request that the owner pull those changes into the main ('master') branch.

In this lesson, we focus our attention on installing git and working with git through both the command line and the VSCode GUI. We discuss cloning, staging, committing, and pushing. We discuss `git diff`. We discuss branching/forking.

## Git Installation

Let's do this through the CLI. You can follow my instructions or use the [Git Book installation instructions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

### Windows Git Installation

#### Windows Step 1 &mdash; software prep

Windows users will need to have `winget` installed. To see if it is installed, open `powershell` and type `winget --version`. It should print out something like this:

```Powershell
winget --version
v1.6.3482
```

If it is installed, move on to Step 2. If not, install it by following these [winget installation instructions](https://docs.microsoft.com/en-us/windows/package-manager/winget)

#### Windows Step 2 &mdash; install git

```powershell
winget install --id Git.Git -e --source winget
```

That's it! The latest version of Git (v.2.43) has been installed and is ready to use. Your powershell output should look something like this:

![screenshot of git installation with winget in powershell](/assets/git-install-powershell.png)

### Linux Git Installation

#### Fedora or any closely-related RPM-based distribution, such as RHEL or CentOS

```bash
sudo dnf install git-all
```

#### Debian-based distribution, such as Ubuntu

```bash
sudo apt install git-all
```

#### Additional troubleshooting instructions for enabling linux 2FA (needed for git to work), can occur with Linux Mint

```bash
git config --global credential.credentialStore secretservice
```

If an error comes up, install gcm (git-credential-manager) and/or run

```bash
git-credential-manager configure
```

then try the above command(s) again.

#### More linux options

There are instructions for installing git on several different Unix distributions on the [Git website](https://git-scm.com/download/linux).

### Mac Git Installation

On a Mac, type `git --version`. If it is not installed, it will prompt you to install it. Alternatively, you might need to install xcode before git, in which case you will simply type `git` which should prompt for xcode installation. Once installed, do as mentioned above, type `git --version`.

The [Git Book installation instructions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) is where you should begin your installation workflow.

## Git set up

Where did get set up essential files? Let's check with this command:

```powershell
git config --list --show-origin
```

We need to set up our username and email address so that git knows to whom to associate any commits. Let's add this info:

```powershell
git config --global user.name "John Doe"
git config --global user.email johndoe@gmail.com
```

If you have questions about a git command, use the help feature. For instance, let's learn about the `config` command:

```powershell
git config -h
```

This gives us all of the options for this command

## Getting a Git Repo

Git works within repositories, making commits and pushing and pulling code into branches of these repos. To start working with Git, you have to ask yourself a basic question: Do I want to start a new repository from my local files or do you want to work with an existing repository?

Your answer to this question will determine if you follow the first or second workflow below. In both cases, we will assume that you have already configured git on your machine and you are working in the terminal in VSCode.

### Initializing a New Repo

Start a VSCode window and open a folder location where you want to create the repository. Let's use this opportunity to create a dh-term-project repository.

Tip: It's important that you use a one-to-one window-to-repo structure. That is, start a window whose root folder is also the the root of your repo.

Now we need to initialize a `.git` subdirectory that includes all of the necessary system files for this specific git repo.

```powershell
git init
```

This adds `.\.git\` directory.

Now we can add a README file to this repository.

```powershell
echo "# This repository contains all files for the development and presentation of my Digital History term paper project." > readme.md
```

Tip: Linux file system treats file and directory names as case-sensitive. Mac and Windows treat them as case-insensitive.

None of the files or folders created above is synced with GitHub, so let's start this process by doing the following:

1. Adding/staging your files
2. Committing your files
3. Pushing your files and repo to GitHub

Use the `git add` command to add files and the `git status` command to check which files are being watched for modifications, which files are ready to committed, and which files have been committed.

First, try `git status`. You'll see that nothing is tracked and nothing is staged or committed. However, you will see that readme.md is 'untracked', meaning that it has never been committed to the repo.

Let's `add` the readme.md file. ('Add' is also called 'stage' or 'index'.)

```powershell
git add readme.md
```

Now, when we run `git status` we see that readme.md is staged to be committed.

The next step is to commit the staged files to the repository, in which case you need to add a commit message, which should be less than 50 characters, the first of which should be capitalized and be the first letter of an imperative verb, such as 'Initialize', 'Add', 'Modify', etc. These are guidelines, not rules, but a message must be added. The `-m` flag is used to add a message to the commit.

```powershell
git commit -m "Initialize repository"
```

Now `git status` will tell you that nothing is left to commit, which is because the staged file(s) were just committed.

Let's set up the repo in github.com, which you all know how to do from last week's lesson.

Now let's push are files to GitHub, which is a 'remote' repository that is&mdash;except upon the first sync as we are doing now&mdash;'upstream' of your local repository.

The command for this is `git push <remote> <branch>`, where <remote> normally has the value of 'origin' and <branch> of 'master' (or 'main' if you changed the name from master to main).

Let's check to see if git has a remote defined:

```powershell
git remote -v
```

You might need to set the 'origin' as such:

```powershell
git remote add origin https://github.com/[username]/[repository].git
```

You can verify the success of the `remote add`command by going to `git remote -v`.

It often looks like this:

```powershell
git push origin master
```

After you push the code for the first time on VSCode, you'll need to authenticate with 2fa.

### Cloning a Repo

The easiest was to get syncing with GitHub remote repositories is by using the `clone` command, which asks Git to receive a full copy of nearly all data that the server has. Every version of every file for the history of the project is pulled down by default when you run git clone.

Start a new VSCode Window in a folder in which you want to work with the clone. Open the terminal and enter this command:

```powershell
git clone https://github.com/username/[repository]
```

Once the repo has been cloned to your local machine, the add/commit/push sequence is the same as described above. As you can see, this building a skeletal version of the repo in GitHub and then cloning it on your local machine is the easier workflow because git takes care of some essential commands without any effort from users.

## The VSCode GUI

Not surprisingly, VSCode is built for git and the GUI can be a useful means to carryout your workflow. Here, we will go through the steps using the GUI.

### GUI Clones

You will notice that a 'welcome screen' is initiated when you open a new window of VSCode. If you have disabled this screen, most of the same options are found by clicking of the 'explorer'. Use the 'Clone Repository' button/link, which launches a finder with an option to select GitHub remote repositories, which you should select. This gives you access to your own repositories and others to which you are a contributor, along with any other public repository. You might not be able to upstream your code to the main branches of those repositories, but you can repurpose it as you wish subject to license agreement.

Once you have selected the repo you want to clone, it will ask you to define the local folder in which the cloned repo will be stored (and where the .git/ subdirectory will be unpacked).

### GUI Stage, Commit, and Push/Pull

You will use the Source Control button on the 'Activity Bar' to stage, commit and even push/pull. Source Control gives you a list of modified files. Untracked modified files are labeled with a 'U' and tracked ones have an 'M'. Hovering over the file reveals more file options. The '+' sign will stage the file and open a new cluster of files called 'Staged Changes' that gives you the option to unstage the file (with '-' sign). When you are ready to commit, write your commit message at the top of the explorer and choose one of the four options:

1. Commit: Records changes that you have made on your local machine. It will not mark the change in the remote repository.
2. Commit (amend): Modifies the most recent commit.
3. Commit & Push: Does the above and pushes it to the remote repository. This means that any changes you have made will be saved to the remote repository as well.
4. Commit & Sync: Does three things. First, it will commit. Second, it will perform a pull (grabs the updated information from the remote repo). Finally, it will push.

Once the files have been committed, you might need to push/pull, which can be done at the bottom-left corner of the screen using the 'synchronize changes' option.

## Git Branching

A Git Branch (or fork) allows you to work on the code in a context where pushing modifications upstream will not change the main branch. This is a safe space for testing code that might result in some upstreaming back to the main, but not necessarily.

Let’s say you want to create a new branch called testing. You do this with the git branch command:

```powershell
git branch testing
```

To switch to an existing branch, you run the git checkout command. Let’s switch to the new testing branch:

```powershell
git checkout testing
```

If you make changes to this branch, and then need to return to the master branch to make a critical change, you can checkout the master:

```powershell
git checkout master
```

At this point, your project working directory is exactly the way it was before you started working on testing branch.

Imagine that you make the necessary fix in the master, checkout the testing, and then desire to merge your testing changes back into your master branch to deploy to production. You do this with the git merge command:

```powershell
git merge testing
```

This causes the master to be 'fast-forwarded' to testing. Now you might want to delete the 'testing' branch:

```powershell
git branch -d testing
```
