+++
title = "10 Years Later"
date = 2023-12-03T13:52:21+01:00
draft = false
tags = ["personal"]
+++

![Image with a tree in time and seasons](/media/10-years-later/top.png "Image of passing time")

After 4 years of inactivity, I decided to give this blog a new, more modern look. It also made me want to reflect on the past a bit. This is a very personal post, there are no technical details below.

### Good ol' PHP Times

This blog has its first posts from 2012 when I was still very focused on PHP. I'm sure the original posts were hosted somewhere else, because [hugo](https://github.com/gohugoio/hugo) didn't even exist yet, but I'm not even sure where or how.

2012 was one of the most important years in my life: In May 2012 my partner and I decided to leave our home country behind, and we moved to Berlin 4 months apart. I joined the Berlin-based venture capital giant [Rocket Internet](https://www.rocket-internet.com/). I was never really fond of the company, and grew to dislike its top management especially, but I liked my teams very much. The first under future Hello Fresh and Tier CTO [Nuno Simaria](https://www.linkedin.com/in/nsimaria/), and then under the leadership of [Tobias Reuter](https://www.linkedin.com/in/tobiasreuter/) who I consider my primary role model as a manager still to this day. In both teams I got to know a lot of great people, but I didn't necessarily grow much as an engineer, other than ditching [SVN](https://en.wikipedia.org/wiki/Apache_Subversion) for [Git](https://en.wikipedia.org/wiki/Git).

Next year I joined a little startup, partially for much better compensation, partially for the false promise of the possibility of growing into a lead role soon after. From my past in Hungary, I was pretty familiar with [Magento](https://en.wikipedia.org/wiki/Magento), a popular [Zend Framework-based](https://en.wikipedia.org/wiki/Laminas) e-commerce platform. I knew how to use various caches effectively, or how to optimize MySQL servers to make Magento run reasonably fast even on affordable virtual servers. At my new company, I also learned a fair bit about how to make Magento work nicely with other systems using RabbitMQ. By then, I knew Magento well enough to fully understand its inherent design flaws and shortcomings. (I'm looking at you, Magento [entity-attribute-value](https://en.wikipedia.org/wiki/Entity%E2%80%93attribute%E2%80%93value_model), you over-engineered beast.)

### Discovering Go

Late into 2013, I had an idea to create a new, much more performant, open source e-commerce platform. I decided that the first step in doing that would be to have a large test suite from the get go, so that performance will be first class citizen, not a feature. I wanted a system that can handle at least 100K products with ease, and for that I set out to be able to generate random data for testing my future system. I'm not entirely sure if I was using any frameworks for this task, but I think I was using a recent version of vanilla PHP. It worked, but it was JUST SOOO SLOOOOW.

In my frustration trying to make the tool fast, I stumbled upon a new language which was hyped to provide easy parallelism: Go. I installed it and my life changed almost instantly. I was able to recreate my random generator tool in a few hours. I remember that Go's type safety already prevented a few small bugs at that point, and I loved the fact that I got feedback without running my application, as things broke at compile time, which probably took less than a second. The feedback loop was just perfect. And not only that, the code also looked more appealing to me than the PHP tool I had crafted with my then 10+ years of professional PHP coding experience. More importantly, Go actually generated my data 2 orders of magnitude faster than PHP did. I just loved every bit of this. The tooling was a little lacking, especially when it came to editors, but I was ready to sacrifice a bit of typing speed for the much better performance. 

While I started using Go for its superior speed, I soon found myself being even more fond of its type safety, and the lack of all the unnecessary OOP shenanigans which top-notch PHP meant at the time. No inheritance, no unnecessary abstractions, just getting shit done. Still to this day I think that its object-oriented mixed procedural programming paradigm is the best for general development, though in the meanwhile I also gained some experience in - and respect for - functional programming.

Mind you, this was Go 1.1 or Go 1.2 times. It was funny hearing [Go guru Bill Kennedy](https://twitter.com/goinggodotnet?lang=en) say the other day that [he also started with Go 1.2](https://youtu.be/0YU4D1TgkrE?si=Aj0LlhACEvSzwEk8). I don't claim to know the language to the extent Bill does, but it sure puts me in a small group of people who've been around the language for a pretty long time.

I appreciate how much the language has improved since, while also remaining almost fully backwards compatible. I still find the language elegant. I also think that the language creators' relentless push back regarding language changes is a great asset preserving the simplicity of the language. Still, 10 years later it's still easy to learn the language, and most best practices still apply 10 years later. (That said, I also think that the time has come to introduce some backwards compatibility breaking changes, most notably a proper enum type.)

In case anyone was wondering, I still have some plans to create a performant open source e-commerce platform, but it's not a whole lot closer to anything presentable than it was 10 years ago. On the other hand I still enjoy [learning new programming languages](/blog/go-is-my-gateway-drug/), and about new technologies. Maybe I'll find time to write about some of them soon.

### Management, episode I.

In 2014, I was ready to find a new job. Partially I wanted to do something new, partially I felt that the company was heading in the wrong direction. (To this day this is the only company I worked for that no longer exists.)

I already frequented the Berlin Go meetup, which usually took place around an average pub table at the time, but I didn't really find anything Go position caught my interest and fit my abilities at once. Instead, I decided to go into management and joined a venture-backed e-commerce startup called [Westwing](https://www.westwing.de/) as a Lead Engineer. I have very fond memories of that time, but 3 years later the company decided to close down its Berlin office, meaning I needed to find new challenges again. (Shout out to [Josemi](https://www.linkedin.com/in/josemiliebana/), my lovely lead and mentor there.)

In the meanwhile, I was partially busy implementing things in PHP, half of my time went into managing people, improving tooling, and providing technical guidance when needed. Go remained my interest, I kept tinkering with it at home.

When we were let go (no pun intended), I knew I was in the right place and time to switch to Go as my main stack. Go has gained a lot of momentum during my time at Westwing, and I was ready to [swing back to a developer role](/blog/3-recent-posts-on-tech-management-i-loved/#the-engineermanager-pendulum). That said, I hadn't interviewed in years at that point, so I decided to do a few "dummy interviews" at companies I didn't really want to join. My second such dummy interview was with Zalando, a company very well known in Berlin, but one I found too big for me to be an interesting option. However, I was interviewed by a small group of engineers, out of which there was a very tall nerd, that I found to be super smart and knowledgeable. I thought to myself, I could learn from this guy, so when I got an offer, I decided to join as a Software Engineer. To be honest, I was a fair bit upset that my future title wouldn't have "senior" in it, after all I had been senior for quite a while by then. Luckily the engineer who impressed me the most, [Adrian](https://www.linkedin.com/in/adrian-stoewer/), also didn't have the senior title, which I found ridiculous, but on the other hand it also made it easier for me to accept a non-senior role.


### Going Go

Our first multi-year project was to replace a PHP monolith in Go. As you can probably imagine, this included a lot of PHP work at the beginning, but after 6 months or so, I was finally fully working with Go. Not only that, but also mostly working with Postgres, whereas previously I only worked with MySQL as my database. I learned a lot from my teammates, especially [Nikolai](https://www.linkedin.com/in/nikolaykrapivchenko/) and Adrian. I will always remember our hour-long discussions geeking out on topics like the optimal value for allowed cyclomatic complexity, or whether we should strive to support ease-of-use for frontend in our API design, or be more strict, representing the business logic more honestly instead.

In the meanwhile I also tried to convince a few friends to switch from PHP to Go. I tried to couch some of them, and I did my best to provide them with [useful Go resources](/blog/everything-you-need-to-know-to-start-with-go/) to kickstart their journeys. (There's at least one great guy who found these either useful or at least motivating, right [Rael](https://www.linkedin.com/in/raelschmulian/)? \*\* INSERT GREAT SUCCESS MEME. \*\*)

It was certainly exciting times for me, but not as exciting as the birth of my daughter in June 2018. A few months later I started my year-long parental leave, which left me with enough time to take care of my firstborn, learn new things, create a CMS, and to blog a little as well. Not so surprisingly the last entry is from right before I returned to the workforce. This time as a Lead Engineer.

### Back to Management

I was excited to lead the team I left behind as a software engineer. It was also interesting to be a co-lead again, this time sharing the position with Nikolai. We started off under the guidance of our lovely, funny, visionary and just slightly crazy lead, [Claudia](https://www.linkedin.com/in/claudia-lajeunesse-gaicd-0395633/). I wish she stayed around longer in the company, but I'm grateful for her time with us.

One of the first things I needed to push for is to get rid of scrum. It wasn't necessarily easy, but I was really happy with the system we set up instead. It was fun to read article after article about the end of scrum in the past 4 years. I just wish I wrote about that sooner. At this point it might not make that much sense, I think by now the industry understands that [scrum](https://www.linkedin.com/pulse/scrum-slowly-dying-david-pereira/) [is](https://blog.logrocket.com/why-scrum-is-becoming-irrelevant/) [dead](https://chrisjameslennon.medium.com/the-age-of-scrum-is-over-185407ad705b). Long live, Agile!

To be honest, while this change was exciting and exhaustive, it was nothing compared to all the projects we had to ship while struggling to hire and ramp up more people. We always managed to deliver what we promised. If not on time, then with acceptable delays. I'm proud of what I and we have achieved in the past for years, riddled with personal issues, covid and the birth of my second child.

There have been a lot of changes in my life since then, and of course not only in mine. We've all learned how to deal with a pandemic, how to do remote work effectively, and many of us learned how to cope mentally with a generally much more dangerous world.

### 4 years later

Yesterday I opened my blog at night, and the light background hurt my eyes so badly, I finally decided to give this blog a little upgrade. I'd like to revisit some of my older posts and reflect on them after many years. If for nothing else, it would be an interesting exercise for myself to see how my thinking has changed. And now this post will stay here for a while to serve as a reminder for myself to write more often. We'll see if it works.

So the bottom line is: If this reads as a goodbye, it is not meant to be. It is a thank you, and a hello again!
