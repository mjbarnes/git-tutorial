# Git Tutorial
This tutorial will provide a chance to learn Git through real world examples.

## Introduction

### Git is
A distributed revision control and source code management system.  Git allows a user to turn a directory into a repository with complete history and full revision tracking capabilities.  Git repositories do not rely on a central server.

#### Getting started with Git
If you have not used Git before please follow the steps below to [Download/Install/Configure Git](https://github.com/j0hnb/git-tutorial#downloadinstallconfigure-git "Download/Install/Configure Git").  If you already have Git installed please skip the [Git Basics workshop](https://github.com/j0hnb/git-tutorial#git-basics-workshop "Git Basics workshop").

## Overview
* [Download/Install/Configure Git](https://github.com/j0hnb/git-tutorial#downloadinstallconfigure-git "Download/Install/Configure Git")
    * [Setting up Git](https://github.com/j0hnb/git-tutorial#setting-up-git "Setting up Git")
    * [Generating SSH Keys](https://github.com/j0hnb/git-tutorial#generating-ssh-keys "Generating SSH Keys")
* [Git Basics workshop](https://github.com/j0hnb/git-tutorial#git-basics-workshop "Git Basics workshop")
    * init
    * status
    * add
    * commit
    * log
    * [Git basics homework](https://github.com/j0hnb/git-tutorial#git-basics-homework "Git basics homework")
* [Working with remote repositories](https://github.com/j0hnb/git-tutorial#working-with-remote-repositories "Working with remote repositories")
    * Pushing a repository to Github
* Branching and Merging
    * Clone
    * Branch
    * Merge
    * Diff
    * Tag
    * Checkout
    * log  --oneline --decorate --graph
* [Be Social](https://github.com/j0hnb/git-tutorial#be-social "Be Social") - Github is a social open source communitry!
    * Fork a repository
    * [Follow a friend](https://github.com/j0hnb/git-tutorial#follow-a-friend "Follow a friend")
    * [Watch a project](https://github.com/j0hnb/git-tutorial#watch-a-project "Watch a project")
    * [Pull requests](https://github.com/j0hnb/git-tutorial#pull-requests "Pull request")
    * [Issues](https://github.com/j0hnb/git-tutorial#issues "Issues")
* [Resources](https://github.com/j0hnb/git-tutorial#resources "Resouces")
    * [Github desktop applications](https://github.com/j0hnb/git-tutorial#github-desktop-applications "Github desktop applications")
    * [Markdown](https://github.com/j0hnb/git-tutorial#markdown "Markdown")
    * [Suggested Reading](https://github.com/j0hnb/git-tutorial#suggested-reading "Suggested Reading")

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
This workshop will walk through the basics of initializing a repository `$ git init` , checking the repository status `$ git status`, adding files to a repository `$ git add`, commiting changes to the repository `$ git commit` and finally reviewing the repository log `$ git log`.  

We will start by creating a local repository.  Git is a decentralized version control system which means that to use Git we do not have to connect our repository to a central repository store unless we want to.  We will being by turning a normal file directory into a Git repository.  We will then move forward by adding files to the local cache and then once we are comfortable with the changes that we've made we will or commit the files to the local repository.

To proceed with this workshop you will need to have Git installed and configured.  All command line commands will always be displayed with a `$` followed by the command.  For example `$ git init` means from the command line run `git init`.

1. Create a new local repository
    * Create a new directory `IntroductionToGit`
    * Navigate into `IntroductionToGit`
    * Use `git init` to initialize the directory and convert it into a Git repository
        * `$ git init`
        <pre>
        C:\git\IntroductionToGit> git init
        Initialized empty Git repository in C:/git/IntroductionToGit/.git/
        </pre>
    * Now that we have initialized our Git repository lets view the repository status
        * `$ git status`
        <pre>
        C:\git\IntroductionToGit [master]> git status
        \# On branch master
        \#
        \# Initial commit
        \#
        nothing to commit (create/copy files and use "git add" to track)
        </pre>
    * We have now created a new local Git repository for the `IntroductionToGit` project and we have checked the repository status.  
    
    Some items to note.  When working inside a Git repository the current branch is visable at all times. For example as seen above we are working in the C:\git\IntroductionToGit directory.  But after the directory path we see [master] `C:\git\IntroductionToGit [master]>`.  This states that we are working on the master branch.  We will go into branching later on in this workshop.
    
2. Adding files to your local repository
    * Before we can add a file to our repository we first need to create a few files to add.  We can quickly create files by using the `touch` command.
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
    * Now that we have some files to work with let's add `status.md` to the local staging repository.  The staging repository here is a cache repository.  The files are not fully added to the repository until they are commited to that repository.  We can add files to the repository by using the git add command which is followed by the file name  `git add [File Name]`.
        * `$ git add status.md`
        <pre>
        C:\git\IntroductionToGit [master +3 ~0 -0 !]> git add status.md
        C:\git\IntroductionToGit [master +1 ~0 -0 | +2 ~0 -0 !]>
        </pre>
    * Now that we have added a file to the local cache lets take a look at out git status to see what it says.
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
        * Since status.md has been added to our cache we are not tracking status.md.  We can remove this file from our cache by calling `$ git rm --cached status.md`.  add.md and init.md have not been added to our cache so they are listed as untracked files.  The branch name now has some additional changes.  `[master +1 ~0 -0 | +2 ~0 -0 !]` status that we are on the master branch and we have one file in stating and 2 unstaged files.
    * In order to track all of the files that we have created let's add all of the .md files from our directory to our local repository.  This can be done by calling `$ git add *.[File Extension]`
        * `$ git add *.md`
        <pre>
        C:\git\IntroductionToGit [master +1 ~0 -0 | +2 ~0 -0 !]> git add *.md
        C:\git\IntroductionToGit [master +3 ~0 -0]>
        </pre>
    * Now that we've added all of our files to the local repository the master banch says +3 and we can confirm our changes by calling git status.
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
3. Now that we have added several files to staging it's time to commit these files to the local repository.
    * To move our changes from staging to the master repository we will need to preform a `$ git commit` command.  Git commits require descriptions.  These descriptions should be short descriptions of what has been changes in this commit.  For our first commit we will attach an "Initial commit" message. 
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
    * Now that we have commited out changes lets take a look at our repository status.
        * `$ git status`
        <pre>
        C:\git\IntroductionToGit [master]> git status
        \# On branch master
        nothing to commit, working directory clean
        C:\git\IntroductionToGit [master]>
        </pre>
    * Our git status is empty.  This is because the git status command reflects active and unsaved work on the git repository.  To view our git commit log we will need to call `$ git log`
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
Git is a decentralized version control system.  This is a great feature for independent developers but what if you want to share your work?  Git can also connect to a cerntral server to allow for easy version control and collaborations.  In this workshop we will take advantage of Github's git powered collaboration platform.  We will create a new repository on Github and we will push the repository that we created in the first workshop to Github.

To proceed you will need to have created a local repository like outlined in the Git Basics workshop.  You will also need a Github account.  If you have not already created a Github account please do so now by [signing up](https://github.com "signing up").

1. Log into Github and create a new repository in GitHub called `IntroductionToGit`
2. Open Git Bash and navigate to your local `IntroductionToGit` repository
3. We will now push our local `IntroductionToGit` repository to Github
    * `$ git remote add origin git@github.com:[User Name]/IntroductionToGit.git`
    * `$ git push -u origin master`
    <pre>
    C:\git\IntroductionToGit [master]> git remote add origin git@github.com:j0hnb/IntroductionToGit.git
    C:\git\IntroductionToGit [master]> git push -u origin master
    Warning: Permanently added 'github.com,207.97.227.239' (RSA) to the list of known hosts.
    Counting objects: 3, done.
    Delta compression using up to 2 threads.
    Compressing objects: 100% (2/2), done.
    Writing objects: 100% (3/3), 228 bytes, done.
    Total 3 (delta 0), reused 0 (delta 0)
    To git@github.com:j0hnb/IntroductionToGit.git
    \* [new branch]      master -> master
    Branch master set up to track remote branch master from origin.
    C:\git\IntroductionToGit [master]>
    </pre>
    
4. Refresh your Github repository to see the changes that you've made.
    
# Branching and Merging

A branch is a git's way of sectioning off code.  Branching allows you to take a snapshot of the code and work from that snapshot without effecting the master or production code.  A real life example.  You are a software developer and have been alerted of a bug in your production code.  The following workflow will take you through the bug fix process.
1. The developer will fork, or clone the production repository
2. The developer will create a branch of the production code to section off his work
    * The branch name should reflect actions or changes within the branch.  The Bug tracking # would be a good unique branch name
3. The developer will resolve and test his bug fix within the branch.
4. Merge the branch with the developer's master repository
5. The developer will then issue a pull request to the production repository.  

For the next part of this workshop we will clone this git-tutorial repository and work on branching and merging.  For this workshop assume there is an bug with diff.md in which you need to update the file.

1. We will start by making a clone of the production code.  To make a local copy of the git-tutorial repository use the `$ git clone` command
    * `$ git clone https://github.com/j0hnb/git-tutorial.git`
    <pre>
    C:\git> git clone https://github.com/j0hnb/git-tutorial.git
    Cloning into 'git-tutorial'...
    remote: Counting objects: 90, done.
    remote: Compressing objects: 100% (53/53), done.
    remote: Total 90 (delta 39), reused 75 (delta 24)
    Unpacking objects: 100% (90/90), done.
    </pre>
2. Now that we have cloned the git-tutorial let's navigate into the git-tutorial directory
3. We want to section off our work from our local production code by working from a branch
    * Create a branch named `diff-example` and switch to that branch by using the `-b` attribute
    * `$ git checkout -b diff-example`
    <pre>
    C:\git\git-tutorial [master]> git checkout -b diff-example
    Switched to a new branch 'diff-example'
    </pre>
4. Within the `diff-example` branch open, edit and save `diff.md` 
5. After you have updated the `diff.md` file let's use the `git diff` command to review the changes
    * `$ git diff`
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

6. Now that we've reviewed the changes and are hapy with our edits we need to merge back into our local production clone.  But before we can merge with production we first need to add our updated file to our local repository
    * `$ git add diff.md`
    <pre>
    C:\git\git-tutorial [diff-example +0 ~1 -0]> git add diff.md
    C:\git\git-tutorial [diff-example +0 ~1 -0]>
    </pre>

7. We've added our changes to our repository, now we need to commit the changes
    * `$ git commit -m 'Commiting Diff example' `
    <pre>
    C:\git\git-tutorial [diff-example +0 ~1 -0]> git commit -m 'Commiting Diff example'
    [diff-example 8c0588c] Commiting Diff example
    1 file changed, 1 insertion(+)
    </pre>

8. We've made a minor change in the repository so we should tag the repository with a new version number
    * Before we add a new version tag we should view the tags on the repository.  This can be done by using `git tag`
    * `$ git tag`
    <pre>
    C:\git\git-tutorial [diff-example]> git tag
    C:\git\git-tutorial [diff-example]>
    </pre>
    * We've reviewed the tags in place on this repository and we want to add a the a version 1.0.1 tag. 
    * `$ git tag -a v1.0.1 -m 'version 1.0.1' `
    <pre>
    C:\git\git-tutorial [diff-example]> git tag -a v1.0.1 -m 'version 1.0.1'
    C:\git\git-tutorial [diff-example]>
    </pre>
    * We can verify now that the tag was created by using `git tag`
    * `$ git tag`
    <pre>
    C:\git\git-tutorial [diff-example]> git tag
    v1.0.1
    C:\git\git-tutorial [diff-example]>
    </pre>

9.  We've completed our updates on this branch.  We will now switch back to the master branch and merge the `diff-example` branch into the master branch
    * `$ git checkout master`
    <pre>
    C:\git\git-tutorial [diff-example]> git checkout master
    Switched to branch 'master'
    C:\git\git-tutorial [master]>
    </pre>

10. Let's merge the changes made in the diff-example branch with the master branch
    * `$ git merge diff-example`
    <pre>
    C:\git\git-tutorial [master]> git merge diff-example
    Updating 9bc2ecc..8c0588c
    Fast-forward
    diff.md | 1 +
    1 file changed, 1 insertion(+)
    C:\git\git-tutorial [master]>
    </pre>

11. Now that we have completed our bug update and merged our branches we can review out commit log to visualize the changes.
    * `$ git log --oneline --decorate --graph`
    <pre>
    C:\git\git-tutorial [master]> git log --oneline --decorate --graph
    \* 8c0588c (HEAD, tag: v1.0.1, master, diff-example) Commiting Diff example
    \* 9bc2ecc (origin/master, origin/HEAD) Added examples to introduction workshop
    \* f8a03b9 Created initial Be Social catgeory and updated Resouces category
    \* c838d60 Updated resouces
    \* 5470962 Updated links
    \* 01bb6a1 Formatting updates
    \* 82759f5 Cleaned up diff.md
    \* f1d994c Moved git commands learned in git basics workshop into a table
    \* d4480bd Cleaning up directory
    \*   94feb43 Updated git command pages
    |\
    | * 7ebebc7 Updated git command pages
    \* | 26f6c3b Added commands table
    \* |   08d40f6 Merge branch 'ManPages'
    |\ \
    | |/
    | * 9b8a09e Man Page updates
    \* |   9e1177d Merge branch 'documentCleaner'
    |\ \
    | * | ee72f5b spelling updates
    | * | c8c4128 slight formatting changes
    | |/
    \* | 1b73af0 Fixing Checkout delete
    |/
    \* 77992f4 Added initial "Working with remote repositories"
    \* d974719 Initial draft of "Branching and Merging"
    \* 61be5d9 Formatting updates
    \* 591b17f Initial Git Basics workshop commit
    \* 88062ad Initial Commit
    C:\git\git-tutorial [master]>
    </pre>

12. Once the work has been completed with this branch a pull request will need to be issued to the production repository.  This pull request will ask the production manager to review your changes and if approved to merge your branch with the production repository.

New commands used in this workshop

Command                                     | Description
------------------------------------------- | ------------------------
`$ git clone `                              | copy a git repository so you can add to it
`$ git checkout `                           | switch to a new branch context    
`$ git tag `                                | tag a point in history as important   
`$ git merge `                              | merge a branch context into your current one
`$ git log --oneline --decorate --graph`    | filter your commit history

# Be Social

## Fork a repository
If you want to contribute to someone else's project you or would like to use someone else's project as a starting point for a project of your own you would want to "Fork" their repository.  Forking will clone the origional repository and place it within your Github account.  
If you would like to help develope this git tutorial then Fork this repository by selecting the Fork button from the top of the page or by clicking [fork me](https://github.com/j0hnb/git-tutorial/fork_select "fork me").  Update and extend this repository and when you're done issue a Pull request so that your edits can be included in this master repository.


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