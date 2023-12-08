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

4.5 years ago I wrote a little blog post that I’d like to republish, after spending 4 more years in management. Noet that at the time of writing of the original piece, I’ve had roughly 3 years of management experience and I had managed about 5-7 people in total. Since then, I spent another 4 years in management and have managed another 15-20 people at least. Below is a slightly revised version of the original post, which is still available [here](https://peteraba.com/blog/the-danger-of-detached-management/). If you’ve read that post, you can script straight to the [solutions section](#solutions).

## Scenario - The good parts

![The good parts](/media/revised-the-danger-of-detached-management/happy.png "Happy unicorns and fluffy mythical creatures in front of a rainbow")

So let's say you have a software feature team made up of a handful of focused and experienced professionals and perhaps a few juniors just for good measure. Let's also imagine that this is true for both the engineers and the product managers. Let's say they together manage to implement a very fruitful culture where things to deliver and their priorities are always clear. Things also get delivered more or less on time and technical debt is also kept under control. Sounds great so far, right?

To color that picture a bit further, let's also imagine that this imaginary team has some process in place to improve their internal processes and discuss pressing issues. For example, they might meet regularly for [Kaizen meetings](https://www.wikiwand.com/en/Kaizen) to keep things generally improving.

Now let's say that said team also has a lead, but that lead is mostly involved in high level discussions, long term plans and in some cases aligning with other teams on said long term plans and their execution. She has her calendar full of meetings with stakeholders and upper management while she also takes part in the hiring process.

## Impact - The bad parts

![The bad parts](/media/revised-the-danger-of-detached-management/sad.png "Gloomy image of unicorns and fluffy mythical creatures looking for food")

It's obvious that she lifts a lot of weight off the team's back, practically enabling them to focus on the product and engineering tasks. I suppose this should still sound great, there's hardly anything to boost team performance more than cutting out distractions. The problems start when she decides not to have one-on-one's with her team members since she's not really part of the team's day-to-day work. She also considers attending stand-ups and Kaizens to be optional for her. This however can render her practically detached from her team.

These actions can and will in-effect the team in a few ways.

### 1. Hard to get help

Perhaps least importantly, if and when there is a problem that the team can not solve themselves, it will be harder to get the lead to make good decisions or even weigh in, because first she’s not used to weighing in on team issues, and second she might lack some important context which is not always easy to obtain on the spot.

### 2. Awkward team activities

Team members may also feel somewhat awkward or even anxious around a detached lead as she may be seen as some sort of outsider without sufficient amount of regular interaction. As a consequence, this may also poison team activities such as team events to some extent, simply because some might feel less ready to open up in front of someone who has not earned their trust. This is probably more of a problem for introverted team members, but still worth mentioning.

### 3. Lack of trust

Lack of touch can also cause a lack of transparency and team members might start wondering what their lead is doing most of her time and whether she has enough insight into the teams' work to be able to properly represent them in long term planning sessions with other managers.

### 4. Understanding team performance

Let’s say the [OKR](https://en.wikipedia.org/wiki/Objectives_and_key_results) says product X will be delivered by the end of the quarter but then some urgent request comes up that pushes the team to deliver product Y first. Or perhaps there’s also a dependency on team Z to deliver product X and they’re late. Either way at the end of the business quarter product X is not delivered, therefore a detached manager may think that the overall performance of our imaginary team is less than great. Needless to say, technical improvements throughout the quarter might go unnoticed even more easily of course.

### 5. Understanding individual performance

Team members might be judged on weird measures like being typically vocal or less vocal during selected meetings attended by the lead. Imagine if that was being used as a deciding factor for your relative performance compared to the team average. This can of course further lead to team members getting unfair and unhelpful promotion feedback, which will inevitably force valuable employees to seek better treatment and potentially promotions elsewhere.

Another common consequence is looking at somewhat artificial numbers like tickets reviewed, tickets closed, number of lines changed, etc. (While I don't think I was ever really detached from my teams, I'm also guilty of this, I plan to write about this in some later post.) 

### 6. Creating legacy systems

Possibly the most important consequence of such unfair feedback is that people who don't quit will typically adjust. When technical greatness is not appreciated, people will simply focus on product delivery and quality will naturally decline. In software development this means that eventually the system will become a mess that no one wants to touch anymore. When this happens, the lead will have her job failed as hard as possible, no matter how great a job she does doing her day-to-day job.

When closed tickets and similar are used to measure performance, engineers will adjust, and in extreme cases they might create a new ticket for the tiniest of things, which will obviously make them less performant as they'll spend more time with administration, then development. (More about that in some later post.)

I imagine most of the above would apply to any delivery team, in or outside of IT, however with software feature teams there's an extra risk: Whether the product delivered is of poor or great quality can be very hard to tell. Yes, if the live system is broken every second day, that's a clear sign. Or in case the UI is not usable, it's easy to assume that the code is one big pile of stinky brown material. However, the complexity of even the simplest software systems is still more complex than most other products in life and this means even software that does a decent job on the surface might be less than pleasant to work on as an engineer. When a leader is detached from the team, there's a good chance that she'll only realise the poor state of the system her team manages when people are already leaving or have left as a consequence. (This tends to be the story behind most, if not all, "legacy-refactoring" projects.)

## Solutions

![Solutions](/media/revised-the-danger-of-detached-management/hope.png "Asian girl holding a glowing crystal ball")

Here's what I think our imaginary lead should do:

1. She should create rapport with her team members. Regular one-on-ones should be considered a foundation for that. If applicable, she should even schedule regular skip-level one-on-ones.

2. She should make sure to be present in some team meetings regularly which shows that she cares about team dynamics. (In the above scenario, this would mostly mean the Kaizen meetings.) It's okay for her to weigh in on issues as well, but it's more important to offer her support in implementing some of the solutions best fit for her capabilities, expertise and pay grade. There's no need to take all the team issues upon herself of course, good professionals don't need babysitting, but being ready to help can go a long way.

3. She should also make sure that the team knows what she's doing day-to-day. Of course this does not mean that she needs to report everything to the team every day, but letting the team know regularly what she's focusing on, what problems are on her plate is usually appreciated.

4. Attend team events and team celebrations religiously. The team should always be aware that their lead is a human being, someone that can relate to their issues and is there for them in bad and good times alike.

I guess being a manager is not easy, and one of the toughest things about it is that sometimes there's very little difference between being great or bad at it.

{{< infobox title="Note" class="alert" >}}
<p>The images for this post were generated by <a href="https://openai.com/dall-e-3" rel="nofollow">DALL-E</a>. No unicorns, pegasuses or any other beings were harmed in the process.</p>
{{< /infobox >}}