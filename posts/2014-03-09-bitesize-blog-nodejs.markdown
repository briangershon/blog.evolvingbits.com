---
layout: post
title: "Bitesize Blogging via Node.js"
date: 2014-03-09 17:07
comments: true
categories:
- Programming
tags:
- node.js
- JavaScript
---
Over the last couple of weeks, I rebuilt my blog so that I could:

* keep my content in a repository all by itself, in a simple markdown format.

* support a responsive design based on a popular framework rather than create custom themes based on the blog framework.

* generate the website on the fly from the markdown files, and not from a "static website generator" nor a database.

It's intentionally built on small and specific node.js modules with the idea that others can take those components and roll their own blog as well.  Some components I built myself, and others are existing ones from the node community.

The primary configuration and blog content are in their own Git repository, written in Markdown with YAML Front-Matter (yfm). The blog itself is in another Git repository -- it's largely data driven from the config file.

This borrows from Octopress and Hexo (having a config and yfm content), but differs in that mine is split into two separate repositories -- content is separate from the blog code and design itself.

Also, Octopress and Hexo are static site generators. Mine grabs all content from the Git repo and caches that. This allows me to contribute content to my site without having to rebuild it manually each time and push the built version.

### Why another blog solution?

I'm a big fan of the Jekyll-based static blog sites, namely writing markdown files and saving in GitHub.

I enjoyed Octopress, and started porting to Hexo, but I really just want to have my content in a repo that is separate from the blog code and design itself.  I also wanted to use presentation libraries directly [like Zurb's Foundation](http://foundation.zurb.com), rather than learn a specific theme framework for the static generator.

This has led to developing the `bitesize` JavaScript library, which won't generate a static site, but will source the blog markdown content from a GitHub repo.

If you're interested in creating your own custom blog, the full source is at <https://github.com/briangershon/bitesizeblog> and if you want to see how the content is formatted, see <https://github.com/briangershon/blog.evolvingbits.com>
