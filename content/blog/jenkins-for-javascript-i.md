+++
draft = false
section = "blog"
title = "Jenkins for Javascript I."
description = "I actually thought that setting up Jenkins to properly test a PHP based application is hard. Then I tried to do the same for JavaScript..."
pubdate = "2012-11-21"
date = "2012-11-21"
keywords = ["jenkins", "javascript", "continious integration"]
tags = ["jenkins", "javascript", "continious integration"]
thumbnail = "/images/jenkins-for-javascript-i.png"
+++

I actually thought that setting up Jenkins to properly test a PHP based application is hard. Then I tried to do the same for JavaScript... I'm currently half way there, but I think I already learnt enough to make up for a quick post.

As an effort to make the code for this blog as clean and good as possible, I decided to set up Jenkins. It wasn't a big deal until I made my mind up that the frontend part should also be tested there. That's where all hell broke loose.

In my previous post, I was actually mourning about the fact that setting up proper debugging is not that easy for PHP. It's not too hard, but you definietly won't get it out of the box. For CI, I could complain about that fact that you need to install and configure a handful of software to make the wonderful PHP template work. Still, it is very straight forward, no thinking is mandatory.

Now for JavaScript, and especially frontend JavaScript, it's a whole different story.

Testing framework
For PHP we have phpUnit. It's a defacto standard. It ships with a runner, assertion library, mocking framework, even some BDD support. Of course there are other tools out there - some of them are really good too -, but if you want to sell your product as tested, you're going to mention phpUnit somewhere for sure.

JavaScript however is just fragmented all the way. I'd dare to say QUnit is a defacto standard for frontend JavaScript, but no one would use it for Node.js

Also, as JavaScript is just way cooler nowadays than PHP is, developers tend to prefer the cooler BDD to traditional TDD. For that, they have JasmineJs and Mocha, both promises to be usable for both frontend and backend JavaScript. I have quite a bit of background using QUnit and Jasmine, but not Mocha. I took a look at the project page of Mocha and it seemed promising and familiar at the same time, so I decided to use whichever framework I can get running on Jenkins easier.

To make my life a bit harder on this matter, I happen to work on a headless virtual machine so anything that requires a real life browser is out of the question.

Education
As I lacked the experience on the subject, I searched throughout the world wide web and my favorite frontend sources about setting up continuous integration for frontend. I found a lot of threads and comments about it, but hardly any tutorials. The only thing I could absorb was that I should setup JsTestDriver. That's basicly a server that can be taught about the testing needs of your project and can run them in browser clients. You do need to connect the client to the server first. I gave it a try, but I found it rather tedious comparing to my cli based php testing tools.

I need a headless browser
I found two promising candidates for running my tests and chose the seemingly more popular PhantomJs. (Just in case you wonder I since then learned that there are a bunch of other ones: http://stackoverflow.com/a/814929)

The problem this time turned out to be that normally you fire up your headless browser just the same way as a regular one, meaning that there is no such option - as far as I know - as open some file in batch mode, than quit. Fortunately, there are projects just for that, but it didn't seem to be available out of the box.

So I actually first setup JsTestDriver with PhantomJs, using js-test-driver-phantomjs. Now I was finally able to run some tests, but was still far from satisfaction, as the default test library shipped with JsTestDriver does not appeal to me. Fortunately, there is some QUnit module and also a third party module for Mocha.

These two I can't yet comment on, as I found another working solution: mocha-phantomjs that caught my attention which so far I like it too. Although you should note that you need add assertion and mock libraries for mocha to really take adventage of it. Still, I need to figure out how to add code coverage to it.

Conclusion?
There's no real conclusion as of yet, but I can tell you that I have spent a lot of time even to get here. At the moment I'm happy about having test results, jshint and csslint results in my builds. Next up is code coverage which might make me change my current stack altogether. After that, I hope I'll be able to evaluate how good these testing stacks really are.

Side note
I found a really interesting - but not yet stable - project that promises to solve all these issues out of the box. It's called Buster.Js. Unfortunately, it didn't work for me and I haven't been able to give them feedback about my issues. I'll try to do that as this project could really change the frontend JavaScript world in my opinion.