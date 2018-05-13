+++
draft = false
section = "blog"
title = "Polyglot Tinkering - Moving to Firefox with Python"
description = "How Python saved my day when it turned out Firefox and Lastpass have limited support for each other"
pubdate = "2018-05-13T14:22:00+01:00"
date = "2018-05-13T14:22:00+01:00"
keywords = ["python", "firefox", "lastpass"]
tags = ["python", "firefox", "lastpass"]
thumbnail = ""
disqus_url = "https://peteraba.com/post/polyglot-tinkering-moving-to-firefox-with-python"
disqus_identifier = "polyglot-tinkering-moving-to-firefox-with-python"
disqus_title = "Polyglot Tinkering - Moving to Firefox with Python"
has_code = true
+++

### Firefox?

I started working as a webdeveloper during the spring of 2002, less than a year after IE6 came out.
For those who have ever heard about IE6 it should be obvious that this means
that I spent a significant amount of my life working around the various quirks of IE and of course
that I was at one point in my life a huge [Firefox](https://www.mozilla.org/en-US/firefox/new/?utm_medium=referral&utm_source=firefox-com) fan.
Firefox was amazing at the time but unfortunately it became slower and slower with each iteration
and by the time Google Chrome came around most webdevelopers were ready for something much faster.
I used a fair number of browsers since but I always found myself going back to Chrome for one
reason or another and so did the majority of my colleagues.

I was a bit sceptical but also excited about [Rust](https://www.rust-lang.org/en-US/) and
[Servo](https://servo.org/) and I tried out the new Firefox as soon as it came out as stable.
I loved its speed and many of its features but I had two major issues with it on Linux:

1. for some reason I had no sound after a few days and it never came back.
2. Lastpass sucked as the copy password feature seemed broken.

So I again went back to Chrome even though I prefer to de-Googlize myself as much as I can.

### LastPass?

Okay, so let's fast-forward a few months until I read
[Calling all web developers: here's why you should be using Firefox](https://stories.jotform.com/calling-all-web-developers-heres-why-you-should-be-using-firefox-983f012d4aec)
and decided it was time to give Firefox another shot.
This time sound was working just fine but Lastpass still had issues copying my password.
When I opened a page with a password stored the password was filled out just fine, but I couldn't
easily search for a stored password and copy it.

This is a huge problem for me.

I hope I don't even have to mention how important password managers are in general but for me having autofill
is just not enough. Period. I store tons of passwords and notes which I often have to copy to access various things
and opening a detail page in my Lastpass Vault is just way too slow to be a viable option.

So at this point I decided to create my first support ticket with LastPass.
Their response was fast, brief and quite disappointing. In essence it said:

> I am sorry to inform you that Firefox browser on Linux does not support binary feature.
> Binary feature is required for copy username and copy password.

Well, I guess this would just mean back to Chrome to most people, but I instead decided to come up
with a tool to solve my problem.
I did not mean to fix everyones problem nor was I thinking of some fancy project on Github with stars and all.
I wanted something quick and dirty, something that's fun for me to write and solves my problem in a way that
I'm no longer blocked from using Firefox as my primary browser.

### Clarifying the project

Here were my requirements:

1. I need to be able to access my notes and passwords for use cases other then logging into websites. (For that autofill works fine)
2. The solution must be at least as fast as using the LastPass Chrome Extension:
  1. Realise I need to enter a password to get my work done
  2. Open / Go to Chrome
  3. Open LastPass browser extension
  4. Search for my password
  5. Right click on the entry I need
  6. Copy note or password

My first idea was to create a small desktop application which sits in my system tray and lets me look up passwords as needed.
Then I figured that what I'd really want is to have a keyboard shortcut to open this application which would allow me to
search instantly.
Finally I realised that I'll start with a CLI app and I'll think about how to start it up once it works in a terminal.

### Lastpass CLI

This thought process took about 2-5 minutes and in the meanwhile I found
[lastpass-cli](https://github.com/lastpass/lastpass-cli) which looked like something I could use,
except that it required multiple command calls to achive what I wanted.

I tested out how to solve my problem using my shell (Bash / Zsh):

1. lpass login
2. lpass ls | grep "my-favorite-server"
3. select the id of the server I want to access (using a mouse)
4. lpass show "id-of-my-favorite-server"
5. copy the note or password to clipboard (using a mouse)

```
my-favorite-server [id: 1112223334445556667]
Username: root
Password: my-super-safe-password
Hostname: 123.234.432.321:12345
NoteType: Server
```

Okay, so it seemed like I can really kind of do what I need by using `lpass`, `grep` and `xclip`
but I'll also need to be able to select one of the results of the search if there's more than one.
Now I happen to be a reasonably experienced terminal user and `Bash` coder for someone who's never been paid to be a sysadmin,
but to be honest I felt disgusted by just thinking of the amount of script needed for this tool, mostly because manupulating
strings is cumbersome in Bash. It is much nicer in `zsh` but most of the time I need to stick to `bash` and my `zsh` is
therefore quite basic.

### Finding a tool that fits

Okay, so if not `Bash` then what? Well, this is such a simple task that could be done in almost any programming language
I'm aware of (`Elm` being the exception) but at first I only really thought about the ones I use every day to keep things simple.
However I didn't happen to like them for this task:

- `PHP` feels bloated for wrapping CLI calls plus it's not installed on all my computers
- `Go` also feels a bit clumsy for wrapping CLI calls because of it's type safety.
- `JavaScript` is not a contender for me because I don't like `Node`.

Well, out of the above choices I'd choose Bash without hesitation in this case but then I remembered that sysadmins
tend to love `Python`. I never used Python heavily but I was sure that I'd be doing less answer-hunting on stack-overflow
than for Bash and that I'd like the end result more and that it is a better fit for the task than my primary languages.

### Hacking is fun

It took me about an hour to hack together what I needed.
I have to admit the resulting code is not something I'll ever be proud of:

- The script only works on Linux systems as it is
- I even made a decision during development that I won't create functions, just to keep things simple. (Sorry, not sorry.)
- I'm sure one could have achieved what I did in less than 20 minutes both with Python or Bash / Zsh.

Using Python however proved to be a blast and I think the end result is readable even if it lacks real craftmanship.
Hell, hacking is still fun!

One of the coolest things about being a programmer is that you get to solve many of your own problems with relative ease.
It's especially true if you take the time to wander to programming problems, principles and languages which you don't use every day.
Python certainly rocks although I'll probably never work on anything serious using it.

### Result

If this is an itch you share with me, feel free to use the script I wrote: https://github.com/peteraba/dotfiles/blob/master/scripts/lps

To make it really efficient I recommend using a Quake-like terminal like [Guake](http://guake.org/) so that it's always one key-stroke away.

With my this script my routine to retrieve a random password looks like this:

 - Realise I need to enter a password to get my work done
 - Hit F12 to open Guake (unless I'm already in a terminal)
 - Type `lps my-favorite-server`
 - Select one of the many results by typing a number and hit `Enter` (unless there's only one result)

At this point the script tells me that the note or password is already copied to my clipboard.
This is way faster than using the Chrome Extension saving me at least 1-2 minutes every day.
More importantly I can now fully embrace any new browser, the lack of a LastPass extension shouldn't hold me back ever again.