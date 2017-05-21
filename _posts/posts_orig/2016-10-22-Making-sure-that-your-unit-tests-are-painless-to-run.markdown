---
layout: post
title:  "Making sure that your unit tests are painless to run."
date:   2016-10-22 22:06:54 +0200
categories: unit_test 
---
To reduce the obstacle of using unit tests in your development flow, it is a good idea to integrate it as part of your development work flow. The lower the barrier to setting it up, the more likely unit testing is going to be used.


The classical development flow is to have your design specifications stabilised and ready for implementation. In reality, at this early stage, stabilisation has different meaning to when the software module is ready for release. The importance of having the public functions stabilised is critical here. There are two reasons why.

The first one is that the users of your functions can rely on those published function signatures and have an understand of its behaviour. This is obvious and is one of the tenets of modern software development.

The second is if your unit testers are not the actual developers, the unit testers can start working on the test code once the public functions are known. There will be some adjustments to function calls as your module is being used.

However, the main key for using unit test in your development flow is to run the test with minimal effort.

When you are doing a build of your module, also include a step in your build process to execute the tests. In your build process, create a dependency of unit test runnable based on your source code and unit test code. As soon as any of those changes, your unit test will get built and executed.

Any mismatch between the unit test code and your module will get picked up. By having your unit test code written by another person, it also creates a method of validating the design documentation. It checks that both code and documentation are aligned.

By making the execution as one of the steps in your build process, it is essential to make a decision whether you want to do when the unit test fails. There are two obvious ways.

The most obvious ways is to treat the unit test fails as warnings and allow the build to complete. I am not a big fan of this method as it puts a lesser importance of unit tests.

The more discipline way is to treat unit test fails as build errors and stop the build process from moving onto the next stop until the errors are fixed. This is much stricter method and is a more discipline method of software development.

Whatever build system you are using, spend some time to integrate the building and executing of unit tests into your build sequences. It will be worth the effort in the long run.

---

I have written a Guide to Successful Unit Tests.
You can get it here at [Leanpub][leadpub_sut] and read about these topics and more.

[leadpub_sut]: https://leanpub.com/successfulunittest/