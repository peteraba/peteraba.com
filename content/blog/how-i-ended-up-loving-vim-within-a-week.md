+++
date = 2014-09-13T15:52:26Z
draft = false
title = "how i ended up loving vim within a week"
tags = ["vim", "ide", "editor"]
section = "blog"
disqus_url = "http://peteraba.com/post/how-i-ended-up-loving-vim-within-a-week"
disqus_identifier = "how-i-ended-up-loving-vim-within-a-week"
disqus_title = "how i ended up loving vim within a week"
+++

Where I'm coming from?
----------------------

I mostly work with PHP and JS at work. I code a fair bit in Go, some in Python and less in some more languages in my free time. As most devs, I'm always in love with my current toolset, especially with my editors and IDEs.

I started writing code in Notepad++ a long-long time ago. Later I used Dreamweaver (I regret to admit), Eclipse, Netbeans, Sublime Text and "finally" PhpStorm. To be precise, I currently use PhpStorm as my main tool and Sublime Text when it makes more sense. It certainly does for programming in my secondary languages. In addition, I also use nano or joe for hacking stuff on remote servers. That's it, all 12 years of development in editor names.

I'm basically happy with this setup. PhpStorm is great for PHP and JS development while Sublime Text can do anything else I need.

About learning vim
------------------

### First 3 days - Vim Adventures (10-12 hours) ###

Obviously I've been hearing about how awesome vim and emacs can be once you master them, but I never really felt strong enough to get started with learning them. I still kind of had the idea of learning them in the back in mind for a long time, and therefore whenever something interesting popped up about vim in my feeds, I  saved it in my [pocket](http://getpocket.com/) for later reviewal.

Last Sunday, I was reviewing the massive list of stuff I had collected lately and an older item caught my attention: [Vim Adventures](http://vim-adventures.com/). I didn't feel like coding, so I decided to play around with it instead. I got caught up and after having completed the first 3 levels and after a bit of hesitation I bought the full version of the game. I played with it after work for 3 days and by the end of the day I got to my current level, level 14. I think it's the last level, but I could be wrong. I will probably finish the game sooner or later, but at the moment I'm way more excited about vim itself than the game.

Vim adventures (so far) has only taught me the very basics, mostly the core text editing features and a little bit about file handling, but I find the game to be very good at making you learn while having fun. Anyway, by level 14 I realised that vim can easily out-perform any editor I've used before. I never thought grabbing the current and next two paragraphs could be done in 5 key strokes. Even less did I think that it could turn out to be so much faster than doing it with a mouse! Same about grabbing the content of a quote with differentiating between inclusive and exclusive grabbing. And this is just the tip of the iceberg. It's very intuitive but requires you to re-learn pretty much everything you know about text editing.

Vim is often described as an editor that comes with its own language. You have to learn the language to use vim efficiently, but than it becomes mind-blowingly powerful.

### Last 3 days - derekwyatt.org and vimcasts.org (18-20 hours) ###

On Thursday I reviewed some other vim related items in my pocket, did some extra research and found some great resourses for vim:

 - http://derekwyatt.org/vim/tutorials/
 - http://vimcasts.org/
 - http://vimawesome.com/
 - http://www.vimgenius.com/

After another 3 days I've read and watched most of the relevant info on these great sites and I've grown to think that I might even make vim my main editor at some point.

### Sunday (6 hours?) ###

So today is Sunday and I decided this morning to blog about vim. I started writing my post in vim and during the process I noticed that for some old posts I still have json files in the header part of my markup files, while I lately use (toml)[https://github.com/toml-lang/toml] format instead.

I decided to use my new superpowers to fix this issue. Here's how it went:

 - I opened my files with :arga from vim
 - I turned my multiline json arrays into in-line ones in all files
 - I turned json format into toml in all files

Opening all my markdown files:

    :args content/**/*.md

multiline arrays on one line:

    :argdo %s/\n\s*\("[a-zA-Z0-9 -]*"\),\?$/\1, /g
    :argdo %s/, \n\s*],$/]/g

json to toml:

    :argdo %s/^{\|}$/+++/g

    :argdo %s/^\s*"\([a-zA-Z0-9_-]*\)"\s*:\s*\(\S\)/\1 = \2/g

    :argdo %s/",$/"/g
    :argdo %s/],$/]/g
    :argdo %s/true,$/true/g
    :argdo %s/false,$/false/g

I'm aware of the fact that I could have easily merged the last 4 commands into one, definietly less readable, command. Obviously I'm not a regexp guru, nor am I experienced in vim, so there might be a lot more things to optimise, but this already shows how great vim is. With the 6 commands above I refactored a bunch of files at once. I'm not sure how much longer it would have taken in PhpStorm, but my guess is a lot.

To be completely honest, I still ended up writing the majority of this post in Sublime Text after all. Why? Because its Markdown plugin is really nice, visually pleasing. On the other hand, it already started to frustrate the hell out of me not to be able to jump to the end of the line with a single key-stroke.

Vim is not IDE, or is it?
-------------------------

So far I've said vim is a great editor, but an IDE is so much more than that, right? Well yes, but vim can integrate so many external things with ease that you might even turn it into something like an IDE.

You can automatically:

 - do syntax highlighting
 - indent code properly
 - run lints
 - run hints
 - run external tools 
 - run tests
 - run debugger

That's almost everything I expect my IDE to do. With vim you we also have a handful of tasks done much better than in any IDE I know:

 - editing text
 - editing multiple files at once
 - creating macros
 - runnimg external programs
 - integrating external programs into your workflow
 
It also supports way more programming languages than any other IDEs, even more than Sublime Text will ever support.
 
Not to mention that vim is much-much faster than a Java based IDEs and consumes way less memory.

There's one thing I expect to be hard to do in vim: **code refactoring**. 

The search and replace functionalities and plugins of vim are great, but it will never deeply understand your code in my opinion. Unless of course someone writes a plugin that does or will...

Conclusions
-----------

I'm not going to abandon PhpStorm or Sublime Text yet and I think I won't for a long time. I will however use vim more and more. 

I'll start by using vim for my go projects and if that works out, I might start experimenting with using vim for PHP too. There are people out there who already think that it's as a [good idea](http://joncairns.com/2012/05/using-vim-as-a-php-ide/) too.

As a final note: I know I still have a lot of stuff to read, watch and try out and learn about vim. And emacs. I should really learn emacs too...