---
layout: post
title:  The ant and the elastic rope
date:   2020-03-20 16:22:50 +0100
categories: test
mathjax: true
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

But, however, things are not so grim ! We need to consider taking another perspective to this problem. How about the proportion of the rope that the ant travelled each day ? On the first day, it travelled 1cm out of 100, so $\frac{1}{100}$ of the total length. On the second day, it still manages to walk 1cm, out of 200 this time, so $\frac{1}{200}$. On the third, $\frac{1}{300}$ and on the fourth, $\frac{1}{400}$. And things go like this, on and on and on...

$$
    S = \frac{1}{100} + \frac{1}{200} + \frac{1}{300} + \frac{1}{400} + \ldots
$$

The sum, that we name $S$, will go on and on, without ever stopping, ever adding smaller and smaller quantities. For the ant to complete its journey, we would have the total sum reaching 1.

## Of sums and infinity

How can we know for sure that the sum will grow larger than 1, or that it will never reach it ? Computers are useless here, since adding up a potentially infinte number of terms could be infinitely long...

In mathematical terms, this sum can have two outcomes: either it will come closer and closer to a limit value, in this case the sum is converging, or it will grow on forever towards infinity, and in that case it is diverging.

For many years mathematicians were uneasy with the notion of infinity, and struggled to evaluate whether this sum would converge or diverge. Even some of the greatest mathematicians of the 19th century failed to correctly answer this question !

However, it is possible to prove, that, without even computing a infinite number of additions, that this sum will diverge : it will grow towards infinity. How ? 

First, let's have a look at what means "growing towards infinity". Infinity is, by defintion, larger than every possible number. We can see the formal definition of this "growth towards infinty" as a game between you and I. You are free to pick any number, be it as large as you want. **If the sum is diverging towards infinty, for any number $n$ that you pick, I will be able to give you another number, $m$ such that the sum of the $m$ first terms of $S$ is larger than the $n$ you pick.**

That means that, for every possible number, $S$ will eventually grow larger than it. With this defintion, mathematicians succeeded in changing the notion of *infinity* into a property the sum has for any number. And while infinities are tricky, it is possible to prove that a property holds for any number. This is what we are going to do now.

## Splitting up the sum

The sum $S$ shows a pretty obvious pattern, from which we can reason to prove our property (that for any number, adding a certain chunk of its terms will eventually end up larger than this number).

Look closely at the terms in $S$, and how many of them are required to add up to at least $\frac{1}{200}$. The first one, obviously, is enough to reach over $\frac{1}{200}$. The second term, too. For the first two terms, we can write:

$$
    \frac{1}{100} \geq \frac{1}{200}
$$

$$
    \frac{1}{200} \geq \frac{1}{200}
$$

 Now, for the next ones, we get:

$$
    \frac{1}{300} + \frac{1}{400} \geq \frac{1}{200}
$$

$$
    \frac{1}{500} + \frac{1}{600} + \frac{1}{700} + \frac{1}{800} \geq \frac{1}{200}
$$

$$
    \frac{1}{900} + \ldots + \frac{1}{1600} \geq \frac{1}{200}
$$

And so on, each step requiring two times more terms from $S$. It works for the first terms, but can it work for *any* terms in the sum ? Well, yes, and that is because of the powers of $2$.

In every line, the denominator of the last term was a power of $2$ times $100$. And since this is the smallest term of the line, all the others are larger. So, for instance:

$$
    \frac{1}{1700} + \frac{1}{1800} + \ldots + \frac{1}{3200} \geq \frac{1}{3200} + \frac{1}{3200} + \ldots + \frac{1}{3200}
$$

this inequality coming from replacing all terms in the left hand side with the smaller $\frac{1}{3200}$ term. And, since there are $16$ terms in this sum, we have

$$
    \frac{1}{1700} + \frac{1}{1800} + \ldots + \frac{1}{3200} \geq \frac{1}{3200} + \frac{1}{3200} + \ldots + \frac{1}{3200} = 16 \times \frac{1}{3200} = \frac{1}{200}
$$

In the end, if we play the "game of diverging", and you give me $\frac{7}{200}$, I can answer you $32$, because, if we add all the seven previous inequalities, we will get

$$
    \frac{1}{100} + \frac{1}{200} + \ldots + \frac{1}{3200} \geq 7 \times \frac{1}{200} = \frac{7}{200}
$$

And this will be the same for the following terms, and the ones after. So, by dividing the general sum $S$ into chunks of terms, each one with two times more terms than the previous, we are guaranteed that each one of these chunks will add to more than $\frac{1}{200}$.

So, if you pick any number, let's call it $n$. So I will give you a number $m$ such that $m$ is big enough to fit $200 \times n$ chunks. We can even show that $m = 2^{200n + 1}$ works. This means that the sum will diverge towards infinty, and be as big as we want.

## Back to the ant
For the poor ant, that is some good news: given enough time, no longer will it be able to reach the end of the rope, but it will also be able to go as far as it wants !

However, for it to reach the end of the rope, it would require around $2^{201}$ days, which is quite some time (almost $9\times10^{57}$ years). And which is way to big to be directly computed by any computer that we know of...