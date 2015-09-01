---
permalink: "/cheatsheets/node/local-npm/"
layout: page
title:  "Node: Local NPM Modules"
---

<ol class="breadcrumb">
  <li><a href="/cheatsheets">Cheatsheets</a></li>
  <li><a href="/cheatsheets/node">Node.js</a></li>
  <li class="active">Local NPM Modules</li>
</ol>

http://podefr.tumblr.com/post/30488475488/locally-test-your-npm-modules-without-publishing

```bash
cd /path/to/package.json
```

Then run the pack command:

```bash
npm pack
```

This will create, in the same directory, a tarball named after the name of the project + the version specified in the package.json.

This is exactly what is published to npmjs.org! You can now see what’s inside

```bash
tar -tf packagename-version.tgz
```

Or you can install it in your project to test it in integration.

```bash
cd path/to/your/project/
npm install ../path/to/your/npm/packagename-version.tgz
```
