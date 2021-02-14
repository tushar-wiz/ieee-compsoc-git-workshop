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

## 2. Committing Files

- Commit Messages
- Resetting your commit messages (We all make mistakes)
- Signing off on your commits

## 3. What did you just do?

- Checking git logs


# Rewind

- Refactoring and Fixing your bloopers

- Why would you need to reset a commit?

- How to go back to a particular state? [Better than time travelling ;)]

# Working with branches

# Let's merge

- Steps
- Recursive Merging
- Merge Conflicts (The soon to be bane of your existence)
- Fixing Conflicts