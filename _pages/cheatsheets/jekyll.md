---
permalink: "/cheatsheets/jekyll/"
layout: page
title:  "Jekyll Cheatsheet"
---

<ol class="breadcrumb">
  <li><a href="/cheatsheets">Cheatsheets</a></li>
  <li>Jekyll</li>
</ol>

## Commands

### Start the Server

```sh

# Start the server, by default it runs watch
$ jekyll serve

```

## Markdown

### Red Carpet

Supports github flavored-code comments.

Does not support css classes for markdown.

For tables to work we need to add to the _config.yml

```yaml
markdown: redcarpet # Triple backtick notation
redcarpet:
  extensions: ["no_intra_emphasis", "fenced_code_blocks", "autolink", "tables", "with_toc_data"]
```

For css for tables, for now, we can just take a global approach, using the bootstrap class:

```scss
table {
  @extend .table;
}
```

## Other Helps

[http://stackoverflow.com/a/28737999/466390](http://stackoverflow.com/a/28737999/466390)

[http://veithen.github.io/2015/03/26/jekyll-bootstrap.html](http://veithen.github.io/2015/03/26/jekyll-bootstrap.html)

[http://kvurd.com/blog/my-jekyll-blog-setup-bootstrap-sass-pygments/](http://kvurd.com/blog/my-jekyll-blog-setup-bootstrap-sass-pygments/)

[https://github.com/aahan/pygments-github-style](https://github.com/aahan/pygments-github-style)