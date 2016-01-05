---
layout: post
category : posts
title: "Creating Custom Dashboards in Gerrit"
tagline:
tags : [gerrit, tutorial]
---

Gerrit has a powerful mechanism for creating dashboards.

There are two different formats for creating dashboards:

1. git config - based format
2. URL parameters

The git config based format can be used for storing the dashboards in gerrit and are useful for project dashboards.

The URL parameter approach is useful for sharing different dashboards and for user dashboards (which can be customized by URL).

## Create a user dashboard

User dashboards can be created with the URL parameter approach.

https://gerrit-review.googlesource.com/Documentation/user-dashboards.html#project-dashboards

Gerrit Dash Creator is a really helpful tool to get started because it takes a git config file-formatted dashboard file and converts it into the URL which you can then use adhoc and by adding that URL to your dashboard.

https://github.com/openstack/gerrit-dash-creator

## Create a project dashboard

### Add dashboard to gerrit

In order to add a dashboard into gerrit's project's dashboard area, you must add a git config file-formatted dashboard file into a branch off of `/refs/meta/dashboards/*`

Here was a helpful approach I found to actually getting a branch created up there:

http://comments.gmane.org/gmane.org.wikimedia.wikivideo/534

```sh
git checkout --orphan custom-dashboards
vim my-dashboard
git reset # if needed to make sure other files aren't going to be committed
git add my-dashboard # name of the git config file-formatted dashboard file
git commit -m "add dashboard"
git push origin custom-dashboards:refs/heads/tmp
```

Then, go to the branch menu in gerrit project admin, add branch `/refs/meta/dashboards/my-dashboard` with id of the above commit.

**Default Site Dashboard**

```yaml
[dashboard]
    title = This Dashboard Name
    description = Description of this dashboard
[section "You are a reviewer, but haven't voted in the current revision"]
    query =  NOT label:Code-Review<=2,self reviewer:self project:the_project_name status:open limit:50
[section "Open Changes"]
    query = status:open project:the_project_name limit:20
[section "Recently Merged"]
    query = status:merged project:the_project_name limit:50
```

I've named this dashboard `main` by substituting `my-dashboard` with `main`

### Edit dashboard

```sh
git fetch origin refs/meta/dashboards/site:refs/remotes/origin/meta/dashboards/site
```

### Add dashboard to the project's config for default

#### Check out meta/config

```sh
git fetch origin refs/meta/config:refs/remotes/origin/meta/config
git checkout meta/config
```

#### Update project.config

```yaml
[dashboard]
    default = refs/meta/dashboards/site:main
```

In this example, `site` is the name of the branch, `main` is the filename in that branch.

ie, `refs/meta/dashboards/site` has a file called `main`


```sh
git commit -a -m "add Project dashboard"

# directly:
% git push origin meta/config:meta/config

# via review:
% git push origin meta/config:refs/for/refs/meta/config
```

### Flush the cache (if necessary):

https://gerrit-review.googlesource.com/Documentation/config-gerrit.html

If the dashboard doesn't show up, you may need to flush the cache to get the dashboard to show up.

```
% ssh gerrit gerrit flush-caches --cache projects
```

The command I use:

```
% ssh -p 29418 gerrit.yourdomain.com gerrit flush-caches --cache projects
```

#### Notes

**Deleting remote dashboards**

If you need to delete a remove dashboard, you can use this command:

```
git push origin :refs/meta/dashboards/site
```

## References & Tools

### Gerrit dashboard documentation

https://gerrit-review.googlesource.com/Documentation/user-dashboards.html

### Dashboard Creator

Creates the URL for a dshboard

https://github.com/openstack/gerrit-dash-creator
