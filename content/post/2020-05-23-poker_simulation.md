---
title: Using Simulation to Understand Probability - Application to Poker
author: Brett J. Gall
date: '2020-05-23'
slug: poker-simulation
categories:
  - Programming
  - Statistics
  - Teaching
tags:
  - Programming
  - R
  - Simulation
  - Teaching
---

Many researchers, students, and consumers of empirical research have poor understandings of probability distributions, calculus, and key concepts necessary for mathematical statistics. At the same time, even researchers with PhD in quantitative fields can have difficulty understanding and interpreting concepts like p-values and confidence intervals. Over time, I've found that the best way to help individuals think through their quantitative problems and understand the logic of statistical inference is by focusing on the data-generating process as the concept of interest. Even without their formalization, the intuition of potential outcomes and the conceptualization of frequentist inference as comparing the data to an assumed process are powerful and intuitive. The [Lady Tasting Tea](https://en.wikipedia.org/wiki/Lady_tasting_tea) was my first introduction to causal inference, but it arguably should be our first introduction to empirical research more generally.

Once individuals start to think in terms of data-generating processes, I suspect we too quickly shift to trying to understand probability distributions and their properties. An intermediate step that is often saved until advanced courses - when it offers much pedagogical potential early on - is to approach problems through simulation. Apparently, [some agree](https://press.princeton.edu/books/hardcover/9780691167039/quantitative-social-science) and have incorporated example-by-simulation into introductory texts.

While eating lunch today, I came across a great case on an online statistics-help forum where simulation could help someone with minimal understanding of statistics. In short, until recently, the poster had played many hands of online poker and found great success, accumulating a sizable amount of winnings. However, the poster expressed concerned that the online site was now stacking the deck against him. Specifically, he wrote "it seems that my first 2...cards have a very low percentage of face cards." The poster then asked whether there was any way to test whether the site's system was indeed changing the game to take back his winnings.

To the quantitatively trained, this is a straightforward applied problem. All we need to do is to determine whether the number of face cards the player observes after a given number of hands is unusually low given a fair deck. In fact, there is an analytic solution to the problem! However, to the individual who is unfamiliar with probability distributions, simulation is often much more informative in these applied settings.

So, how would we use simulation to assess whether the the deck was indeed stacked against him? Building the simulation requires several steps:

1. Build a deck of cards.
2. Deal 2 cards at random from the deck (without replacement).
3. Count the number of face cards dealt.
4. Return the cards and repeat step 2 and 3 for as many hands as the poster played.
5. Add up the total number of cards observed and total number of face cards observed across all hands.
6. Repeat steps 1 through 5 many times to simulate many games.
7. Compare the poster's observed face card rate to the rates we observed across our simulations.

This should make sense to many with minimal quantitative training: we're simply simulating many games under the assumption the deck is not stacked and then assessing the probability the poster observed a specified number of face cards given the deck was not stacked. For those familiar with R, you can wrap this up into a simple function as follows. For the code and a cleaner version of this document, check out [this link](https://www.dropbox.com/s/u2ci65q3p6pj9ak/simulation_poker_example.html?dl=0).
