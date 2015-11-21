+++
title = "Test PHP projects with Docker in minutes"
draft = true
description = "Here's how I use docker to test out new tools"
keywords = ["php", "docker"]
tags = ["php", "docker"]
pubdate = "2015-11-17T01:51:54+01:00"
date = "2015-11-17T01:51:55+01:00"
section = "blog"
thumbnail = ""
disqus_url = "http://peteraba.com/post/test-php-projects-with-docker-in-minutes"
disqus_identifier = "test-php-projects-with-docker-in-minutes"
disqus_title = "Test PHP projects with Docker in minutes"
has_code = true
+++

Docker is an awesome technology used by more and more people and companies for developement and software delivery world-wide. I think most of my readers have at least heard of it many also tried it. None the less, I thought it might be useful for some to show how to get started with it.

I've installed it both on Linux and OSX and both went super smooth, so I'll just point you to the [official installation page](http://docs.docker.com/engine/installation/).

Once you have it up and running feel free read [the user guide](http://docs.docker.com/engine/userguide/) or check out the following post for inspriration first.

#### Check the magento2 codebase with phpmetrics in minutes

[Magento 2](https://github.com/magento/magento2.git) is out, let's get some idea about the code base by running [phpmetrics](http://www.phpmetrics.org/) on it.

```bash
host$ docker pull peteraba/php:5.6-cli
host$ git clone git@github.com:magento/magento2.git src
host$ cd src
host$ git checkout 2.0.0
host$ docker run -it -v "$PWD":/src:ro --name=mag2 --rm peteraba/php:5.6-cli-dev zsh
container$ time phpmetrics --report-cli /src/app/code
exit
```

So maybe it's been a bit too much at first so let's break it down:
 - We pull down a php image from [docker hub](https://hub.docker.com/). This image happens to be created by me and has many popular cli tools pre-installed, phpmetrics being one of them.
 - We checkout the magento2 code base into the `src` directory.
 - We cd into the `src` directory.
 - We check out the tag we're interested in (2.0.0).
 - And we docker run to create a new instance (so called container) from the image we downloaded in the first point. This one might be a bit complex at first, so I'll break it further down:
   - *peteraba/php* is an image name that docker will look for. It will first look for it on the local machine. If not found it will look for the php image of the user peteraba on dockerhub.
   - *5.6-cli-dev* is a tag name which specifies a version of the image. If not provided, docker will assume `latest`.
   - *docker run peteraba/php:5.6-cli-dev zsh* creates and starts a new container from the image and execute the zsh command. By default docker will run in the background and shut the docker container down as soon as the command finishes, which in this case would be a matter of miliseconds.
   - *docker run -it peteraba/php:5.6-cli-dev zsh* is the same command as before but with the instructions of starting the container in interactive mode and with a pseudo-tty. This will basically allow you to interact with the container
   - *docker run -it -v "$PWD":/src:ro peteraba/php:5.6-cli-dev zsh* attaches the current directory as /src to the docker container, making it possible to access the magento codebase. The optional `:ro` at the end of the directive makes the directory read-only within the container. Technically the directory is linked so changes made to it on the host will be represented inside the container immediately. (At least on OSX and Linux it is so.) Both the local and container paths have to be absolute, hence the "$PWD". On Windows you probably need to provide a real absolute path or come up with a different solution.
   - *docker run -it -v "$PWD":/src/:ro --name=mag2 --rm peteraba/php:5.6-cli-dev zsh* is our final command here. The --name directive tells docker to start to create the new container with the name 'mag2'. Since you can only have one container with a certain name, this command would fail the second time if you didn't remove the existing container first. That's what --rm takes care of.
 - Once inside, we can just use the pre-installed phpmetrics tool and request a cli output.
 - Type exit to get back to your host and shut down the container.


#### Php 5.6 vs Php 7.0

In software development, new versions are almost always advertised with performance benefits right? Php is no exception and the upcoming 7.0 is said to be a major improvement too. Of course no one is using it in production yet (hopefully!) so to some extent this will only be proven by time. Still, you can get a sense of this by running something have on the two versions in a couple of minutes. This isn't really the best indicator of real world speed improvements, but surely fun.

Let's see how long it takes for 5.6 to finish again:

```bash
host$ docker run -it -v "$PWD":/src:ro --name=mag2 --rm peteraba/php:5.6-cli-dev zsh
container$ time phpmetrics --report-cli /src/app/code
container$ exit
```

And now 7.0-RC7 is up:

```bash
host$ docker pull peteraba/php:7.0-cli
host$ docker run -it -v "$PWD":/src:ro --name=mag2 --rm peteraba/php:7.0-cli-dev zsh
container$ time phpmetrics --report-cli /src/app/code
container$ exit
```

Impressive, isn't it? Next time we'll look at an example of using multiple containers together and then perhaps building an image too. Until then, check out the tools pre-installed in [my php images](https://hub.docker.com/r/peteraba/php/) and give me feedback using the regular forums.

