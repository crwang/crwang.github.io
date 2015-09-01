---
permalink: "/cheatsheets/git/"
layout: page
title:  "Git Cheatsheet"
---

<ol class="breadcrumb">
  <li><a href="/cheatsheets">Cheatsheets</a></li>
  <li>Git</li>
</ol>

## Config
**~/.gitconfig**

https://gist.github.com/crwang/bbf8bd09c826d49189f5


## Rebasing

[https://www.atlassian.com/git/tutorials/rewriting-history](https://www.atlassian.com/git/tutorials/rewriting-history)

### Flow if I'm the only one working on the branch

The normal flow if I need to rebase a development branch.

```sh

# Pull the latest from origin
$ git checkout develop

$ git pull

$ git checkout [my-branch]

# Do the interactive rebase
$ git rebase -i develop

# Overwrite the branch on origin
$ git push -f origin

```

## Update Forked Repo

http://stackoverflow.com/questions/7244321/how-to-update-github-forked-repository

```bash
# Add the remote, call it "upstream":

git remote add upstream https://github.com/whoever/whatever.git

# Fetch all the branches of that remote into remote-tracking branches,
# such as upstream/master:

git fetch upstream

# Make sure that you're on your master branch:

git checkout master

# Rewrite your master branch so that any commits of yours that
# aren't already in upstream/master are replayed on top of that
# other branch:

git rebase upstream/master
```

## Squash all commits

http://stackoverflow.com/questions/1657017/how-to-squash-all-git-commits-into-one

`git rebase --root -i`
