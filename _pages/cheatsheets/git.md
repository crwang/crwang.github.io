---
permalink: "/cheatsheets/git/"
layout: page
title:  "Git Cheatsheet"
---

<ol class="breadcrumb">
  <li><a href="/cheatsheets">Cheatsheets</a></li>
  <li>Git</li>
</ol>

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