---
layout: post
title: Operations, Operators & Synthesis
modified:
categories:
excerpt: Accept that you will not know until you suffer. - Buddha (not)
tags: [Development, Ruby, Ruby on Rails, Operations, Advertising, Learning]
image:
  credit: Revelate. Concatenate. The animals we ate. At 98 we all rotate.
  feature: ampsnds.jpeg
date: 2015-08-27T21:16:06-04:00
---
I'm here to tell you now: The struggle to code well is real. And I'm not even that far along yet. So you could say my struggle is even a bit more pronounced, because I do not even know what I don't know. And while I can appreciate the fact that I don't have to know it all--and that I will never know enough to make me feel like I know enough--it's still difficult to accept.

But acceptance is the key to getting better. Accepting that you suck, and you don't know enough. And you have to keep screwing up to learn more and get better.

I've come across some very surprising (and cool) things in my coding experience so far. Like the following:

~~~ ruby
def unique(integers)
  integers & integers
end
~~~

This was a solution to a problem on <a href="http://codewarriors.com">codewarriors.com</a>, and that little ampersand was essentially the solution.

The problem?

> Remove Duplicates

> You are to write a function called unique that takes an array of integers and returns the array with duplicates removed. It must return the values in the same order as first seen in the given array. Thus no sorting should be done [...]

> Assumptions
* All values given are integers (they can be positive or negative).
* You are given an array but it may be empty.
* They (sic) array may have duplicates or it may not.
* <b>You cannot use the uniq method on Arrays (don't even try it), or the nub function from Data.List.</b> (bolding mine.)

My problem? Well, I don't have a problem, per se. I figured it out, eventually.

But...

As a person who has spent the last 10 or so years perfecting the art of approaching operational/strategic/business problems with the intent of relentless due diligence up front and flawless execution, my mind had me scouring the now slightly more familiar landscape of the Ruby on Rails materials I knew. And what I knew of the "&" operator was its use in sets of two to define if/else statements (e.g., the logical AND operator):

~~~ ruby
def find_integer(array)
  for element in array
    if element.is_a?(Integer) && yield element
      return element
    end
  end
end
~~~

And so for a long time I looked in other directions, and started writing code that had more to do with trying to anticipate what kinds of combinations of elements could show up in arrays. I was focusing on making sure the order was maintained. That if one array was empty I'd still need to return the items in the other (as long as there were no duplicates in that one). That I <i>couldn't</i> use <b>uniq</b> (Why not!? I knew that was the answer!)

And my mind wandered around in that forest for awhile. Then I saw it.

Simple, peaceful: &

The single & operator as used with the Array class in Ruby takes two sets of data, and simply returns the set intersection (read: common elements) of those two sets.

Little revelations like this one happen to me every day, every time I sit down to code. And I'm happy to be challenged. And I'm also glad that I'm getting the opportunity to flip the script I'm so used to reading from, because I'm guessing that over time, I'm going to gain some new perspectives on some things I've become very used to doing, which can only yield better results over time.
