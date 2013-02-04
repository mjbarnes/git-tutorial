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
* Be Social - Github is a social open source communitry!
    * Follow a friend
    * Watch a project
    * Pull requests
    * Issues
* Resources
    * Github desktop applications
    * Markdown
    * Suggested Reading

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
    <pre>
    C:\git\IntroductionToGit> git init
    Initialized empty Git repository in C:/git/IntroductionToGit/.git/
    </pre>
    * `$ git status`
    <pre>
    C:\git\IntroductionToGit [master]> git status
    \# On branch master
    \#
    \# Initial commit
    \#
    nothing to commit (create/copy files and use "git add" to track)
    </pre>
    * We have now created a new local git repository for the `IntroductionToGit` project
* Adding files
    * Create three .md files within your repository
        * `$ touch add.md`
        * `$ touch status.md`
        * `$ touch init.md`
        <pre>
        C:\git\IntroductionToGit [master]> touch add.md
        C:\git\IntroductionToGit [master +1 ~0 -0 !]> touch status.md
        C:\git\IntroductionToGit [master +2 ~0 -0 !]> touch init.md
        C:\git\IntroductionToGit [master +3 ~0 -0 !]>
        </pre>
    * Add `status.md` to the local staging repository
    * `$ git add status.md`
    <pre>
    C:\git\IntroductionToGit [master +3 ~0 -0 !]> git add status.md
    C:\git\IntroductionToGit [master +1 ~0 -0 | +2 ~0 -0 !]>
    </pr>
    * `$ git status`
    <pre>
    C:\git\IntroductionToGit [master +1 ~0 -0 | +2 ~0 -0 !]> git status
    \# On branch master
    \#
    \# Initial commit
    \#
    \# Changes to be committed:
    \#   (use "git rm --cached <file>..." to unstage)
    \#
    \#       new file:   status.md
    \#
    \# Untracked files:
    \#   (use "git add <file>..." to include in what will be committed)
    \#
    \#       add.md
    \#       init.md
    C:\git\IntroductionToGit [master +1 ~0 -0 | +2 ~0 -0 !]>
    </pre>
    * `status.md` has been added to the local index (Cache) but it has not been committed to the local repository
    * Now add all .md files to the local staging repository
    * `$ git add *.md`
    <pre>
    C:\git\IntroductionToGit [master +1 ~0 -0 | +2 ~0 -0 !]> git add *.md
    C:\git\IntroductionToGit [master +3 ~0 -0]>
    </pre>
    * `$ git status`
    <pre>
    C:\git\IntroductionToGit [master +3 ~0 -0]> git status
    \# On branch master
    \#
    \# Initial commit
    \#
    \# Changes to be committed:
    \#   (use "git rm --cached <file>..." to unstage)
    \#
    \#       new file:   add.md
    \#       new file:   init.md
    \#       new file:   status.md
    \#
    C:\git\IntroductionToGit [master +3 ~0 -0]>
    </pre>
* Initial commit
    * To move files out of the local index and into the repository the changes need to be commited
    * Perform a commit with the message "Initial commit"
    * `$ git commit -m "Initial commit"`
    <pre>
    C:\git\IntroductionToGit [master +3 ~0 -0]> git commit -m "Initial commit"
    [master (root-commit) acc420d] Initial commit
    0 files changed
    create mode 100644 add.md
    create mode 100644 init.md
    create mode 100644 status.md
    C:\git\IntroductionToGit [master]>
    </pre>
    * Review the Repository status and the commit log
    * `$ git status`
    <pre>
    C:\git\IntroductionToGit [master]> git status
    \# On branch master
    nothing to commit, working directory clean
    C:\git\IntroductionToGit [master]>
    </pre>
    * `$ git log`
    <pre>
    C:\git\IntroductionToGit [master]> git log
    commit acc420dcc8038d250e9180d295845206d1b38771
    Author: John Banks <jcbanks@gmail.com>
    Date:   Sun Feb 3 21:13:40 2013 -0500

    Initial commit
    C:\git\IntroductionToGit [master]>
    </pre>
    
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

# Be Social

## Follow a friend
> One of the great features on GitHub is the ability to see what other people are working on and who they are connecting with. When you follow someone, you will get notifications on your dashboard about their GitHub activity.

Step 1. Pick a friend
Step 2. Follow that friend.

## Watch a project
Notifications are powered by the repositories you are watching. If you are watching a repository, you will receive notifications for all discussions.

* Issues and their comments
* Pull Requests and their comments
* Comments on any commits

## Star a project
> Stars are a way to keep track of repositories that you find interesting. Any repositories you were previously watching can now be found on your stars page.

[Star this repository!](https://github.com/j0hnb/git-tutorial/star "Star this repository!")

## Pull requests
> Pull requests let you tell others about changes you've pushed to a GitHub repository. Once a pull request is sent, interested parties can review the set of changes, discuss potential modifications, and even push follow-up commits if necessary.

[Github:help - Pull requests](https://help.github.com/articles/using-pull-requests "Github:help - Pull requests")

## Issues
> When you are collaborating on a project with someone, you sometimes come across problems that need to be fixed. To help you keep track of these problems, each GitHub repo has a section called Issues.

If you notice any issues with this repository please report the issue to the [Git-Tutorial](https://github.com/j0hnb/git-tutorial/issues "Git Tutorial") issues page.

# Resources

## Github desktop applications
Install and configure the GitHub desktop application. (The application will generate an SSH key and add it to your Github account for you)

* [Github:Windows](http://windows.github.com "Github:Windows")
* [Github:Mac](http://mac.github.com "Github:Mac")

## Markdown
This tutorial has been written in [Github flavored Markdown](http://github.github.com/github-flavored-markdown "Github flavored Markdown").

Press *M* on this page to see the github markdown cheat sheet.

### Online Markdown editors

* [Markable](http://markable.in "Markable") is a good online markdown editor.
* DaringFireBall aslo has a good online [Markdown editor](http://daringfireball.net/projects/markdown/dingus "Markdown editor").

## Suggested Reading 
[A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model "A successful Git Branching model")