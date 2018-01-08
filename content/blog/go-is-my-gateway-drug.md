+++
draft = false
section = "blog"
title = "Go is my gateway drug"
description = "How Go opened me up for functional languages"
pubdate = "2018-01-07T17:20:00+01:00"
date = "2018-01-07T17:20:00+01:00"
keywords = ["go", "programming", "php", "f-sharp", "python"]
tags = ["go", "programming", "php", "f-sharp", "python"]
thumbnail = ""
disqus_url = "https://peteraba.com/post/go-is-my-gateway-drug"
disqus_identifier = "go-is-my-gateway-drug"
disqus_title = "Go is my gateway drug"
has_code = true
+++

I've been a long time PHP / JavaScript developer by 2013 when I first started toying with Go. It's been almost 5 years by now and I've been an advocate of the language ever since. I was one of the many programmers who tried it out for the concurency primitives but stayed for it's simplicity. It was with Go that I realised how much nicer life is without inheritance and the rest of the OOP shenenigans. On the other hand Go also gave me a push to experiment with even more languages. It turned out to be my gateway drug to learning programing languages.

Of course, I played with some languages like Java, Python or Ruby before but honestly they didn't provide me anything that would be that much more than I had before. I was not interested in writing games, desktop or mobile apps at the time, I was happy as webdeveloper. To me Java felt too clumsy, Ruby felt too much magic and Python felt lacking the momentum at the time. (Not to mention the 2.x vs 3.x confusion.) Learning either of these languages felt too much work for the potential gain. With Go it was different, practically a love at first sight. It was so easy to learn and promised (and fulfilled) so much that I couldn't even stop learning more. Once I mastered it though, I realized that my old OOP languages feel verbose and my dynamically typed languages feel fragile. I was however feeling that Python was nicer to read than Go and this made me looking at further languages, mostly new ones like Rust and Elixir.

