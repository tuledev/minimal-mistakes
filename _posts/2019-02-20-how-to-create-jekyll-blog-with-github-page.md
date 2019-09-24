---
title: A fast way to create a blog with Jekyll and Github Pages
categories:
  - Jekyll
tags:
  - Jekyll
  - Minimal Mistakes
  - Github Pages
---

# 2019-02-20-how-to-create-Jekyll-blog-with-github-page

_In this post, I will explain step-by-step how I created this simple blog in a short time_

**Many thanks to** [**Minimal Mistakes**](https://github.com/mmistakes/minimal-mistakes)

My blog's using

* Github Pages
* [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) theme base on Jekyll
* Markdown format for posts

My blog features:

* Writing posts with markdown format
* Tags, categoris
* Comment
* Share

There are many ways to use Jekyll, I chose Minimal Mistakes and Github Pages because it's the simplest way I can find.

## How to fork Minimal Mistakes theme and host blog in Github Pages

There are 3 ways to [install](https://github.com/mmistakes/minimal-mistakes#installation) Jekyll themes. I chose forking the repo so it's easy to use with Github Pages

1. Fork [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) repo
2. Change the forked repo name to your github usename `{username}.github.io`
3. DONE. You have a blog at `https://{username}.github.io` \(For the first time, the blog will be available in a few minutes\)

You have a blog with inititial data now. Look at [quick-start-guide](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/#), you can custom many things with less effort.

## Site settings section

With `# Site Settings` section in `_config.yml`, you can update:

```text
# Site Settings
title                    : "tuledev Blog"
title_separator          : "-"
name                     : "Anh Tu Le"
description              : "A personal blog."
masthead_title           : "Play With Me"
```

## Author section

With `# Site Settings` section in `_config.yml`, you can update:

```text
# Site Author
author:
  name             : "Anh Tu Le"
  avatar           : "assets/images/ic_author.png" # image that you add to assets folder
  bio              : "Working Programmer"
  location         : "Ho Chi Minh - VN"
  email            :
  links:
    - label: "Email"
      icon: "fas fa-fw fa-envelope-square"
      url: mailto:tule.developer@gmail.com
```

## Footer section

With `# Site Author`, you can custom footer link items.

## Posts

You can write posts with Markdown format, and then commit/push them to master branch. For more format details, you can read here [Woking with posts](https://mmistakes.github.io/minimal-mistakes/docs/posts/#)

## Tags, Categories

Because Github Pages work with Liquid, you just need to copy [tag-archive](https://github.com/tuledev/tuledev.github.io/blob/master/tag-archive.md), [category-archive](https://github.com/tuledev/tuledev.github.io/blob/master/category-archive.md) and paste them to the root folder.

## Comment plugin

Custom comment plugin in `_config.yml` also. Enable in

```text
# Defaults
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: true // here
      share: true
      related: true
```

Custom facebook **appid** from facebook comment plugin in. For creating facebook appid, you can read more here [Facebook](https://developers.facebook.com/docs/apps/)

```text
comments:
  provider               : "facebook"
  facebook:
    appid                : "APP_ID"
    num_posts            : # 5 (default)
    colorscheme          : # "light" (default), "dark"
```

_All the sources for this blog, you can find at my_ [_repo_](https://github.com/tuledev/tuledev.github.io)

