## The news feed

### What is it?
The news feed allow to notify EAF usersdirectly within the application as seen in the below screencast:

![News in JupyterLab](https://user-images.githubusercontent.com/8435071/201953604-91e97e7c-4e89-4964-b9e4-cf488d7d0d6d.gif)

The news will be displayed as a toast only once. Then it will be only silently notified (accessible through the notification
center). And if the user dismiss the news, it will not see that news any longer.

### How does it work?

This repository builds a [GitHub pages website](https://docs.github.com/en/pages) that will be published at https://fermilab-eaf.github.io/newsfeed/.

The website is using [Jekyll](https://jekyllrb.com/). And the news feed is generated by the plugin [jekyll-feed](https://github.com/jekyll/jekyll-feed/tree/v0.15.1); the Atom feed is accessible at https://fermilab-eaf.github.io/newsfeed/feed.xml.

The feed plugin is parametrized to list only the most recent post (see the [configuration](./_config.yml)).

### How to draft a news?

To propose a news, you need to create a new PR that adds a new file in the folder [_posts](./_posts) named _YYYY-MM-DD-NAME-OF-POST.md_. You must replace _YYYY-MM-DD_ with the date of your post and _NAME-OF-POST_ with the name of your post.

The file itself must follow this structure:

```md
---
layout: post
title: "Thanks for using JupyterLab"
date: 2022-11-02 14:00:00 -0000
categories: posts
excerpt: "Big thanks to you, beloved JupyterLab user."
---

# Welcome

Thanks a lot for your interest in JupyterLab.
```

The header must contain the following entries:
- _layout_: Set to `post`
- _title_: Your post title
- _date_: The date and time for the post
- _categories_: Space separated list that must contains `posts`
- _excerpt_: Short summary of the post

The notification displayed in JupyterLab will be the concatenation of the _title_ and the _excerpt_ as plain text.

After the header, you can write the post using Markdown formatting.

> That part won't be displayed in JupyterLab but the notification will have a link to see it.

You will find additional information in the [GitHub documentation](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-content-to-your-github-pages-site-using-jekyll#adding-a-new-post-to-your-site).

