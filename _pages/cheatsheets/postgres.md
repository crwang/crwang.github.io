---
permalink: "/cheatsheets/postgres/"
layout: page
title:  "Postgres Cheatsheet"
---

<ol class="breadcrumb">
  <li><a href="/cheatsheets">Cheatsheets</a></li>
  <li>Postgres</li>
</ol>

## Overview

*   Relational
*   Support for JSON columns
*   Not case sensitive
*   Postgres for Mac: [http://postgresapp.com/](http://postgresapp.com/)

## Commands

~/Applications/Postgres.app/Contents/MacOS/bin/createuser -s chris

### Switch connections

`Type \c [database_name]; and then press ENTER`

### Exit Postgres command-line utility

`Type \q and then press ENTER to quit psql.`

## Connecting

[http://postgresapp.com/documentation/](http://postgresapp.com/documentation/)

Connection parameters When using a GUI program, here are the connection parameters you need to enter:

Host: localhost Port: 5432 (default) User: your user name Password: blank Database: same as user name If you need to provide an URL (eg. for Induction), use postgresql://YOURUSERNAME@localhost/YOURUSERNAME

## GUI Tools

### PG Commander

[https://eggerapps.at/pgcommander/](https://eggerapps.at/pgcommander/)

### PG Admin

[http://www.pgadmin.org/](http://www.pgadmin.org/)

### Induction

[http://inductionapp.com/](http://inductionapp.com/)

## Common pitfalls

*   Not including the path. ** Add to the ~/.bash_profile and use source ~/.bash_profile to reset it on the current terminal.