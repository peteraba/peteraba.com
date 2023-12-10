+++
draft = false
section = "blog"
title = "Revised: The danger of detached management"
description = "Revision of The danger of detached management especially in software engineering teams"
pubdate = "2023-12-08T14:40:00+02:00"
date = "2023-12-08T14:40:00+02:00"
keywords = ["management"]
tags = ["management"]
thumbnail = ""
has_code = false
+++


![Revised: The danger of detached management](/media/revised-the-danger-of-detached-management/top.png "Image of a detached caravan")

## Preface

4.5 years ago, I wrote a little blog post that I'd like to republish after spending four more years in management. Note that at the time of writing the original piece, I had roughly three years of management experience, and I had managed about 5-7 people in total. Since then, I have spent another four years in management and lead at least 20 more people. Below is a slightly revised version of the original post, which is still available [here](https://peteraba.com/blog/the-danger-of-detached-management/). If you've read that post, you can skip straight to the [solutions section](#solutions).

## Scenario - The good parts

![The good parts](/media/revised-the-danger-of-detached-management/happy.png "Happy unicorns and fluffy mythical creatures in front of a rainbow")

Let's say you have a software feature team comprising a handful of focused and experienced professionals and perhaps a few juniors just for good measure. Let's also imagine that this is true for both the engineers and the product managers. Together, they implement a very fruitful culture where it's always clear what to deliver, and so are their priorities. The team ships features more or less on time and keeps technical debt under control. Sounds great so far, right?

To color that picture further, let's say that this imaginary team uses some system to improve internal processes and discuss pressing issues. For example, they meet regularly for [Kaizen meetings](https://www.wikiwand.com/en/Kaizen) to keep things improving.

Let's say that said team also has a lead, but she's primarily involved in high-level discussions, long-term plans, and, in some cases, aligning with other teams on said long-term plans and their execution. She has her calendar full of meetings with stakeholders and upper management while also participating in the hiring process.

## Impact - The bad parts

![The bad parts](/media/revised-the-danger-of-detached-management/sad.png "Gloomy image of unicorns and fluffy mythical creatures looking for food")

She lifts a lot of weight off the team's back, enabling them to focus on the product and engineering tasks. This should sound great; there's hardly anything to boost team performance more than cutting out distractions. The problems start with her decision not to have one-on-ones with her team members since she's not really part of the team's day-to-day work. She also considers attending stand-ups and Kaizens to be optional for her. This, however, can render her practically detached from her team.

These actions can and will affect the team in a few ways.

### 1. Hard to get help

If and when there is a problem the team can not solve itself, it might be more challenging for the lead to make good decisions or even weigh in at times because she is not used to weighing in on team issues. She might lack some important context and a solid understanding of team dynamics, which is not always easy to obtain on the spot.

### 2. Awkward team activities

Team members may also feel awkward or anxious around a detached lead, as some might see her as an outsider without sufficient regular interaction. Consequently, this may also poison team activities such as team events when she's present because some might feel less ready to open up in front of someone with power who has yet to earn their trust. This is more of a problem for introverted team members, but it is still worth mentioning.

### 3. Lack of trust

A lack of touch can also cause a lack of transparency. Team members might wonder what their lead is doing and whether she has enough insight into the teams' work to represent them properly in long-term planning sessions with other managers.

### 4. Understanding team performance

Let’s say that according to the [OKR](https://en.wikipedia.org/wiki/Objectives_and_key_results), the team should ship product X  by the end of the quarter, but then some urgent request pushes the team to deliver product Y first. Or perhaps there’s also a dependency on team Z to deliver product X, and they’re late. Either way, product X will not be shipped at the end of the business quarter. Therefore, a detached manager may think that the overall performance of our imaginary team is mediocre or worse. Because she is disconnected, she might also miss or dismiss technical improvements.

### 5. Understanding individual performance

A detached lead might also start judging individuals on weird measures like being typically vocal or less vocal during selected meetings attended by the lead. Imagine if that was being used as a deciding factor for your relative performance compared to the team average. This can lead to team members getting unfair and unhelpful promotion feedback, inevitably forcing valuable employees to seek better treatment and promotions elsewhere.

Another common consequence is looking at somewhat artificial numbers like pull requests created, issues closed, the number of lines changed, etc. (While I don't think I was ever really detached from my teams, I'm also guilty of this. I plan to write about this in some later post.)

### 6. Creating legacy systems

Arguably, the most important consequence of such unfair feedback is that people who don't quit will typically adjust. When technical greatness is not appreciated, people will focus entirely on product delivery, and code quality will naturally decline. In software development, this means that eventually the system will become a mess that no one wants to touch anymore. When this happens, the lead will have failed her job as hard as possible, no matter how great a job she does in her day-to-day tasks.

Engineers will adjust their behavior when management uses the number of closed tickets and similar statistics to measure performance. For example, they might create a new ticket for the tiniest things, which will obviously render them less performant as they'll spend more time with administration than development. (More about that in some later post.)

Most of the above is likely true for any delivery team, in or outside IT. However, with software feature teams, there's an extra risk: It can be challenging to tell whether the product delivered is of poor or excellent quality. Yes, if the live system crashes every second day, that's a clear sign. Or, in case the UI is not usable, it's easy to assume that the code is one big pile of stinky brown material. However, even the simplest software systems are still more complex than most other products in life, and this means even software that does a decent job on the surface might be less than pleasant to work on as an engineer. When a leader is detached from the team, there's a good chance that she'll only realize the poor state of the system her team manages when people are already leaving or have left as a consequence. (This tends to be the story behind most, if not all, "legacy-refactoring" projects.)

## Solutions

![Hope](/media/revised-the-danger-of-detached-management/hope3.png "Hell to Eden via a tunnel")

Here's what I think our imaginary lead should do:

1. She should create rapport with her team members. Regular one-on-ones should be a foundation for that. If applicable, she should even schedule regular skip-level one-on-ones.

2. She should be present in some team meetings regularly, which shows that she cares about team dynamics. (This would primarily mean the Kaizen meetings in the above scenario.) It’s okay for her to weigh in on issues, but it’s more important to offer her support in implementing some of the changes the team wants to implement. Of course, there’s no need to handle all the team issues. Good professionals don’t need babysitting. But for a lead to be ready to help can go a long way.

3. She should also ensure the team knows what she's doing. Of course, this does not mean that she needs to report every task to her team daily, but at least regularly letting the team know what she's focusing on is usually appreciated.

4. Attend team events and team celebrations religiously. The team should always be aware that their lead is a human being who can relate to their issues and is there for them in bad and good times.

I guess being a manager is not easy, and one of the most challenging things about it is that sometimes there's very little difference between being great or bad at it.

{{< infobox title="Note" class="alert" >}}
<p>The images for this post were generated by <a href="https://openai.com/dall-e-3" rel="nofollow">DALL-E</a>. No unicorns, pegasuses or any other beings were harmed in the process.</p>
{{< /infobox >}}