There are a few ways to try out new languages and I usually prefer doing a small project in them even if I never actually finish those projects. This past two weeks however I went back to an old favorite: [exercism.io](http://exercism.io). What's really nice about this service is that you can check how others solved a particular problem and with a bit of extra effort it's also possible to find or construct a "perfect" solution.

To showcase what I mean I'll add a few solutions for a simple problem called the Hamming problem throughout the exercism.io. The problem is simply finding the "distance" between two strings meaning the number of characters being different.


### PHP

Here's my PHP solution from 2015:

```php
<?php

function distance($a, $b)
{
    if (strlen($a) != strlen($b)) {
        throw new \InvalidArgumentException('DNA strands must be of equal length.');
    }

    $aSplit = str_split($a);
    $bSplit = str_split($b);

    $diff = array_diff_assoc($aSplit, $bSplit);

    return count($diff);
}
```

It's actually quite simple, there's just one if for checking the string lengths. On the other hand there are a few strange things about PHP already showing:

1. Notice how str\_split has a '\_' character to separate the parts but strlen is written as one word? Typical PHP...
2. Notice that array_diff_assoc is a rather specific function. It shows me that there is a very large standard library to learn.
3. Throwing an exception is okay. If you're a consumer of this function, you better catch the exception being thrown here.
4. The lack of types mean you can always call this function with whatever values you want from `null` to any type of `object`s, up to you. (Yes, this can be optionally fixed in PHP 7.0+, kind of.)


#### Note 1.

Hopefully no one would try to get everything done in one line, because it can seriously hurt anyone looking at it:

```php
<?php

function distance($a, $b)
{
    if (strlen($a) != strlen($b)) {
        throw new \InvalidArgumentException('DNA strands must be of equal length.');
    }

    return count(array_diff_assoc(str_split($a), str_split($b)));
}
```

#### Note 2.

One could also write the following using PHP 7 making some of the issues Go away.

```php
<?php

/**
 * @throws \InvalidArgumentException
 */
function distance(string $a, string $b): string
{
    if (strlen($a) != strlen($b)) {
        throw new \InvalidArgumentException('DNA strands must be of equal length.');
    }

    $aSplit = str_split($a);
    $bSplit = str_split($b);

    $diff = array_diff_assoc($aSplit, $bSplit);

    return count($diff);
}
```


### Go

My Go solution from 2017:

```go
package hamming

import "errors"

const testVersion = 6

func Distance(a, b string) (int, error) {
	if len(a) != len(b) {
		return -1, errors.New("Lengths of the provided strings are not equal.")
	}

	aBytes := []byte(a)
	bBytes := []byte(b)

	dist := 0
	for i, ch := range aBytes {
		ch2 := bBytes[i]
		if ch != ch2 {
			dist += 1
		}
	}

	return dist, nil
}
```

OK, what's the takeaway here?

1. This is considerably longer and more complex than the PHP solution.
2. On the other hand it requires much less prior knowledge from the user to understand, we don't even use the standard library. (To be fair it could also be avoided in PHP)
3. There's no way this solution could be written on one line without breaking readability completely.
4. Notice how the strong typing makes it impossible to call this method with weird data and how predictable the returned data is, except that error can also be a `nil`.
5. Notice how errors handled by just forcebly returning an error type, "never" throwing something unexpected. (In reality there is a panic which can be raised, but it's usage is different from your typical exceptions)
6. Make sure you understand that the error can be `nil`. *Warning:* There will be dragons!
7. It might be strange that the function starts with a capital letter whereas the other identifiers start with a smaller case. This makes the code public / exported in Go.

*Note:* I tried to find a more functional or considerably simpler solution but I didn't find any.


### Python

My Python solution again from 2015:

```python
"""Python distance exercise solution"""

def distance(text_one, text_two):
    """Calculate distance between two strings"""
    count = 0

    for (char1, char2) in zip(text_one, text_two):
        if char1 != char2:
            count += 1

    return count
```

Takeaway:

1. The cyclomatic complexity is a bit larger here than with PHP, even without the error checking, but I do find it easier to read.
2. Python's support for tuples and the `zip` function makes it kind of functional-like, although the `for` loop isn't all that usual in FP.
3. There's nothing preventing us from calling this function with strange data.
4. There's little we can expect from this function to be returned. If we change the return type to a string, the callers won't know until they get a runtime error.
5. We are using the standard library here but `zip` feels much less esoteric than `array_diff_assoc` was for PHP.

*Note:* My Python is roughly on advanced beginner level, Christoph Schindler appears to be more experienced, his solution reads even more functional-like:

```python
def distance(sequence, other):
    if len(sequence) != len(other):
        raise ValueError('Sequences must be of same length.')
    
    return sum(1 for a, b in zip(sequence, other) if a!=b)
```

Additional takeaway:

6. By raising a value error we can cause even more havoc on the caller's side.


### F-sharp

and finally here's the same thing I wrote in F# this week having about 2 days worth of experience:

```fsharp
module Hamming

let distance (strand1: string) (strand2: string): int option =
    match strand1.Length, strand2.Length with
    | x, y when x = y ->
        let seq1, seq2 = (List.ofSeq strand1), (List.ofSeq strand2)
        Some(List.fold2 (fun acc a b -> if a = b then acc; else acc + 1) 0 seq1 seq2)
    | _, _ -> None
```

What can we take away here?

1. It is slightly longer than the Python solution.
2. You may find the `match` syntax strange but you can think of it as an `if` on steriod for now.
3. There's no way you could call this function with wrong types.
4. The response is even more obvious than Go's is as the `null` part is not a surprise here, it's expressed by the `option` type annotation.
5. We are also using the standard library here but, much like `zip`, `List.fold2` and `List.ofSeq` also feel much less esoteric than `array_diff_assoc` in the PHP solution.


### Conclusions

I guess it's no surprise that I find the F# solution the best here but of course I do not mean to say that F# is the best language out of the four. I don't even think it's fair to say such a thing in general. I also don't think that this example proves in any way that FP is better than OOP. Obviously these examples provide no good insight into how hard these languages are to learn, how usable they are in the wild and many other important aspect of the languages. They do prove however, at least to me, that it's worth learning other languages as not all languages are equal.
