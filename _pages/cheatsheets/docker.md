---
permalink: "/cheatsheets/docker/"
layout: page
title:  "Docker"
---

<ol class="breadcrumb">
  <li><a href="/cheatsheets">Cheatsheets</a></li>
  <li>Docker</li>
</ol>

## Running on MacOS

https://github.com/codekitchen/dinghy

## Aliases

Helpful aliases for ~/.bash_profile

```sh
alias dc="docker-compose"
alias dcrw="docker-compose run --rm web"
alias dcrwx="docker-compose run --rm web bundle exec"
alias dcbx="docker-compose run --rm web bundle exec"
alias dcbx="docker-compose run --rm web bundle exec"
alias dcbxrspec="docker-compose run -e RAILS_ENV=test -e COVERAGE=1 --rm web bundle exec rspec"

function docker_clean() {
  docker rm -v $(docker ps -a -q -f status=exited)
  docker rmi $(docker images -f "dangling=true" -q)
}
```

