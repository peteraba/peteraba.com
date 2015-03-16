+++
date = 2014-08-09T23:16:51Z
draft = true
title = "installing php5.5 on debian wheezy"
disqus_url = "http://peteraba.com/post/dont-die/"
disqus_identifier = "peteraba http://peteraba.com/?p=peteraba"
disqus_title = "don't die"
+++

E = Unable to locate package bzip2-dev
apt-get install libbz2-dev

configure = error: Please reinstall the libcurl distribution -
    easy.h should be in <curl-dir>/include/curl/
apt-get install libcurl4-openssl-dev

configure = error: jpeglib.h not found.
apt-get install libjpeg-dev

configure = error: png.h not found.
apt-get install libpng12-dev

configure = error: freetype-config not found.
apt-get install libfreetype6-dev

configure = error: Unable to detect ICU prefix or no failed. Please verify ICU install prefix and make sure icu-config works.
apt-get install libicu-dev

configure = error: mcrypt.h not found. Please reinstall libmcrypt.
apt-get install libmcrypt-dev

configure = error: xslt-config not found. Please reinstall the libxslt >= 1.1.0 distribution
apt-get install 
