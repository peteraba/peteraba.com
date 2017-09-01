+++
draft = true
section = "blog"
title = "Everything You Need to Know about Generics in Go 2.0"
description = "Links for understanding the current state generics in Go 2.0"
pubdate = ""
date = "2017-09-01T13:16:28+02:00"
keywords = ["go", "generics"]
tags = ["go", "generics"]
thumbnail = ""
disqus_url = "https://peteraba.com/post/everything-you-need-to-know-about-generics-in-go-2.0"
disqus_identifier = "everything-you-need-to-know-about-generics-in-go-2.0"
disqus_title = "Everything You Need to Know about Generics in Go 2.0"
has_code = false
+++

The lack of Generics in Go have been discussed ever since the first public release of Go and this is one of the few
features the Go team has always declared to be discussed internally as well. However Go is a language which tries to be
as "small" as possible and all versions of generics discussed so far seemed to introduce more problems than what they solve.

On 13th of July, 2017, during GopherCon 2017, [Russ Cox announced the beginning of discussions for Go 2.0](https://www.youtube.com/watch?v=0Zbh_vmAKvk).
This inspired many experienced Go developers to express their feelings and opinions on Generics.

### Pre-GopherCon posts

 - [Golang has generics - Why I Don't Miss Generics Anymore - 2014-06-30](http://blog.jonathanoliver.com/golang-has-generics/)
 - [Idiomatic Generics in Go - 2014-09](http://bouk.co/blog/idiomatic-generics-in-go/)
 - [Living without generics in Go - 2014-12-12](https://web.archive.org/web/20141227092139/http://www.weberc2.com/posts/2014/12/12/living-without-generics.txt)
 - [Poor man's generics in Golang (Go) [or pick your poison] - 2016-05-30](https://codeblog.shank.in/poor-mans-generics-in-golang/)
 - [Who needs generics? Use ... instead - 2016-07-14](https://appliedgo.net/generics/)
 - [Using code generation to survive without generics in Go - 2017-05-09](https://www.calhoun.io/using-code-generation-to-survive-without-generics-in-go/)
 - [Closures are the Generics for Go - 2017-07-07](https://medium.com/capital-one-developers/closures-are-the-generics-for-go-cb32021fb5b5)
 - [Golang Pros & Cons for DevOps (Part 3 of 6): Speed vs. Lack of Generics - 2017-07-10](https://blog.bluematador.com/posts/golang-pros-cons-devops-part-3-speed-lack-generics/)

### Post-GopherCon posts

 - [Why I miss generics in Go - 2017-07-14](https://medium.com/@watchforstock/why-i-miss-generics-in-go-9aef810a1bef)
 - [Go experience report: the append function - 2017-07-15](https://www.airs.com/blog/archives/559)
 - [Should Go 2.0 support generics? - 2017-07-22](https://dave.cheney.net/2017/07/22/should-go-2-0-support-generics)
 - [Generics on Go’s stdlib - 2017-07-28](https://hackernoon.com/generics-on-gos-stdlib-10de52fe824d)
 - [Are We There Yet: The Go Generics Debate - 2017-08-09](https://dzone.com/articles/are-we-there-yet-the-go-generics-debate)
 - [A use case for Go Generics in a Go compiler - 2017-08-09](https://dr2chase.wordpress.com/2017/08/09/a-use-case-for-go-generics-in-a-go-compiler/)
 - [Generics - I Wish You Were Here... - 2017-08-19](https://varunksaini.com/blog/use-case-for-generics/)
 - [Go Experience Report for Generics: Google metrics API - 2017-08-25](https://medium.com/@sameer_74231/go-experience-report-for-generics-google-metrics-api-b019d597aaa4)

### Experience reports

The Go team is also collecting so called experience reports which they plan to use for finalising the feature set for Go 2.0. The list for generics can be found on [Github](https://github.com/golang/go/wiki/ExperienceReports#generics).

