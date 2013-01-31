# Git Tutorial
This tutorial will give you a chance to learn Git through real world examples.
Our branching model derrives "A successful Git branching model" - http://nvie.com/posts/a-successful-git-branching-model/

##Objective

## Overview
Create a GitHub Account
Setup your local Git account
Link your locak git to Github
Fork a repository
Make local edits to a new branch
Sync branch to GitHub


## Download and Install Git
Download and install the latest version of Git. http://git-scm.com/downloads

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


Recources:
https://help.github.com/articles/set-up-git