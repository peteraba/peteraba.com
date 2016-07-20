+++
draft = false
section = "blog"
title = "PhpStorm and IntelliJ tips"
description = ""
pubdate = "2014-11-02T20:16:00+02:00"
date = "2014-11-02T20:20:00+02:00"
keywords = ["ide", "phpstorm", "intellij"]
tags = ["ide"]
disqus_url = "https://peteraba.com/post/phpstorm-and-intellij-tips/"
disqus_identifier = "phpstorm-and-intellij-tips"
disqus_title = "PhpStorm and IntelliJ tips"
+++

PhpStorm
--------

I find Jeffrey Way's series on PhpStorm extremely useful even after 2 years of using the software. Please
check out his series on [laracast.com](https://laracasts.com/series/how-to-be-awesome-in-phpstorm).

On the other hand, Jeffrey uses a Mac therefore he's keyboard layout and keymap preferences are somewhat different from 
mine. Feel free to adapt whatever you like from both of us. My keys were only really tested on Debian linux.

Short keys

 * **Alt+0:** Toogle Project window. By default, PhpStorm sets it to Alt+1, but that just doesn't work for me on Debian.
 * **Ctrl+P:** The default Ctrl+Shift+N isn't too bad either. But finding files is just too  important to miss Sublime's 
 default Ctrl+P.
 * **Ctrl+Shift+P:** File structure in a key stroke. Nice. Default Ctrl+F12 is just crazy. Ctrl+Shift+Alt+N is often too 
 much of a hassle...
 * **Ctrl+Alt+O:** Pull repository. (Only makes sense because of Ctrl+Shift+O)
 * **Ctrl+Alt+P:** Push repository.
 * **Ctrl+Shift+D:** Adding to default Alt+J makes selecting the occurrences of the word under the cursor so much 
 easier...
 * **Ctrl+Shift+V:** Split vertically. Jeff suggests using Ctrl+V, I guess that probably makes more sense on the Mac...
 * **Ctrl+Shift+H:** Split horizontally. Works like a charm
 * **Ctrl+W:** Close tab.

As a final note on PhpStorm, keep in mind that JetBrains also has some 
[hello](https://www.jetbrains.com/phpstorm/documentation/phpstorm-video-tutorials.jsp) on the topic.


Intellij
--------

I'm experimenting with the big gun for various reasons and I found a couple of things missing or behaving differently.

### Monokai ###

The great Monokai style is not available under IntelliJ by default. You can download it from 
[github](https://github.com/y3sh/Intellij-Colors-Sublime-Monokai), but it is less than perfect at the moment and was 
especially painful when comparing commits. At the moment I keep this scheme disabled.


