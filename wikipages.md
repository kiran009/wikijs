---
title: GIT submodules
description: GIT submodules
published: true
date: 2019-08-30T06:23:32.934Z
tags: 
---

# GIT Submodules

Git allows you to include other git repositories called submodules, checkout of an external project.

Submodule support includes support for adding, updating, synchronizing, and cloning submodules.

Submodules maintain their own identity.

The Parent repo stores the submodule repository location and commit id.

You have a choice to clone none, few submodules.

Adding submodule to the repository:

git submodule add git@github.com:kiran009/newproject.git A/B/C/D/newproject
.gitmodules
[submodule "A/B/C/D/newproject"]
    path = A/B/C/D/newproject
    url = git@github.com:kiran009/newproject.git
Initialization:

git submodule init
git submodule update
Cloning:

Cloning a repository containing submodules

git clone --recursive [URL to Git repo]
Updating submodules:

git submodule update --init
# if there are nested submodules:

git submodule update --init --recursive
# download up to 8 submodules at once

git submodule update --init --recursive --jobs 8
git clone --recursive --jobs 8 [URL to Git repo]
# pull all changes in the repo including changes in the submodules

git pull --recurse-submodules
# pull all changes for the submodules

git submodule update --remote
Executing commands in submodules:

git submodule foreach 'git reset --hard'
# including nested submodules

git submodule foreach --recursive 'git reset --hard'

