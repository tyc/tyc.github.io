---
layout: post
title:  "Why you need to measure your test coverage?"
date:   2016-10-22 22:06:54 +0200
categories: unit_test 
---
I was at a meetup recently and I asked the question on what tools are available for measuring coverage data during a test run for an up and coming programming language. Some comments were made that coverage measurements are not that important in the scope of unit testing. I was rather taken back by this comment. Coverage measurements must be part of the data that is used how determine how successful the testing was.

To get useful measurement of coverage, lets go through what is meant by coverage. From a testing perspective, if a requirement can be validated by tests, the requirement is covered by tests. The validation comes by testing the implementation’s behaviour is the same as the requirement.

## Stuff that needs coverage

Executed code – There are code that you write that are absolutely critical to the functionality of your product. Software modules such as your scheduler or startup code must be covered. These modules are core. There are also code that will be executed but its functionality are not so critical. An example might be a module that performs a maths calculation, its accuracy is important but the time it takes is not so important. Both types of code must be unit tested as they are executed.


Safety Critical Code – These code performs functions that are critical to the safety of the user. This might include software function dealing with air bag system in a car. These type of code must be covered to ensure its correct behavior.


Code that will be audited – Some of the code written will be audited to ensure that it conforms to a set of design principles. The validation of these code are based on the auditing.


Safe path execution – not only should the code execution be covered, the path which the execution takes should also be covered. For code dealing with functional safety, the safe execution path must be mapped out when a failure occurs. In this context, failure means a failure that can be detected and managed. For example, the code detects that some critical memory has become corrupted, so the execution path to recover or to contain the corruption must be checked.


I have only given four examples where coverage is a very good tool to use. It is the only the metric to ensure that all of your code is tested.

--

I have written a Guide to Successful Unit Tests.
You can get it here at [Leanpub][leadpub_sut]. or here at Gumroad. and read about these topics and more.

[leadpub_sut]: https://leanpub.com/successfulunittest/