---
permalink: "/cheatsheets/mac-terminal/"
layout: page
title:  "Mac Terminal Cheatsheet"
---
<ol class="breadcrumb">
  <li><a href="/cheatsheets">Cheatsheets</a></li>
  <li>Mac Terminal</li>
</ol>

[https://github.com/tomislav/osx-terminal.app-colors-solarized](https://github.com/tomislav/osx-terminal.app-colors-solarized)

Different colors for different languages

[https://github.com/stephenway/monokai.terminal](https://github.com/stephenway/monokai.terminal)


## Bash Profile

**~/.bash_profile**

```sh
# Add this to allow killing of the background job
alias kk='jobs -p | xargs kill -9'
```

## Dvorak gotchas

If you're like me, you use dvorak and Mac's built in Dvorak - Querty layout.

But, there's a bug in their layout that causes `ctrl + c` not to work on the terminal.

The workaround is to use the alternative command: `cmd + .`
