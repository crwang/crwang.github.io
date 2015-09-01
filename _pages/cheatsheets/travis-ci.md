---
permalink: "/cheatsheets/travis-ci/"
layout: page
title:  "Travis CI Cheatsheet"
---

<ol class="breadcrumb">
  <li><a href="/cheatsheets">Cheatsheets</a></li>
  <li>Travis CI</li>
</ol>

### Node.js Peer dependencies

For now, in our .travis.yml file in the root directory, add the dependent peer dependency to pre-install it.

Here's an example for pre-install `rendr`

```yaml
language: node_js
node_js:
  - "0.12"
  - "0.10"
notifications:
  email: false
before_install:
- npm install rendr
```


