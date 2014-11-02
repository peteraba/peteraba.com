+++
date = 2014-08-06T17:23:51Z
title = "first Impressions of hugo"
tags = ["open source", "go", "hugo"]
keywords = ["open source", "go", "hugo"]
disqus_url = "http://peteraba.com/post/first-impressions-of-hugo"
disqus_identifier = "first-impressions-of-hugo"
disqus_title = "first impressions of hugo"
+++

Prerequisite
------------

So I'm lately enjoying Go as my langauge of choice and [Hugo](http://hugo.spf13.com/) is an open source site generator written in Go. It is a new project when you compare it to alternatives like Wordpress or Joomla but even when compared to the big fish of the genre: [Jekyll](http://jekyllrb.com/).

Since I haven't done any blogging for ages, I had the urge to start over from scratch, hopefully lasting longer and having a much better sprint this time. Anyway, I felt like giving Hugo a try and it turned out so well that after two months of thinking about it, I decided to launch two sites more or less at the same time. A more traditional blog just about my day to day life in IT/Programming and one [dedicated to teaching programming](http://devmonk.com/).


Static Site Generators
----------------------

I think it might make sense to clearify what a static site generator is, before diving into too much details about Hugo itself.

There's a growing trend, mostly among programmers and other technical people, to leave all the fancy backend stuff off their blogs and small websites and write their content in plain text. Some even go as far as writing full html pages in pure html files. While this is clearly feasible, hardly practical, as most of us don't like to write html when doing creative work, a.k.a. writing posts. Instead, most of us would prefer working only on the very core, the content of a new post or page and having a system to render that content into the final html. 

This html generation is the very basic functionality of site generators, but of course generator software tend to know a lot more about our website and provide more space for customalization. Still, tthey usually prefer simplicity over feature-richness and tend to get into the way of content creation is little as possible.

So why is it better than, let's say, a Wordpress blog? Well, while it certainly lacks in features and power, it static site generator beat any CMS / Blog engine a couple of things:

 * Workflow fits the technical mindset better (vi, git, etc.)
 * Next post can always be worked on offline
 * Unbeatable performance (Not to mention scalablity)
 * No need to install or maintain a database
 * Has a bad-ass feel to it for geeks :)
 * Page generated on localhost will (almost) always be the same as on server
 * Can be hosted freely by GitHub --> great for open source project sites.


Markdown
--------

While it is not mandatory, usually site generators support some formatting syntax for text that users write. The two most common syntaxes are plain html and [markdown](http://en.wikipedia.org/wiki/Markdown). While html may provide (when left unfiltered) full control over the final outcome, markdown is nicer to read and write. Hugo, as many others, support both format and even allows the usage of html tags within a markdown text.

If you're interested in seeing markdown in action. You can take a quick look at the raw version of this post on github [here](https://raw.githubusercontent.com/peteraba/peteraba.com/master/content/blog/first-impressions-of-hugo.md).


Hugo
----

#### Upside ####

As I've already mentioned, Hugo got my interest because it was written in Go and it was one of the few open source Go projects that had a bit of a following at the time I found it. Granted, Hugo is not yet stable and has it's shortcomings, it does have a bit to offer:

 * A server that looks for file modifications and generates static sites automatically
 * Live update (refreshes browser on modifications)
 * Good documentation
 * Extra post information can be defined in 3 different formats (json, yaml, toml)
 * Supports custom taxonomies 
 * Html and Markdown formats can be mixed
 * Pretty Urls and Randomized urls
 * Dynamic menu creation
 * Rss generation
 * Html and Go template language for layouts
 * Easy templating
 * Partials
 * Redirects
 * Support for relative and absolute urls
 * Completely cross platform (thanks to Go)
 * Fast build times (~1ms per page)
 * Helpful and friendly community

#### Downside ####

Again, Hugo is not yet stable, so it's too early for critising, but at the moment I miss two features:

 * Real pagination instead of only being able to limit the number of rendered posts.
 * A way to be consistently access all pages. At the moment I can only access all pages from the homepage and posts belonging to the section inside on section list page.

#### Conclusion ####

The lack of aforementioned features don't bother me too much, because I believe that these will sorted out shortly. And if they don't, I'll be always able to hack the feature in since it's in Go and it is open source. All-in-all great job guys!
