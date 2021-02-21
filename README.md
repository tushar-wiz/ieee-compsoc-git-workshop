# Setup
Install [Github's git GUI](https://help.github.com/articles/set-up-git/).

    $ git config --global user.name "Your Name"
    $ git config --global user.email your.email@example.com

Now's the time to pick an editor. Don't worry. Its not a speak now or forever hold your peace moment. For the purpose of this tutorial, we're sticking with the absolute basics for now, which is why we will be going with emacs.

    $ git config --global core.editor emacs


# Let's begin

First things first. How do you get a copy of the fancy projects (psst. they are called repositories) you see on github?

Its simple. You can either fork or clone a repository. A *fork* of the project is your personal copy of the project on your own github profile which can be *cloned* on to your local so that you can build on it or make changes at whim.You can find the fork button at the top right of the screen on a github repository

For now, let's clone this repository

    $ git clone https://github.com/chandrashritii/ieee-compsoc-git-workshop.git

Once you have cloned your repository, you should now see a directory
called `ieee-compsoc-git-workshop`. You now have your very own copy of the rpository. The techies call this the `working directory`. Let's make our way into the repository on our terminal.

    $ cd ieee-composoc-git-workshop
    $ ls


Let's look at this repository.

- README.md (This is the cover letter of your repository. What you write in it depends on you. *Psst. Always write good descriptions for you projects. Help the world possess better code.*)
- `.git` subdirectory (This is where all your repository’s history is kept). Let's take a look inside the `.git` folder. Run the following in your terminal :

    $ ls -a .git

You will see :

    branches  config  description  HEAD  hooks  info  objects  refs

# Get Started

## 1. Creating Files

We'll be creating files now. 

    $ nano file.md

Git provides you with a staging area. Adding files and data to the staging area is easy. Run :

    $ git add file.md

## 2. Committing Files

- Commit Messages

        $ git commit -m "your commit message"

- Signing off on your commits

        $ git commit -s -m "your commit message"

- Resetting your commit messages (We all make mistakes)

        $ git commit --amend

Forgot to signoff on your commit?

        $ git commit --amend -s

## 3. What did you just do?

- Checking git logs

You just made a commit. But what really happened behind the curtain?

To see all your commits, run :

    $ git log

Git log lists an index of all the commits, inclusive of the following details :

* Name of the Author
* Commit Date
* Commit SHA Number
* Commit Message

Want more details?

    $ git show

# Let's Rewind

- Refactoring and Fixing your bloopers

Mistakes are human and so is the ability to correct them. This is where its gets interesting. 

Let's open file.md and add some more content.

Now, let's see what we changed. Run :

    $ git diff

QnA: Why would you need to reset a commit?

# Working with branches

Creating a branch is easy. First, let's list all the current (live) branches. Run :

    $ git branch -a

The * against the branch name should indicate the current branch you are on, which at the moment should be main.

Let's create and switch to another branch.

    $ git checkout -b shriti

Now, let's add some content to the branch - 'shriti' and the run a diff to compare our changes with the main branch. Run :

    $ git diff main

# Let's merge

- Steps

       $ git checkout main

       $ git merge shriti

 You should now see a similar output :

    Merge made by recursive.
    file.md |    1 +
    1 files changed, 6 insertions(+), 0 deletions(-)
    create mode 100644 test.txt

- Recursive Merging
- Merge Conflicts (The soon to be bane of your existence)
    
    * Why do they happen?
    * Fixing Merge conflicts

# Cracking the whip


- How to go back to a particular state? [Better than time travelling ;)]

What happens if we don't like the content we've added to a commit? How do you retrace your steps?

We land on two scenarios here. 

1. The file is still in the staging area 

        $ git reset HEAD file.md

The output should look like :

        Unstaged changes after reset:

        M   file.md

2. The file has already been commited

     Here comes the tough stuff

- Rebasing (Interactive Mode)

        $ git rebase -i HEAD~6

- Cherry Picking

        $ git cherry-pick <commit-hash>
        $ git cherry-pick -x <commit-hash>