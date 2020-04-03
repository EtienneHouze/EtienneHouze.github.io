---
layout: post
title:  The ant and the elastic rope
date:   2020-03-20 16:22:50 +0100
categories: test
---

A classical example of counter-intuitive mathematics
============

Imagine a rope, of length 1 meter, lying somewhere on the ground. One this rope, on day 1, climbs an ant. The ant is at one end of the rope and, each day, slowly crawls 1cm towards the other end. I know, this ant is not really fast, but hey, it is a lazy ant. However, each night, as the ant is resting, a malicious person stretches the rope by one meter. This rope being kind of magical, it can be stretched as long as this malevolent person wishes.

The ant might be lazy, but it is resilient, and decides to pursue its quest to the other end. On day 2, it crawls one more centimeter, then goes to rest again. Once more,  the malevolent devil stretches the rope by one meter at night. And this goes on, and on, and on.... But how long will it last ? Will the ant one day reach the other end of the rope, or is it doomed to endlessly crawl on this rope while someone is stretching it every night ?

Well, think about it for a while, and then take a deep breath and see how maths can help sort this out !

First glance 
------------

At first glance, one might consider how far the other end is from the ant, and these distances are noted below :

|Morning | Remaining distance|
|:-------|:------------------|
|   0    |    100cm          |
|   1    |    199cm          |
|   2    |    298cm          |
|   3    |    397cm          |

It seems fairly straightforward, looking at this table, that the ant is never going to complete its quest: each evening, it is further away from its goal. Knowing that for the journey to be complete, the remaining distance would have to be 0cm, it is obvious that the ant will never succeed.

Easy, right ? 

A closer look
--------

Well, not quite...

Thinking a bit more about the problem, when one stretches a rope, the rope stretches everywhere. That means, in our example, that on the morning on the second day, the ant is further away from the goal than it was on the evening.
For instance, on the morning of day 1 (after one stretch of the rope), the ant is not 199cm away from its goal and 1cm away from the start, as we first thought, but rather 2cm away from the start, and 198cm away from the end. Apllying the same process for the first few days gives the following number :

|Morning | Remaining distance|
|:-------|:------------------|
|   0    |    100cm          |
|   1    |    198cm          |
|   2    |    295.5cm        |
|   3    |    392.7cm          |

Does it change a lot, though ? The ant is still, everyday, further away from the end that it was the previous. So its journey seems as doomed as it seemed before.

But, however, things are not so grim ! We need to consider taking another perspective to this problem. How about the proportion of the rope that the ant travelled each day ? On the first day, it travelled 1cm out of 100, so 1/100 of the total length. On the second day, it still manages to walk 1cm, out of 200 this time, so 1/200. On the third, 1/300 and on the fourth, 1/400. And things go like this, on and on and on...

\[
    \frac{1}{2}
\]
