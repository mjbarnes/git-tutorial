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

*Be warned: Do not use PuTTY if you are given the option. GitHub only provides support for openssh.*

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
`$ git remote add origin git@github.com:[User Name]/IntroductionToGit.git`
`$vgit push -u origin master`
<pre>
C:\git\IntroductionToGit [master]> git remote add origin git@github.com:j0hnb/In
troductionToGit.git
C:\git\IntroductionToGit [master]> git push -u origin master
Warning: Permanently added 'github.com,207.97.227.239' (RSA) to the list of know
n hosts.
Counting objects: 3, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 228 bytes, done.
Total 3 (delta 0), reused 0 (delta 0)
To git@github.com:j0hnb/IntroductionToGit.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
C:\git\IntroductionToGit [master]>
</pre>

# Branching and Merging

In the Github website `Fork` this repository.  Forking will add a clone of this repository to your account.  But the repository is currently only stored on Github.

To make a local copy of the git-tutorial repository call by using the `$ git clone` command

`$ git clone https://github.com/j0hnb/git-tutorial.git`
<pre>
C:\git> git clone https://github.com/j0hnb/git-tutorial.git
Cloning into 'git-tutorial'...
remote: Counting objects: 90, done.
remote: Compressing objects: 100% (53/53), done.
remote: Total 90 (delta 39), reused 75 (delta 24)
Unpacking objects: 100% (90/90), done.
</pre>
Navigate into the git-tutorial directory

In order to organize our changes we're going to create a branch of this repository
`$ git checkout -b diff-example`
<pre>
C:\git\git-tutorial [master]> git checkout -b diff-example
Switched to a new branch 'diff-example'
</pre>

Open, edit and save `diff.md`.  Use the `git diff` command to show the changes.
`$ git diff`
<pre>
C:\git\git-tutorial [diff-example]> git diff
diff --git a/diff.md b/diff.md
index 125f1a5..2d3a5c1 100644
--- a/diff.md
+++ b/diff.md
@@ -1,5 +1,6 @@
 Lorem ipsum dolor sit amet, consectetur adipiscing elit.
 Ut diam ipsum, molestie cursus luctus et, convallis sollicitudin risus.
+What is "Lorem ipsum"?
 Suspendisse dapibus, elit in vestibulum elementum, libero dolor porttitor mauri
 Cras augue quam, mattis sed gravida id, ultrices sed enim. In laoreet odio semp
 Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculu
 ...
 C:\git\git-tutorial [diff-example +0 ~1 -0]>
</pre>

Add the changes to the local repository and commit the changes
`$ git add diff.md`
<pre>
C:\git\git-tutorial [diff-example +0 ~1 -0]> git add diff.md
C:\git\git-tutorial [diff-example +0 ~1 -0]>
</pre>

`$ git commit -m 'Commiting Diff example' `
<pre>
C:\git\git-tutorial [diff-example +0 ~1 -0]> git commit -m 'Commiting Diff example'
[diff-example 8c0588c] Commiting Diff example
 1 file changed, 1 insertion(+)
</pre>

Now lets see if this repository has any tags.  
`$ git tag`
<pre>
C:\git\git-tutorial [diff-example]> git tag
C:\git\git-tutorial [diff-example]>
</pre>

Tag the repository for version 1.0.1
`$ git tag -a v1.0.1 -m 'version 1.0.1' `
<pre>
C:\git\git-tutorial [diff-example]> git tag -a v1.0.1 -m 'version 1.0.1'
C:\git\git-tutorial [diff-example]>
</pre>

Now lets verify that the tag that we created is in place
`$ git tag`
<pre>
C:\git\git-tutorial [diff-example]> git tag
v1.0.1
C:\git\git-tutorial [diff-example]>
</pre>

Switch back to master
`$ git checkout master`
<pre>
C:\git\git-tutorial [diff-example]> git checkout master
Switched to branch 'master'
C:\git\git-tutorial [master]>
</pre>

Merge the changes made in the diff-example branch with the master branch
`$ git merge diff-example`
<pre>
C:\git\git-tutorial [master]> git merge diff-example
Updating 9bc2ecc..8c0588c
Fast-forward
 diff.md | 1 +
 1 file changed, 1 insertion(+)
C:\git\git-tutorial [master]>
</pre>

Visualize the log
`$ git log --oneline --decorate --graph`
<pre>
C:\git\git-tutorial [master]> git log --oneline --decorate --graph
* 8c0588c (HEAD, tag: v1.0.1, master, diff-example) Commiting Diff example
* 9bc2ecc (origin/master, origin/HEAD) Added examples to introduction workshop
* f8a03b9 Created initial Be Social catgeory and updated Resouces category
* c838d60 Updated resouces
* 5470962 Updated links
* 01bb6a1 Formatting updates
* 82759f5 Cleaned up diff.md
* f1d994c Moved git commands learned in git basics workshop into a table
* d4480bd Cleaning up directory
*   94feb43 Updated git command pages
|\
| * 7ebebc7 Updated git command pages
* | 26f6c3b Added commands table
* |   08d40f6 Merge branch 'ManPages'
|\ \
| |/
| * 9b8a09e Man Page updates
* |   9e1177d Merge branch 'documentCleaner'
|\ \
| * | ee72f5b spelling updates
| * | c8c4128 slight formatting changes
| |/
* | 1b73af0 Fixing Checkout delete
|/
* 77992f4 Added initial "Working with remote repositories"
* d974719 Initial draft of "Branching and Merging"
* 61be5d9 Formatting updates
* 591b17f Initial Git Basics workshop commit
* 88062ad Initial Commit
C:\git\git-tutorial [master]>
</pre>

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