---
layout: post
title:  "Why Should Developers Write Unit Tests?"
date:   2017-01-03 00:00:00 -0500
categories: professional
tags: [programming, testing]
---
Even though nowadays it is generally expected that developers would always write [unit tests](http://artofunittesting.com/definition-of-a-unit-test/), I have run into quite a few of them who loathe doing that. In fact if it weren't for [test coverage](http://istqbexamcertification.com/what-is-test-coverage-in-software-testing-its-advantages-and-disadvantages/) gates in the code check-in process, they would completely skip that step and keep coding new features instead. But forcing developers to meet a certain testing metric does not always produce the desired results. You can end up with a bunch of useless test cases that were written specifically to meet the minimum required coverage threshold.

Now I will admit that I myself have sometimes wondered what the point of unit tests was. Why should I have to write a completely separate set of methods to prove that the code I wrote in the main source directory actually works? Keep in mind that when done the right way, the amount of code in the unit tests is often greater than the amount of code that is being tested. It seems to be a terrible waste of valuable developer time and effort.

In my mind, there are two convincing reasons [why unit tests](https://en.wikipedia.org/wiki/Unit_testing#Advantages) make a lot of sense.
- When I approach the problem with a testing mindset, I discover facets that are not readily apparent when I am only thinking about the solution. For example, writing tests leads me to address concerns such as boundary conditions and exception scenarios. Of course, [test first development](http://www.extremeprogramming.org/rules/testfirst.html) is a natural extension of this line of reasoning and has proven to produce better designs and fewer bugs in new code.
- Value is also realized when someone (even if it is me) revisits the main code to either enhance its capabilities or fix defects. The developer can confidently make changes knowing that the existing unit tests would protect him from accidentally breaking current functionality. That safety net pays for itself as long as the code lives.

However, to truly benefit from the above, the developer should put in the effort to [write good unit tests](http://softwaretestingfundamentals.com/unit-testing/). This does take some learning and experience. Additionally, the developer should follow best practices to ensure the test code is of the highest quality. This is especially important because there are no unit tests to back up the original unit tests.
