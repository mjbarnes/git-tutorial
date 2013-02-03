# Git Tutorial
This tutorial will provide a chance to learn Git through real world examples.
We will be following "A successful Git branching model" - http://nvie.com/posts/a-successful-git-branching-model/

##Objective
Learn Git

# What is Git
Git is a dustruvyted revusuib control and source code management system.  Git allows a user to turn a directory into a repository with complete history and full revision tracking capabilities.  This repositior is not dependent on a central server.

# Getting started
If you have not used Git before please follow the steps below to Download/Install/Configure Git.  If you already have Git installed please skip the ##Git Basics section


## Overview
[] Download/Install/Configure Git
[] Git Basics
    [] init
    [] status
    [] add
    [] commit
[] Create a GitHub Account
[] Setup your local Git account
[] Link your locak git to Github
[] Fork a repository
[] Make local edits to a new branch
[] Sync branch to GitHub

## Download/Install/Configure Git
Download and install the latest version of Git from http://git-scm.com/downloads

**Be warned: Do not use PuTTY if you are given the option. GitHub only provides support for openssh.

## Set up Git
Now that you have Git installed, it's time to configure your settings. To do this you need to open Git Bash (not the Windows command line).

# Username

First you need to tell git your name, so that it can properly label the commits you make.
'<pre>
git config --global user.name "Your Name Here"
# Sets the default name for git to use when you commit
</pre>'

# Email

Git will saves your email address into your commits we  will use the email address to associate your commits with your GitHub account.

'<pre>
git config --global user.email "your_email@youremail.com"
# Sets the default email for git to use when you commit
</pre>'

# Generating SSH Keys

Follow the instructions provided by GitHub - https://help.github.com/articles/generating-ssh-keys

Or install and configure the GitHub desktop application. (The application will generate an SSH key and add it to your Github account for you)
Github:windows - http://windows.github.com/
Github:mac - http://mac.github.com/

## Git Basics
In this Git basic workshop we will learn how to initialize and check out local reposiroty's status.  We'll add and remove documents to the repository's index.  We'll wrap up the basic workshop by commiting our changes to the repository and reviewing the commit log.

* Create a new local repository
    * Create a new directory "IntroductionToGit"
    * Navigate into "IntroductionToGit"
    * $ git init
    * $ git status
    * We have no created a new local git repository for the "IntroductionToGit" project.
* Adding files
    * Create three .txt files within your repository. 'add.md', 'status.md', 'init.md'
    * Add 'status.md' to the local staging repository.
    * $ git add status.md
    * $ git status
    * status.md has been added to the local index (Cache) but it has not beem commited to the local repository.
    * Now add all .txt files to the local staging repository
    * $ git add *.txt
    * $ git status
    * Modify 'add.md'
    * $ git status
    * The changed file will show up in red in the status view.  
    * $ git checkout add.md
* Initial commit
    * To move files out of the local index and into the repository the changes need to be commited.
    * Perform a commit with the message "Initial commit"
    * $ git commit -m "Initial commit"
    * Review the Repository status and the commit log
    * $ git status
    * $ git log
    
During this workshop three Git commands were created as markdown files.  Populate these files with your notes on the individual commands for future reference.
    
In this practice session we have learned several base git functions.
We learned how to initialize a git repository
'$ git init'
We learned how to check out repository status
'$ git status'
We learned how to add files to the local repository index
'$ git add'
We learned how to remove an item from the local index and place it back in the working tree
'$ git checkout [File Name]'
We learned how to record our changes to the repository
'$ git commit'
We learned how to view the repository commit log
'$ git log'



# Git Basics workshop
Go to http://www.codeschool.com and take their try git, http://try.github.com,  course.



Recources:
https://help.github.com/articles/set-up-git