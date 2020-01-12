---
layout: default
title: Getting Started
nav_order: 2
---

# Getting Started
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

If this is the first time you are contributing to an open source project on GitHub,
you might feel overwhelmed by all the technical details you need to know about Git
and GitHub in general, and the OpenSSL workflow on GitHub in particular.
This page intends to guide you through your first steps. Also you can rest assured
that the OpenSSL team welcomes every new contributor and we are happy to answer your
questions and help you with any problem you might encounter during your first
pull requests.


## Getting started with GitHub

The GitHub Help site has detailed information about [Getting started with GitHub][get-started],
which we don't want to replicate here. If you never used Git version control system before,
take a look at the excellent [Pro Git][pro-git] book by Scott Chacon (a co-founder of GitHub)
and Ben Straub. It is free and you can read it online or download an offline copy.
The book serves both as a tutorial for beginners and a valuable reference for the experienced user.
It also contains a detailed introduction to GitHub in [Chapter 6][pro-github].


## Setting up the Repositories

The OpenSSL project maintains two source repositories: The main OpenSSL repository
at git.openssl.org and an official GitHub mirror at github.com (openssl/openssl).
Unless you are an OpenSSL team member who has commit access to the main repository
(short: a "Committer"), you can safely ignore the former repository for the moment.
In addition, you will create two more repositories for yourself, a public fork of
the OpenSSL repository, and a local working copy.


![repositories](/assets/images/repositories.svg)


| Repository                   | Name     |  URL/Location                            |
|:-----------------------------|:---------|:-----------------------------------------|
| 1: Main OpenSSL repository   | upstream |  git://git.openssl.org/openssl.git       |
| 2: Official GitHub mirror    | github   |  https://github.com/openssl/openssl.git  |
| 3: Your public GitHub fork   | origin   |  https://github.com/yourname/openssl.git |
| 4: Your local working copy   |          |  ~/src/openssl                           |


### Fork the OpenSSL GitHub Repository

Follow the [GitHub instructions][fork-a-repo] to create a fork of the OpenSSL GitHub mirror:

```
https://github.com/openssl/openssl.git -> https://github.com/yourname/openssl.git
```

### Clone your public fork into a local repository

For all examples, the local repository will be located at ~/src/openssl. Of course you can
choose a different location if you prefer.

```
~$ cd ~/src
~/src$ git clone https://github.com/yourname/openssl.git
~/src$ cd openssl
```

The git remote command now shows your clone as the origin:

```
~/src/openssl$ git remote -v
origin	https://github.com/yourname/openssl.git (fetch)
origin	https://github.com/yourname/openssl.git (push)
```
From now on, it will be assumed that all shell commands are issued in the ~/src/openssl
directory and the ~/src/openssl$ shell prompt will be shortened to a simple $.


### Add the GitHub mirror as second remote repository

```
$ git remote add github https://github.com/openssl/openssl.git
```

```
$ git remote -v
origin	https://github.com/yourname/openssl.git (fetch)
origin	https://github.com/yourname/openssl.git (push)
github	https://github.com/openssl/openssl.git (fetch)
github	https://github.com/openssl/openssl.git (push)
```

Your current `master` branch is currently tracking the `origin/master` branch, i.e.,
the `master` branch of your GitHub clone. This is not very useful, because GitHub
does not update the branches of a cloned repository automatically, when when the
parent repository changes. For that reason it is better to track the master branch
of the official GitHub mirror instea:

```
$ git branch --set-upstream-to=github/master
Branch 'master' set up to track remote branch 'master' from 'github'.
```

## The Pull Request Workflow


The OpenSSL pull request workflow is slightly different from the normal
[GitHub workflow][pull-requests] for pull requests, because pull requests are not
merged on GitHub directly. Instead, a committer merges the changes locally and pushes
them to git.openssl.org, from where they are immediately pushed to the GitHub mirror
by a script.

The following figure shows the OpenSSL pull request workflow. The parts which affect
only the committers, are greyed.

...WIP...

![repositories](/assets/images/workflow.svg)


### Update your local working copy

```
$ git fetch --all
```

### Implement the changes on a topic branch

### Push the topic branch to your clone

### Create the pull request



[pro-git]: https://git-scm.com/book/en/v2
[pro-github]: https://git-scm.com/book/en/v2/GitHub-Account-Setup-and-Configuration

[get-started]: https://help.github.com/en/github/getting-started-with-github
[fork-a-repo]: https://help.github.com/en/github/getting-started-with-github/fork-a-repo
[pull-requests]: https://help.github.com/en/github/collaborating-with-issues-and-pull-requests
