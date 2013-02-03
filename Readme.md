# Git Tutorial
This tutorial will provide a chance to learn Git through real world examples.

## Introduction

### Git is
A distributed revision control and source code management system.  Git allows a user to turn a directory into a repository with complete history and full revision tracking capabilities.  Git repositories do not rely on a central server.

#### Getting started with Git
If you have not used Git before please follow the steps below to [Download/Install/Configure Git](https://github.com/j0hnb/git-tutorial#downloadinstallconfigure-git "Download/Install/Configure Git").  If you already have Git installed please skip the [Git Basics workshop](https://github.com/j0hnb/git-tutorial#git-basics-workshop "Git Basics workshop").

## Overview
* Download/Install/Configure Git
    * Setting up Git
    * Generating SSH Keys
* Git Basics workshop
    * init
    * status
    * add
    * commit
    * log
* Working with remote repositories
    * Pushing a repository to Github
* Branching and Merging
    * Fork
    * Clone
    * Branch
    * Merge
    * Diff
    * Checkout
* Github

## Download/Install/Configure Git
Download and install the latest version of Git from [http://git-scm.com](http://git-scm.com/downloads "http://git-scm.com")

**Be warned: Do not use PuTTY if you are given the option. GitHub only provides support for openssh.

## Setting up Git
Now that you have Git installed, it's time to configure your settings. To do this you need to open Git Bash (not the Windows command line).

### Username

First you need to tell git your name, so that it can properly label the commits you make.  Set the default name for git to use when you commit.

`$ git config --global user.name 'Your Name Here' `

### Email

Git will saves your email address into your commits we  will use the email address to associate your commits with your GitHub account. Set the default email for git to use when you commit.

`$ git config --global user.email 'your_email@youremail.com' `

## Generating SSH Keys

Follow the [generating SSH key](https://help.github.com/articles/generating-ssh-keys "generating SSH key") instructions provided by GitHub.

# Git Basics workshop
In this Git basic workshop we will learn how to initialize and check out local reposiroty's status.  We'll add and remove documents to the repository's index.  We'll wrap up the basic workshop by commiting our changes to the repository and reviewing the commit log.

* Create a new local repository
    * Create a new directory `IntroductionToGit`
    * Navigate into `IntroductionToGit`
    * `$ git init`
    * `$ git status`
    * We have no created a new local git repository for the `IntroductionToGit` project.
* Adding files
    * Create three .md files within your repository. 
        * `$ touch add.md`
        * `$ touch status.md`
        * `$ touch init.md`
    * Add `status.md` to the local staging repository.
    * `$ git add status.md`
    * `$ git status`
    * `status.md` has been added to the local index (Cache) but it has not been committed to the local repository.
    * Now add all .txt files to the local staging repository
    * `$ git add *.txt`
    * `$ git status`
* Initial commit
    * To move files out of the local index and into the repository the changes need to be commited.
    * Perform a commit with the message "Initial commit"
    * `$ git commit -m "Initial commit"`
    * Review the Repository status and the commit log
    * `$ git status`
    * `$ git log`
    
During this workshop three Git commands were created as markdown files.  Populate these files with your notes on the individual commands for future reference.
    
In this practice session we have learned several base git functions.

Command          | Description
-----------------| ---------------
`$ git init`     | initializes a directory as a Git repository
`$ git status`   | show repository status
`$ git add`      | adds file contents to the staging area 
`$ git commit`   | records a snapshot of the staging area
`$ git log`      | filter your commit history


## Git Basics Homework
Go to [CodeSchool.com](http://www.codeschool.com "CodeSchool.com") and login with your GitHub account.  After you have signed in take the [Try Git](http://try.github.com "Try Git") course.  Upon completion of the try git course Code School will give you access to level 1 of their Git Real course.  Play level one for some extra practice.

# Working with remote repositories

Create a new repository in GitHub called `IntroductionToGit`

Now push the IntrductionToGit repository to GitHub
<pre>
git remote add origin git@github.com:[User Name]/IntroductionToGit.git
git push -u origin master
</pre>

# Branching and Merging

In the Github website `Fork` this repository.  Forking will add a clone of this repository to your account.  But the repository is currently only stored on Github.

To make a local copy of this repository call `$ git clone [Repository URL]`

`$ git clone https://github.com/[User Name]/git-tutorial.git`

In order to organize our changes we're going to create a branch of this repository
`$ git checkout -b diff-example`

Create a new `diff.md` file.

`$ touch diff.md`

Open, edit and save `diff.md`.  Use the `git diff` command to show the changes.
`$ git diff`

Add the changes to the local repository and commit the changes
`$ git add diff.md`
`$ git commit -m 'Completed diff practice' 

Create a version file
`$ touch version.md`

Tag the repository for version 1.1
`$ git tag -a v1.1`

Switch back to master
`$ git checkout master`

Merge the changes made in the diff-example branch with the master branch
`$ git merge diff-example`

Visualize the log
`$ git log --oneline --decorate --graph`

New commands used in this workshop

Command                                     | Description
------------------------------------------- | ------------------------
`$ git clone `                              | copy a git repository so you can add to it
`$ git checkout `                           | switch to a new branch context    
`$ git tag `                                | tag a point in history as important   
`$ git merge `                              | merge a branch context into your current one
`$ git log --oneline --decorate --graph`    | filter your commit history


## Github desktop applications
Install and configure the GitHub desktop application. (The application will generate an SSH key and add it to your Github account for you)

[Github:Windows] (http://windows.github.com "Github:Windows")

[Github:Mac] (http://mac.github.com "Github:Mac")

# Suggested Reading 
[A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model "A successful Git Branching model")