+++
title = "10 Years Later"
date = 2023-12-03T13:52:21+01:00
draft = false
tags = ["personal", "career", "php", "go"]
+++

![Image with a tree in time and seasons](/media/10-years-later/top.png "Image of passing time")

After four years of inactivity, I decided to give this blog a new, more modern look. It also made me reflect on the past a bit. This is a very personal post. There are no technical details below.

### Good ol' PHP Times

This blog has its first posts from 2012, when I was still very focused on PHP. I'm sure I hosted the original posts somewhere else because [hugo](https://github.com/gohugoio/hugo) didn't even exist [yet](https://github.com/gohugoio/hugo/commit/50a1d6f3f155ab837310e00ffb309a9199773c73), but I don't even remember where or how.

2012 was one of the most important years in my life: In May 2012, my partner and I decided to leave our home country behind, and we moved to Berlin 4 months apart. I joined the Berlin-based venture capital giant [Rocket Internet](https://www.rocket-internet.com/). I was never really fond of the company, and grew to dislike its top management especially, but I liked my teams very much. The first one was under future Hello Fresh and Tier CTO [Nuno Simaria](https://www.linkedin.com/in/nsimaria/), and then under the leadership of [Tobias Reuter](https://www.linkedin.com/in/tobiasreuter/), who I still consider my primary role model as a manager to this day. In both teams, I got to know many great people, but I didn't necessarily grow much as an engineer, except that we ditched [SVN](https://en.wikipedia.org/wiki/Apache_Subversion) for [Git](https://en.wikipedia.org/wiki/Git) at some point.

Next year, I joined a smallish startup, partially for much better compensation and partially for the false promise of the possibility of growing into a lead role soon after. From my past in Hungary, I was pretty familiar with [Magento](https://en.wikipedia.org/wiki/Magento), a popular [Zend Framework-based](https://en.wikipedia.org/wiki/Laminas) e-commerce platform. I knew how to use various caches effectively, and how to optimize MySQL servers to make Magento run reasonably fast on affordable virtual servers. At my new company, I learned a lot about RabbitMQ and how to build distributed systems. By then, I knew Magento well enough to understand fully its inherent design flaws and shortcomings. (I'm looking at you, Magento [entity-attribute-value](https://en.wikipedia.org/wiki/Entity%E2%80%93attribute%E2%80%93value_model), you over-engineered beast.)

### Discovering Go

Late into 2013, I had an idea to create a new, much more performant, open-source e-commerce platform. I decided that the first step would be to have an extensive test suite from the get-go so that performance will be a first-class citizen, not a feature. I wanted a system that could handle at least 100K products with ease, and for that, I set out to be able to generate random data for testing my future system. I don't remember if I used any frameworks for this task, but I was probably using a recent version of vanilla PHP. It worked, but it was JUST SOOO SLOOOOW.
In my frustration trying to make the tool fast, I stumbled upon a new language hyped to provide easy parallelism: Go (often referred to as Golang at the time).

I installed it, and my life changed almost instantly. I was able to recreate my random generator tool in a few hours. I remember that Go's type safety already prevented a few minor bugs at that point, and I loved that I got feedback without running my application, as things broke at compile time, which probably took less than a second. The feedback loop was just perfect. And not only that, the code also looked more appealing to me than the PHP tool I had crafted with my 10+ years of professional PHP coding experience. More importantly, Go generated my data 2 orders of magnitude faster than PHP did. I just loved every bit of this. The tooling was lacking, especially regarding editors, but I was ready to sacrifice some typing speed for much better runtime performance.

While I started using Go for its superior speed, I soon found myself even more fond of its type safety, explicitness, and the lack of all the unnecessary OOP shenanigans that top-notch PHP meant at the time. No inheritance, no unnecessary abstractions, no wondering about execution path because of exceptions thrown, just getting shit done. I still think that its mainly procedural programming paradigm is the best for general development, though I have also gained some experience in - and respect for - functional programming in the meantime.

Mind you, this was Go 1.1 or Go 1.2 times. Hearing [Go guru Bill Kennedy](https://twitter.com/goinggodotnet?lang=en) say the other day that [he also started with Go 1.2](https://youtu.be/0YU4D1TgkrE?si=Aj0LlhACEvSzwEk8) was funny. I don’t claim to know the language to the same extent as Bill, but it does put me in a small group of very early adopters.

I appreciate how much the language has improved since then while remaining almost entirely backwards-compatible and adding relatively few new features. While the low number of new features might sound bad to some, I think it's the only way to prevent unnecessary bloat. Ten years later, it's still easy to learn the language. Most best practices I learned then still apply today. (That said, the time has come to introduce some backwards-compatibility breaking changes, most notably a proper enum type is long overdue.)

In case anyone was wondering, I still plan to create a performant open-source e-commerce platform, but it's not much closer to anything presentable than it was ten years ago. On the other hand, I still enjoy [learning new programming languages](/blog/go-is-my-gateway-drug/) and new technologies. Maybe I'll find time to write about some of them soon.

### Management, Episode I.

In 2014, I was ready to find a new job. I wanted to do something new, and I felt the company was heading in the wrong direction. (To this day, this is the only company I worked for that no longer exists.)

I already frequented the Berlin Go meetup, which usually took place around pub tables at the time. We didn't need to find conference rooms that would fit 100+ people like today. I found no Go positions that were both fitting and interesting simultaneously. Instead, I decided to venture into management and joined an e-commerce startup called [Westwing](https://www.westwing.de/) as a Lead Engineer. I have fond memories of that time, but the company closed its Berlin office three years later, meaning I needed to find new challenges again. (Shout out to [Josemi](https://www.linkedin.com/in/josemiliebana/), my lovely and extremely dedicated lead. Not many would fly to Berlin three days a week for three years straight to be close to their teams!)

While there, I was partially busy implementing things in PHP. Half my time went into managing people, improving tooling, and providing technical guidance when needed. Go remained my interest, and I kept tinkering with it at home.

### Going Go

When the company let us go (no pun intended), I knew I was in the right place and time to switch to Go as my main stack. Go has gained a lot of momentum during my time at Westwing, and I was ready to [swing back to a developer role](/blog/3-recent-posts-on-tech-management-i-loved/#the-engineermanager-pendulum). That said, I hadn't interviewed in years at that point, so I decided to do a few "dummy interviews" at companies I didn't really want to join. My second dummy interview was with [Zalando](https://zalando.de/), a company well-known in Germany but one I found too big to be an exciting option. However, I was interviewed by a small group of engineers, out of which there was a very tall, nerdy guy whom I found super knowledgeable: [Adrian](https://www.linkedin.com/in/adrian-stoewer/), whom I call a friend these days. I thought to myself that I could learn from this guy, so when I got an offer, I decided to join as a Software Engineer. I was pretty upset that my future title wouldn't have "senior" in it. After all, I had been a senior for quite a while by then. Luckily, I found my invite and saw that Adrian also didn't have the senior title then. I found this ridiculous on the one hand, but on the other hand, it also made it easier for me to accept a non-senior role.

Our first multi-year project was to replace parts of a PHP monolith with Go microservices. As you can probably imagine, this included a lot of PHP work initially, but after about six months, I was finally fully working with Go. Not only that, but I also worked with Postgres, whereas previously, I only worked with MySQL as my database. I learned a lot from my teammates, especially [Nikolai](https://www.linkedin.com/in/nikolaykrapivchenko/) and Adrian. I will never forget our hour-long discussions geeking out on topics like the optimal value for allowed cyclomatic complexity, or whether we should strive to support ease-of-use for frontend in our API design, or be more strict, representing the business logic more honestly instead.

Meanwhile, I tried convincing a few friends to switch from PHP to Go. I tried to couch some of them and provided them with [helpful Go resources](/blog/everything-you-need-to-know-to-start-with-go/) to kickstart their journeys. (There's at least one great guy who found these either valuable or at least motivating, right [Rael](https://www.linkedin.com/in/raelschmulian/)? ** INSERT GREAT SUCCESS MEME. **)

It was undoubtedly an exciting time for me, but not as exciting as the birth of my daughter in June 2018. A few months later, I started my year-long parental leave, which gave me enough time to take care of my firstborn, learn new things, create a CMS, and blog a little. Unsurprisingly, before this soft relaunch, the last entry went live right before I returned to the workforce. This time, I joined my team as a Lead Engineer.

### Back to Management

I was excited to lead the team I left behind as a software engineer. It was also interesting to be a co-lead again, sharing the position with Nikolai. We worked under the guidance of our lovely, funny, visionary, and just slightly crazy lead, [Claudia](https://www.linkedin.com/in/claudia-lajeunesse-gaicd-0395633/). I wish she stayed around longer in the company, but I'm grateful for her time with us.

One of the first things I needed to push for was to get rid of scrum. It was challenging at first, but I was pleased with the system we set up instead. Reading article after article about the end of scrum in the past four years was fun. I just wish I had written about our experience sooner. At this point, it might not make that much sense. By now, the industry understands that [scrum](https://www.linkedin.com/pulse/scrum-slowly-dying-david-pereira/) [is](https://blog.logrocket.com/why-scrum-is-becoming-irrelevant/) [dead](https://chrisjameslennon.medium.com/the-age-of-scrum-is-over-185407ad705b). Keep it simple, stupid!

While this change was exciting and exhaustive, it was a piece of cake compared to all the projects we had to ship while struggling to hire and ramp up more people. We always managed to deliver what we promised. If not on time, then with acceptable delays. I'm proud of what I and we have achieved in the past for years, riddled with personal issues, covid, and the birth of my second child.

There have been a lot of changes in my life since then, and of course, not only in mine. We've all learned how to deal with a pandemic and how to do remote work effectively. Many of us learned to cope mentally with a much more dangerous world.


### Four years later

Yesterday, I opened my blog at night, and the light background hurt my eyes so badly that I finally decided to give this blog a slight boost. I want to revisit some of my older posts and reflect on them after many years. If for no one else, it would be interesting for me to see how my thinking has changed. And now, this post will stay here for a while to remind me to write more often. We'll see if it works.

So the bottom line is: If this reads as a goodbye, it is not meant to be. It is a thank you to some great people and a hello again to whoever is interested!
