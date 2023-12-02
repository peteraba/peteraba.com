+++
draft = false
section = "blog"
title = "FP public code review (#1)"
description = "Looking at how to solve problems in different languages is fun"
pubdate = "2018-05-13T13:58:00+01:00"
date = "2018-05-13T13:58:00+01:00"
keywords = ["fsharp", "functional", "exercism.io", "discuss"]
tags = ["fsharp", "functional", "exercism.io", "discuss"]
thumbnail = ""
has_code = true
+++

This post first appeared on my [dev.to](https://dev.to/peteraba/go-is-my-gateway-drug-5efm).

Imagine the following: You're a software engineer in a small team of an amazing but small company. One day your lead comes up to you saying that the company is looking for more engineers to hire but the person in charge of the tech part of the process had to leave in a hurry for her home country in the middle of the process. Unfortunately she won't be available in the foreseeable future.

Originally there were tons of applications but HR and some juniors already filtered out the most obviously weak ones. There's still a handful of applications for you to sort out however. All the applicants solved the same set of problems using some online tool and your job is to check all remaining solutions for one of the problems.

Since there's only time to invite a limited amount of applicants for an on-site interview, they'd like to have your expert opinion about how well each applicant performed. There will be other factors for sending out the invitation(s) so they need more from you than just selecting the best solution. It would be best if you could describe what each solution does well and how they could be improved, but please make sure to score each from 1 to 10, 10 being a perfect solution.

All solutions are in F#, but the company is looking for good programmers, not necessarily F# experts. It's okay if they aren't using F#-specific shortcuts although that's okay too. You need to review their solutions for the following problem: (copy-paste from the Sieve [exercism.io](http://exercism.io) problem)

# Sieve problem

Use the Sieve of Eratosthenes to find all the primes from 2 up to a given
number.

The Sieve of Eratosthenes is a simple, ancient algorithm for finding all
prime numbers up to any given limit. It does so by iteratively marking as
composite (i.e. not prime) the multiples of each prime,
starting with the multiples of 2.

Create your range, starting at two and continuing up to and including the given limit. (i.e. [2, limit])

The algorithm consists of repeating the following over and over:

- take the next available unmarked number in your list (it is prime)
- mark all the multiples of that number (they are not prime)

Repeat until you have processed each number in your range.

When the algorithm terminates, all the numbers in the list that have not
been marked are prime.

The Wikipedia article has a useful graphic that explains the algorithm:
https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes

Notice that this is a very specific algorithm, and the tests don't check
that you've implemented the algorithm, only that you've come up with the
correct list of primes.

### Source

Sieve of Eratosthenes at Wikipedia [http://en.wikipedia.org/wiki/Sieve_of_Eratosthenes](http://en.wikipedia.org/wiki/Sieve_of_Eratosthenes)

# Solutions

Here are the solutions you need to rate, review and report back to management and HR. Use the a comment section of this post for communicating with them:

## Solution #1
```fsharp
let primesUpTo2 limit =
    let rec mark st acc prime limit =
        let acc' = acc + prime
        match acc' > limit with
        | true -> st
        | false -> mark (Set.add acc' st) acc' prime limit

    let rec iterate st list limit =
        match list with
        | [] -> st
        | x::tail ->
            match Set.contains x st with
            | true -> iterate st tail limit
            | false ->
                let st' = mark st x x limit
                iterate st' tail limit

    let list = [2..limit]
    let nonPrimes = iterate Set.empty list limit
    (Set.ofList list) - nonPrimes |> Set.toList
```

## Solution #2
```fsharp
let primesUpTo3 n =
    let sieveStep n ((primes, composites) as acc) i =
        if Set.contains i composites then acc
        else (i :: primes, {i..i..n} |> Set.ofSeq |> Set.union composites)

    {2..n}
    |> Seq.fold (sieveStep n) ([], Set.empty)
    |> fst
    |> Seq.rev
```

## Solution #3
```fsharp
let primesUpTo1 limit =
    let sq = (limit |> float |> (fun n -> n ** 0.5) |> int )

    let filterMultiples possiblePrimes prime =
        if prime > sq then possiblePrimes
        else possiblePrimes |> List.filter (fun x -> x <= prime || x % prime <> 0)

    let possiblePrimes = [ 2 .. limit ]

    List.fold filterMultiples possiblePrimes possiblePrimes
```

## Solution #4
```fsharp
let primesUpTo4  n =
    let isMultiple factor x = x % factor = 0
    let rec seiveNextPrime primes = function
        | prime :: tail -> seiveNextPrime (prime :: primes) (List.filter (isMultiple prime >> not) tail)
        | [] -> List.rev primes
    seiveNextPrime [] [2..n]
```

## Solution #5
```fsharp
type Candidate  =
    | Unmarked of int
    | Marked of int

let primesUpTo5 limit =
    let mark prime range =
        range
        |> List.map (
            function
            | Unmarked i when i % prime = 0 -> Marked i
            | c -> c)

    let rec sieve marked =
        function
        | [] -> marked |> Seq.rev
        | ((Unmarked p) as pp) :: tail -> sieve (pp :: marked) (mark p tail)
        | c :: tail -> sieve (c :: marked) tail

    [2..limit]
    |> List.map Unmarked
    |> sieve []
    |> Seq.map (
        function
        | Unmarked i -> i
        | _ -> 0)
    |> Seq.filter ((<) 1)
```

If you like this discussion, let me know and there might be more coming.