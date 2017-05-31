---
layout: post
title:  "Unit Test code and technical debt."
date:   2016-10-22 22:06:54 +0200
categories: unit_test 
---

Technical debt has many different meaning. It depends on the context that it is used in. Wikipedia has a nice statement that I quite like.

“The debt can be thought of as work that needs to be done before a particular job can be considered complete or proper. If the debt is not repaid, then it will keep on accumulating interest, making it hard to implement changes later on.”  – [wikipedia][wiki1]


Unit tests is one area where technical debt can be easily obtained, and the amount of debt can grow exceptionally quickly. It definitely needs to be forethought and well planned before it is used in full force. The following questions must be answered to fully.

**What language will the test code be implemented in?** – This is critical contributor to technical debt. If you use a language which the majority of your development team is not familiar with, the chances of increasing technical debt is quite high. As the language is not well known by your team, training will need to be provided to it and the future team that will be maintaining the code. For example, implementing the test code in Java while the code under test is in C means that your development team must know Java and C to deliver good software.

**Is the infrastructure of your unit test environment well supported?** – Using a unit test framework that does not have a well supported community (either through the online community or supported commercially) means that the support of it must be carried out by your development team. When the code enters maintenance phase, the unit test framework still needs to be maintained, as specially as the computers and operations system it is using starts to revised to newer versions. This particularly true if the code has a long life time, as it is true with most embedded software. As more test cases are being implemented, the amount of technical debt gets larger and it makes supporting the unit test framework quite difficult.

**Is the unit test framework integrated well with your tool chain?** – Using a unit test framework that is not well integrated in your tool chain means that the result from you test runs must be analysed manually. For a small project, manual analysis of the the test result is OK and relatively easy. However as the project gets bigger with a large code set with high level complexity, good integration into your tool chain is a must. This will ensure that the results are easily analysed, and the correct notifications are generated. It will ensure continuous integration can be achieved easily and automatically. It will also means that removing manual work will also reduce the risk of performing the manual process incorrectly.


By answering these questions, there is a chance that your technical debt could become technical credit.

---

I have written a Guide to Successful Unit Tests.
You can get it here at [Leanpub][leadpub_sut] and read about these topics and more.

[leadpub_sut]: https://leanpub.com/successfulunittest/

References

[wiki1]: https://en.wikipedia.org/wiki/Technical_debt