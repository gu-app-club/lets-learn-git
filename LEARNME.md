# Git Guide

This is basically a reference guide for the lab today. You're joining a tradition set forth by the founders of GUMAD many years ago: signing the `README.md`!

Find the slides from the lecture at https://lets-learn-git.now.sh. 

## Prereqs

### Git!

It's helpful if you have git installed.

#### 🍎 Mac Installation

##### Step 1: Install Homebrew

[Homebrew](https://brew.sh/) is a package manager for mac. You'll need it for a bunch of stuff.

Install by copy/pasting the following into your terminal:

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

##### Step 2: Install git

Once you have brew, you can type the following in your terminal to install git:

```
brew install git
```

Woo you have git.

#### 🐧 Linux Installation

If you're on Ubuntu or any other debian based system, just run the following in your terminal:

```
sudo apt-get install git
```

If you're not on Debian based systems, you get to figure this one out yourself.

#### 😭 Windows Installation

If you're on windows, install it by following [the steps here.](https://git-scm.com/download/win)

You'll get a terminal as part of the installation, that will be what we mean by "terminal" for you during this process.

### A reasonable OS (kinda)

FYI: like most things, this guide is easier in linux or mac. It's still very possible, but you may run into some annoyances. If you haven't switched yet, this might serve as a good wakeup call to give using a unix-based operating system (Mac or Linux) a try.

If you're a windows user trying to switch to mac, try [Ubuntu](https://www.ubuntu.com/)! It's modern, friendly version of linux that runs everything you need. Many of us used it as our main OS for a long while.

It's much, much nicer than the lubuntu linux VM that they had you try in your CS 121 or Operating Systems classes.

If you're on windows and really, really don't want to switch, you can still complete this lab. It's cool. We won't judge that much.

### The command line

If you can open your terminal and know what `cd` and `ls` do, then you're good. No fancy wizardry here, we'll explain any other commands used.

### A text editor

You'll need some way to edit raw text files. (IE: Not microsoft word). [Visual Studio Code](https://code.visualstudio.com/) or [Atom](https://atom.io/) are popular free choices.

## Lab Steps

If you missed it during the presentation, you can find the steps here.

### Step 0 - Verify git's installed

If you can type `git` in the terminal and you get something that looks like this:

```sh
usage: git [--version] [--help] [-C <path>] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

...
```

Then your good.

### Step 1 - Clone the repo

First things first, you'll need this github repository.

You can get it by going to [the repo on github](https://github.com/gu-app-club/lets-learn-git), clicking
on the big green button, and copy/pasting that link into a command like this:

```
git clone PUT_THE_LINK_HERE
```

### Step 2 - Make a change to the file

Next, open up the README.md file in a text editor and add your name to the bottom of the list!
Don't forget to keep up the format!

### Step 3 - "add" your file to your local changes

Next you'll need to add your changes to your local changes:

```
git add README.md
```

### Step 4 - Check your "status"

Next, check that all went well with:

```
git status
```

It should look something like this:

```sh
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

### Step 5 - "Commit" to your changes

Finally, we'll `commit` our changes with:

```
git commit -m "Added Grace Hopper"
```

If you forgot the `-m` and git opened up vim, you can exit
by pressing `esc` and then typing `:wq` and pressing enter. You'll need to run it again,
but if you get stuck, ask one of the club leaders for help! (That's why we're here!)

### Step 6 - "Push" your changes

Now that we're all committed, we need to `push` our commit up to the repository in the cloud (on Github!)

We can do that with:

```
git push
```

### Step 7 (maybe) - "Pull" someone elses changes

If git won't let you push, it may ask you to "pull" the changes before "push"ing.

We can do that with:

```
git pull
```

### Step 8 (maybe) - "Merge" your changes

If git still won't let you push, it's probably because you've hit a merge conflict!

Open up the file in your editor, and you'll see several lines like: `<<<<<<<`.

These create two different groups of text, some that's your changes and some that's
other people's changes.

It might look something like this:

```
<<<<<<< HEAD
- Evan Conrad
=======
- You McYouFace
>>>>>>> branch-a
```

Your goal is to be the smart human and "merge" these manually. Remove the `<<<`, `>>>`, and `===` markers
and combine the two pieces of text so it looks something more like this:

```
- Evan Conrad
- You McYouFace
```

Once your done, `git add` your changes:

```
git add README.md
```

And then `git commit -m "Merge"`. 
