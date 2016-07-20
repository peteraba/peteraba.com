+++
draft = true
section = "blog"
title = "Test PHP versions and projects with Docker in minutes"
description = "Docker is definitely gaining momentum among developers as lightweight virtual-machine, helping developers replicating faking live environments or even deploying built images. However I think many still fail to realise the potential of Docker as an easy and fast way to \"install\" and test tools"
pubdate = "2016-07-20T11:53:23+01:00"
date = "2016-07-20T01:51:55+01:00"
keywords = ["php", "docker"]
tags = ["php", "docker"]
thumbnail = ""
disqus_url = "https://peteraba.com/post/docker-for-php-developers"
disqus_identifier = "test-php-versions-and-projects-with-docker-in-minutes"
disqus_title = "Test PHP versions and projects with Docker in minutes"
has_code = true
+++

Docker is an awesome technology used by more and more people and companies for developement and software delivery world-wide. I think most developers have heard of it by now, many have probably tried it too. None the less, I thought it might be useful for some to show how to get started with it.

I've never had a problem installing Docker via the [official installation page](http://docs.docker.com/engine/installation/), so there's no need for me to add anything regarding that.

Once you have it up and running, feel free read [the user guide](http://docs.docker.com/engine/userguide/) or check out the following post for some inspriration first.

#### Check the magento2 codebase with PhpMetrics in minutes

[Magento 2](https://github.com/magento/magento2.git) is out, so let's get some idea about the code base by running [PhpMetrics](http://www.phpmetrics.org/) on it.

```bash
git clone git@github.com:magento/magento2.git src
cd src
git checkout 2.1.0
cd ..
wget https://github.com/phpmetrics/PhpMetrics/raw/master/build/phpmetrics.phar
chmod +x phpmetrics.phar
wget https://peteraba.com/media/test-docker-versions-and-projects-in-minutes/zzz-custom.ini
docker run -it -v "$PWD"/src:/src:ro -v "$PWD"/phpmetrics.phar:/phpmetrics.phar:ro -v "$PWD"/zzz-custom.ini:/usr/local/etc/php/conf.d/zzz-custom.ini:ro php:5.6 bash -c 'time php /phpmetrics.phar --report-cli /src/app/code'
```

So maybe it's been a bit too much at first, so let's break it down to smaller steps:

 1. Checkout magento2 codebase into **src** directory.
 1. Change the working directory to **src**.
 1. Check out the tag we're interested in: **2.1.0**.
 1. Check out the parent directory again. *This step is only needed to make the `docker run` command a bit nicer.*
 1. Download the latest [phpmetrics](https://github.com/phpmetrics/PhpMetrics) phar from github.
 1. Make phpmetrics executable.
 1. Download a simple PHP config file which will set the memory limit, to allow the tool to use up to 2GB of memory.
 1. Finally run `docker run` to create a new instance (so called container) of an image. This one might be a bit complex for docker newbies first, so I'll break it further down. I'll start in the middle, working my way more or less outwards:
   1. **php** is an image name that docker will try to start up. Docker will first look for the image on the local machine. If not found, it will try to fetch it from [dockerhub](http://hub.docker.com/). It might be noteworthy that docker hub is not the only [docker registry](https://docs.docker.com/registry/) but the official and default one. The image can be pulled explicitly (via `docker pull php`), but in our case it will happen automatically when we run `docker run`. In this example docker will find the [official PHP image](https://hub.docker.com/r/_/php/) on dockerhub and it will get downloaded right away.
   1. **5.6** is a tag name which specifies a version of the image. If not provided, docker will assume **latest**. The available tags are always listed on docker hub.
   1. `docker run php:5.6 bash` creates and starts a new container from the image and executes the bash command. By default docker will run the command in the background and it will shut the docker container down as soon as the command finishes. In this case, this would happen immediately as bash will exit without a tty. (See next step for details.)
   1. `docker run -it php:5.6 bash` is the same command as before but with the instructions of starting the container in interactive mode and with a pseudo-tty. This will basically allow you to interact with the container
   1. `docker run -it php:5.6 bash -c 'time php /phpmetrics.phar --report-cli /src/app/code'` only adds the command which bash will need to execute. In this case it will run **phpmetrics.phar** with cli reporter for the output and it will run on the remote directory **/src/app/code/**.
   1. `docker run -it -v "$PWD"/src:/src:ro -v "$PWD"/phpmetrics.phar:/phpmetrics.phar:ro -v "$PWD"/zzz-custom.ini:/usr/local/etc/php/conf.d/zzz-custom.ini:ro php:5.6 bash -c 'time php /tools/phpmetrics.phar --report-cli /src/app/code'` links 2 local directories and a file into the container. The arguments can be split into 3 parts by the colon character: local path, remote path and options. Only the remote path is required and "*PWD*" in the local path only serves to save as from typing the full path. The *ro* options at the end mean that the directory or file will be read-only inside the container.
   1. Finally, `docker run -it -v "$PWD"/src:/src:ro -v "$PWD"/phpmetrics.phar:/phpmetrics.phar:ro -v "$PWD"/zzz-custom.ini:/usr/local/etc/php/conf.d/zzz-custom.ini:ro php:5.6 bash -c 'time php /phpmetrics.phar --report-cli /src/app/code'` only adds the command which bash will need to execute. In this case it will run phpmetrics.phar with cli reporter for the output and it will run on the remote directory **/src/app/code/**.
 1. Once inside, we can just use the pre-installed phpmetrics tool and request a cli output.
 1. Type exit to get back to your host and shut down the container.


#### PHP 5.6 vs PHP 7.0

In software development, new versions are almost always advertised with performance benefits, right? PHP is no exception and the upcoming 7.0 is said to come wtih major speed improvements too. Of course no one is using it in production yet (hopefully!), so to some extent this will only be proven by time. Still, we can try to get a sense of this by running something with both versions and it only takes a couple of minutes. This isn't really the best indicator of real world speed improvements, but surely fun.

Let's see how long it takes for 5.6 to finish again:

```bash
docker run -it -v "$PWD"/src:/src:ro -v "$PWD"/phpmetrics.phar:/phpmetrics.phar:ro -v "$PWD"/zzz-custom.ini:/usr/local/etc/php/conf.d/zzz-custom.ini:ro php:5.6 bash -c 'time php /phpmetrics.phar --report-cli /src/app/code'
```

```
real	10m33.115s
user	3m15.456s
sys	6m53.836s
```

Let's see how 7.0 performs:

```bash
docker run -it -v "$PWD"/src:/src:ro -v "$PWD"/phpmetrics.phar:/phpmetrics.phar:ro -v "$PWD"/zzz-custom.ini:/usr/local/etc/php/conf.d/zzz-custom.ini:ro php:5.6 bash -c 'time php /phpmetrics.phar --report-cli /src/app/code'
```

```
real	4m36.014s
user	2m29.476s
sys	1m35.052s
```

So it seems like PHP 7 performed easily outperformed 5.6 in this particular case. Obviously your results might be different, and thanks to docker, it takes close to nothing for you to test it yourself.

I plan to write a post on how to co-ordinate multiple containers and then perhaps building an image too, but let's see how that pans out.

